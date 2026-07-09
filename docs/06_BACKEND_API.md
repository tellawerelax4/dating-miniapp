# BACKEND API

Version: 1.0

---

# PURPOSE

This document defines the complete REST API specification.

Backend Framework:

NestJS

API Style:

REST

Authentication:

Telegram Mini Apps InitData + JWT

Response Format:

JSON

Every endpoint must validate input data.

Every endpoint must return standardized responses.

---

# API RULES

Base URL

/api/v1

---

Response Format

Success

{
    success: true,
    data: {}
}

Error

{
    success: false,
    error: {
        code: "...",
        message: "..."
    }
}

---

HTTP Status Codes

200 OK

201 Created

204 No Content

400 Bad Request

401 Unauthorized

403 Forbidden

404 Not Found

409 Conflict

422 Validation Error

429 Too Many Requests

500 Internal Server Error

---

# AUTH MODULE

POST

/auth/login

Purpose

Validate Telegram InitData.

Create or refresh JWT session.

Returns

Access Token

Refresh Token

User Profile

Registration Status

---

POST

/auth/refresh

Returns

New Access Token

---

POST

/auth/logout

Invalidates current session.

---

GET

/auth/me

Returns

Current authenticated user.

---

# PROFILE MODULE

GET

/profile

Returns

Current profile.

---

POST

/profile

Creates profile.

Allowed only once.

---

PATCH

/profile

Updates profile.

---

DELETE

/profile

Schedules profile deletion.

30-day grace period.

---

POST

/profile/restore

Cancels pending deletion.

---

POST

/profile/hide

Hide profile.

---

POST

/profile/show

Show profile again.

---

# MEDIA MODULE

POST

/media/photo

Upload photo.

Validation

JPEG

JPG

WEBP

Maximum 6 photos.

---

DELETE

/media/photo/:id

Delete photo.

---

PATCH

/media/photo/order

Reorder gallery.

---

POST

/media/video

Upload video.

Validation

MP4

Maximum 10 sec.

Maximum one video.

---

DELETE

/media/video

Delete video.

---

# DISCOVERY MODULE

GET

/discovery

Returns

Next profile.

Applies filters.

Applies priority algorithm.

---

POST

/discovery/reset

Restarts discovery queue.

Previously rejected profiles become available.

---

# LIKE MODULE

POST

/likes

Send like.

Consumes one daily like.

---

POST

/likes/message

Send Message Like.

Consumes one daily like.

Stores message.

---

GET

/likes

Returns users who liked current user.

---

POST

/likes/:userId/accept

Creates Match.

---

POST

/likes/:userId/reject

Reject incoming like.

---

# MATCH MODULE

GET

/matches

Returns

Current matches.

---

GET

/matches/:id

Returns

Match details.

Telegram username.

Creation date.

---

# FILTER MODULE

GET

/filters

Returns

Current filters.

---

PATCH

/filters

Updates filters.

---

POST

/filters/reset

Reset filters.

---

# LOCATION MODULE

GET

/cities

City search.

Supports pagination.

Search query.

---

POST

/location

Update GPS.

GPS is optional.

---

# INTEREST MODULE

GET

/interests

Returns all available interests.

---

# REPORT MODULE

POST

/reports

Create report.

Reasons

Spam

Scammer

Fake

Maximum

3/day.

---

GET

/reports/reasons

Returns available reasons.

---

# SETTINGS MODULE

GET

/settings

Returns user settings.

---

PATCH

/settings/theme

Updates theme.

Light

Dark

---

# NOTIFICATION MODULE

GET

/notifications

Returns notification history.

---

POST

/notifications/read

Marks notifications as read.

---

# SYSTEM MODULE

GET

/health

Health check.

---

GET

/version

Returns backend version.

---

# ADMIN AUTH

POST

/admin/login

Login

---

POST

/admin/logout

Logout

---

GET

/admin/me

Returns administrator.

---

# ADMIN USERS

GET

/admin/users

User list.

Supports filtering.

Pagination.

Sorting.

---

GET

/admin/users/:id

User details.

---

PATCH

/admin/users/:id

Edit profile.

---

POST

/admin/users/:id/ban

Ban user.

---

POST

/admin/users/:id/unban

Unban user.

---

# ADMIN REPORTS

GET

/admin/reports

Report queue.

---

GET

/admin/reports/:id

Report details.

---

POST

/admin/reports/:id/approve

Approve report.

---

POST

/admin/reports/:id/reject

Reject report.

---

# ADMIN BROADCAST

POST

/admin/broadcast

Create broadcast.

---

GET

/admin/broadcasts

Broadcast history.

---

DELETE

/admin/broadcast/:id

Delete draft.

---

# ADMIN STATISTICS

GET

/admin/statistics

Returns

Users

Online

Likes

Matches

Reports

Registrations

Activity

---

# ADMIN CITIES

GET

/admin/cities

POST

/admin/cities

PATCH

/admin/cities/:id

DELETE

/admin/cities/:id

---

# ADMIN INTERESTS

GET

/admin/interests

POST

/admin/interests

PATCH

/admin/interests/:id

DELETE

/admin/interests/:id

---

# RATE LIMITS

Login

10/minute

Profile Update

30/hour

Like

100/day

Report

3/day

Media Upload

20/hour

Broadcast

Admin only

---

# VALIDATION

Every endpoint must use:

DTO

class-validator

class-transformer

ValidationPipe

---

# DOCUMENTATION

Swagger/OpenAPI must be generated automatically.

Every endpoint requires:

Description

Parameters

Responses

Examples

Validation rules

Authentication requirements.

---

# SECURITY

Every protected endpoint requires JWT.

Every request validates Telegram InitData on initial authentication.

Input sanitization required.

SQL Injection protection required.

XSS protection required.

Rate limiting enabled.

CORS configurable.

Helmet enabled.

Compression enabled.

Logging enabled.

---

# DEFINITION OF DONE

The API is considered complete only when:

- Every endpoint is implemented.
- Every endpoint is documented.
- Every endpoint is tested.
- Swagger is generated.
- Validation is implemented.
- Authentication works.
- Authorization works.
- Error handling is standardized.
- Logging is implemented.
- Rate limiting is implemented.
- No placeholder endpoints exist.

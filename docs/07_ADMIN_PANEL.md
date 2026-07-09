# ADMIN PANEL

Version: 1.0

---

# PURPOSE

The Admin Panel is a standalone web application for administrators and moderators.

It must provide complete management of the dating platform without requiring direct database access.

Framework:

React

TypeScript

The Admin Panel communicates only with the Backend API.

No direct database connections are allowed.

---

# ACCESS

Authentication:

Username

Password

JWT Session

HTTPS only.

---

# USER ROLES

Administrator

Full access.

Moderator

Limited access.

Permissions must be role-based.

Every action is validated by the backend.

---

# ADMIN LAYOUT

Persistent Sidebar

↓

Top Navigation Bar

↓

Workspace

↓

Responsive Tables

↓

Action Drawers

↓

Dialogs

---

# SIDEBAR

Dashboard

Users

Reports

Broadcasts

Cities

Interests

Statistics

Audit Log

Settings

Logout

---

# LOGIN PAGE

Fields

Username

Password

Remember Session

Button

Login

Validation

Invalid credentials

Locked account

Network error

---

# DASHBOARD

Widgets

Total Users

Online Users

Profiles Hidden

New Registrations Today

Likes Today

Matches Today

Reports Pending

Reports Processed

Broadcast Status

System Status

Quick Actions

Recent Activity

Recent Reports

Recent Registrations

---

# USERS

Purpose

Manage all user accounts.

Table Columns

Avatar

Name

Username

Telegram ID

Gender

Age

City

Relationship Goal

Online

Hidden

Registration Date

Last Seen

Actions

---

# USER SEARCH

Search by

Name

Username

Telegram ID

City

---

# USER FILTERS

Gender

City

Relationship Goal

Online

Hidden

Deleted

Registration Date

Age Range

---

# USER DETAILS

General Information

Photos

Video

About

Interests

Profile Metadata

Reports

Likes Received

Matches

Activity

Current Status

---

# USER ACTIONS

View

Edit

Hide

Unhide

Ban

Unban

Delete

Restore

---

# REPORTS

Purpose

Moderate reported profiles.

Table Columns

Reported User

Reporter

Reason

Status

Created

Moderator

Actions

---

# REPORT DETAILS

Reported Profile

Reporter Profile

Reason

Report History

Screenshots (future)

Moderator Notes

Decision

---

# REPORT ACTIONS

Approve

Reject

Ban User

Hide Profile

Request Review (future)

---

# BROADCASTS

Purpose

Send Telegram notifications.

Fields

Title

Message

Audience

Schedule

Status

---

# BROADCAST TARGETS

All Users

Online Users

Offline Users

Hidden Profiles

Specific City

Specific Gender

Specific Age Range

---

# BROADCAST HISTORY

Status

Created

Sent

Failed

Recipients

Delivery Rate

---

# CITIES

Purpose

Manage city database.

Columns

Name

Region

Population

Coordinates

Status

Actions

---

# CITY ACTIONS

Create

Edit

Disable

Delete

Search

---

# INTERESTS

Purpose

Manage predefined interests.

Columns

Icon

Name

Sort Order

Status

Actions

---

# INTEREST ACTIONS

Create

Edit

Disable

Delete

Reorder

---

# STATISTICS

Charts

Registrations

Online Users

Daily Likes

Daily Matches

Reports

Retention

Growth

---

# ANALYTICS

Top Cities

Top Interests

Gender Distribution

Age Distribution

Relationship Goals

Average Likes

Average Matches

Most Active Hours

---

# AUDIT LOG

Every administrator action must be recorded.

Columns

Administrator

Action

Entity

Target

Date

IP Address

---

# SETTINGS

Application Name

Maintenance Mode

Registration Enabled

Maximum Likes Per Day

Maximum Reports Per Day

Maximum Photos

Maximum Videos

Maximum Video Duration

Allowed Image Formats

Allowed Video Formats

Default Theme

Future Feature Flags

---

# SYSTEM STATUS

Backend

Database

Redis

Storage

Telegram Bot

Disk Usage

Memory Usage

CPU Usage

Application Version

---

# UI REQUIREMENTS

Responsive Design

Dark Theme

Light Theme

Search Everywhere

Pagination

Sorting

Filtering

Bulk Actions

Confirmation Dialogs

Animated Tables

Skeleton Loading

Toast Notifications

---

# TABLE REQUIREMENTS

Server-side Pagination

Column Sorting

Multi-selection

Sticky Header

Search

Filtering

Row Actions

Export (future)

---

# SEARCH

Instant Search

Debounced Requests

Highlight Matches

No Full Page Reloads

---

# FORMS

Client Validation

Server Validation

Error Messages

Success Messages

Unsaved Changes Warning

---

# NOTIFICATIONS

Success

Warning

Error

Information

Auto Dismiss

Manual Close

---

# SECURITY

JWT Authentication

Role-based Authorization

HTTPS Only

CSRF Protection

Rate Limiting

Audit Logging

Automatic Session Expiration

---

# PERFORMANCE

Lazy Loading

Code Splitting

Virtualized Tables

Request Caching

Optimistic Updates Where Safe

Minimal Re-rendering

---

# ACCESSIBILITY

Keyboard Navigation

Visible Focus States

Screen Reader Support

Minimum Touch Target

Semantic HTML

---

# DEFINITION OF DONE

The Admin Panel is considered complete only when:

- Every page is implemented.
- Every action communicates through the Backend API.
- Role-based permissions are enforced.
- Audit logging is implemented.
- Dashboard statistics are functional.
- Reports can be fully moderated.
- Users can be fully managed.
- Broadcasts can be created and sent.
- Settings are configurable.
- No placeholder pages exist.
- No TODO or FIXME comments exist.
- The application builds successfully without errors.

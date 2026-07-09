# DATABASE SCHEMA

Version: 1.0

---

# PURPOSE

This document defines the complete database structure.

Database:

PostgreSQL

ORM:

Prisma

Every entity described here must have a corresponding Prisma model.

---

# GENERAL REQUIREMENTS

Primary Key:

UUID v7

Timestamps:

createdAt

updatedAt

Soft Delete:

deletedAt (where applicable)

All timestamps stored in UTC.

---

# MAIN ENTITIES

- User
- UserSettings
- UserLocation
- UserMedia
- UserInterest
- Interest
- City
- Like
- Match
- Report
- Notification
- UserSession
- Admin
- Broadcast
- AuditLog

---

# USER

Stores the primary profile.

Fields:

id

telegramId

telegramUsername

firstName

gender

birthDate

age

bio

height

education

job

zodiac

smoking

alcohol

children

relationshipGoal

cityId

gpsLatitude

gpsLongitude

gpsUpdatedAt

isGpsEnabled

isHidden

isOnline

lastSeen

profileCompleted

avatarId

videoId

likesToday

reportsToday

lastLikeReset

lastReportReset

createdAt

updatedAt

deletedAt

---

Constraints

telegramId UNIQUE

telegramUsername UNIQUE

Minimum age validation handled by backend.

Username is required.

---

# USER SETTINGS

One-to-one relation.

Fields

id

userId

theme

createdAt

updatedAt

---

# USER LOCATION

Optional GPS information.

Fields

id

userId

latitude

longitude

accuracy

updatedAt

Only latest position is stored.

History is not stored.

---

# USER MEDIA

Stores every uploaded file.

Fields

id

userId

type

orderIndex

path

thumbnailPath

mimeType

size

width

height

duration

isPrimary

createdAt

UpdatedAt

Rules

3–6 photos.

Maximum 1 video.

Video duration <=10 sec.

---

# CITY

Russian cities.

Fields

id

name

region

latitude

longitude

population

createdAt

Indexes

name

region

---

# INTEREST

Reference table.

Fields

id

title

icon

sortOrder

isActive

Approximately:

50–100 records.

---

# USER INTEREST

Many-to-many relation.

Fields

userId

interestId

Maximum:

10 interests per user.

---

# LIKE

Represents one user liking another.

Fields

id

fromUserId

toUserId

message

createdAt

Rules

One active like per pair.

Like cannot be revoked.

Message optional.

---

# MATCH

Created automatically.

Fields

id

user1Id

user2Id

createdAt

Rules

Created only after mutual like.

Unique pair.

---

# REPORT

Fields

id

reporterId

reportedUserId

reason

status

createdAt

processedAt

processedBy

Allowed reasons

Spam

Scammer

Fake

Statuses

Pending

Approved

Rejected

---

# NOTIFICATION

Stores notification history.

Fields

id

userId

type

payload

sent

sentAt

createdAt

Notification Types

New Like

New Match

Moderation

Broadcast

---

# USER SESSION

Stores active Mini App sessions.

Fields

id

userId

ip

userAgent

device

lastActivity

expiresAt

createdAt

---

# ADMIN

Administrator accounts.

Fields

id

username

passwordHash

role

isActive

lastLogin

createdAt

Roles

Administrator

Moderator

---

# BROADCAST

Admin broadcasts.

Fields

id

title

message

status

createdAt

sentAt

createdBy

Statuses

Draft

Scheduled

Sent

Cancelled

---

# AUDIT LOG

Stores administrative actions.

Fields

id

adminId

action

entity

entityId

payload

createdAt

Every admin action must be logged.

---

# RELATIONSHIPS

User

↓

UserSettings

1:1

---

User

↓

UserLocation

1:1

---

User

↓

UserMedia

1:N

---

User

↓

Like

1:N

---

User

↓

Match

N:N

---

User

↓

Report

1:N

---

User

↓

Notification

1:N

---

User

↓

UserInterest

N:N

---

City

↓

User

1:N

---

Interest

↓

UserInterest

1:N

---

Admin

↓

AuditLog

1:N

---

# INDEXES

Create indexes for:

telegramId

telegramUsername

cityId

isOnline

lastSeen

relationshipGoal

gender

createdAt

fromUserId

toUserId

status

reason

---

# UNIQUE CONSTRAINTS

telegramId

telegramUsername

Like(fromUserId,toUserId)

Match(user1Id,user2Id)

UserInterest(userId,interestId)

---

# CASCADE RULES

Deleting User

↓

Delete

Settings

Media

Sessions

Notifications

UserInterests

Likes

Reports

Matches

Soft delete where business logic requires.

---

# FILE STORAGE

Media files are stored on server filesystem.

Database stores only metadata.

Media folders

/uploads/photos

/uploads/videos

/uploads/thumbnails

Storage service must be abstracted for future S3 compatibility.

---

# FUTURE TABLES

Reserved for future versions.

Premium

Subscription

Story

StoryView

VideoCall

Verification

AI Moderation

Push Token

Country

Language

Device

Conversation

Message

Payment

These tables must not affect current architecture.

---

# PRISMA REQUIREMENTS

Every entity must have:

Proper relations

Indexes

Unique constraints

Cascade rules

Validation comments

Enums instead of string literals where appropriate.

Schema must be fully compatible with PostgreSQL.

Database migrations must be reproducible.

Database must initialize using:

Prisma Migrate

Prisma Seed

without manual intervention.

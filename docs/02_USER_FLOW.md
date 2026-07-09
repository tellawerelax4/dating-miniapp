# USER FLOW

Version: 1.0

---

# PURPOSE

This document describes every user interaction with the application.

Every flow defined here is mandatory.

The implementation must not deviate from these flows unless explicitly overridden by future documentation.

---

# APPLICATION FLOW

Application Launch

↓

Telegram Authorization

↓

Validate Telegram InitData

↓

Load User

↓

Check Username

↓

Check Registration

↓

If profile incomplete → Registration Flow

↓

If profile complete → Home

---

# FIRST LAUNCH

User opens Mini App.

↓

Application validates Telegram authorization.

↓

Application verifies Telegram username.

IF username is missing:

Display blocking screen.

Explain why username is required.

Provide button:

"I've added a username"

↓

Recheck username.

↓

Continue only after username exists.

---

# REGISTRATION FLOW

Registration consists of mandatory steps.

User cannot skip any required step.

---

Step 1

Basic Information

Required:

• Name

• Gender

• Birth Date

↓

Continue

---

Step 2

City Selection

Search field

Russian cities database

Select city

↓

Continue

---

Step 3

Media Upload

Upload photos

Minimum:

3

Maximum:

6

Upload optional video

Maximum:

1

Maximum duration:

10 seconds

↓

Continue

---

Step 4

Profile Information

About Me

Height

Education

Job

Smoking

Alcohol

Children

Relationship Goal

Interests

↓

Finish

↓

Registration Complete

---

# HOME FLOW

Application opens Swipe Screen.

Current profile loads.

Display:

Photos

Video

Distance

City

Online status

Profile information

Actions

---

# SWIPE FLOW

Available actions:

Like

Reject

Like with Message

Report

---

LIKE

Tap Like

↓

Consume one daily like

↓

Load next profile

---

LIKE WITH MESSAGE

Tap Message icon

↓

Open modal

↓

Enter message

↓

Send

↓

Consume one daily like

↓

Store message

↓

Load next profile

---

REJECT

Tap Reject

↓

Load next profile

Rejected profiles may appear again in future discovery sessions.

---

REPORT

Tap Report

↓

Open reasons

Spam

Scammer

Fake

↓

Submit

↓

Show confirmation

If daily limit exceeded:

Display warning.

Do not create report.

---

# DISCOVERY END

No profiles available.

↓

Display Empty State.

Message:

"No more profiles available."

↓

Button:

"Start Again"

↓

Discovery restarts.

Previously rejected profiles become available again.

Previously liked profiles remain excluded.

---

# LIKES FLOW

Bottom Navigation

↓

Likes

↓

Display only users that liked current user.

Each card includes:

Photos

Video

Profile

Message (if provided)

↓

User chooses:

Like back

Reject

---

LIKE BACK

↓

Create Match

↓

Notify both users

↓

Move conversation to Matches

---

REJECT

↓

Dismiss card

↓

No Match

Profile may appear again later in Discovery.

---

# MATCH FLOW

Mutual Like

↓

Create Match

↓

Store Match

↓

Send Telegram notification

↓

Both users receive:

Telegram username

↓

Open Telegram profile

↓

Continue communication in Telegram

No internal chat exists.

---

# PROFILE FLOW

Bottom Navigation

↓

Profile

↓

View profile

↓

Edit profile

↓

Save

↓

Return

---

PROFILE EDIT

Editable:

Photos

Video

About

Height

Education

Job

Children

Smoking

Alcohol

Interests

Relationship Goal

City

Everything updates immediately.

---

# HIDE PROFILE

Profile

↓

Hide Profile

↓

Profile removed from Discovery.

Likes and Matches remain accessible.

↓

User can enable profile again anytime.

---

# DELETE ACCOUNT

Profile

↓

Delete Account

↓

Confirmation dialog

↓

Account becomes inactive.

↓

Deletion scheduled.

↓

30-day countdown begins.

↓

If restored:

Cancel deletion.

↓

Otherwise:

Permanent deletion.

---

# SETTINGS FLOW

Bottom Navigation

↓

Settings

↓

Theme

Light

Dark

↓

Save instantly.

No additional settings exist.

---

# FILTER FLOW

Discovery

↓

Filters

↓

Gender

↓

Relationship Goal

↓

Interests

↓

City

↓

Radius

↓

Online

↓

Apply

↓

Reload Discovery.

---

# ONLINE FLOW

Mini App opened

↓

User status:

Online

↓

Mini App closed

↓

Save timestamp

↓

Display:

Last seen

---

# NOTIFICATION FLOW

Events:

New Like

↓

Telegram Bot message

---

New Match

↓

Telegram Bot message

---

Moderation Result

↓

Telegram Bot message

---

# ADMIN MODERATION FLOW

Administrator opens panel

↓

Reports

↓

Open profile

↓

Review

↓

Decision

Approve

Reject

Ban

↓

Notify user if required.

---

# ERROR FLOW

Network Error

↓

Display Retry button.

↓

Retry request.

---

Server Error

↓

Display friendly error.

↓

Allow retry.

---

Unauthorized

↓

Restart authorization.

---

# EMPTY STATES

No profiles

No likes

No matches

No search results

No reports

Every empty state must contain:

Illustration

Short explanation

Primary action button.

---

# LOADING STATES

Every screen must support:

Skeleton loading

Image placeholders

Lazy loading

Progress indicators

No blank screens are allowed.

---

# SUCCESS STATES

Every successful action must provide visual feedback.

Examples:

Profile saved

Like sent

Match created

Report submitted

Theme changed

Profile hidden

Account deletion requested

Feedback should be animated and non-blocking.

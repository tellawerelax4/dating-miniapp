# PRODUCT REQUIREMENTS

Version: 1.0

---

# 1. PRODUCT OVERVIEW

## Project Name

(TBD)

---

## Product Type

Telegram Mini Apps Dating Platform.

---

## Product Goal

Create a completely free dating platform inside Telegram Mini Apps that combines:

- DaiVinchik simplicity
- VK Dating usability
- Modern UI/UX
- Fast performance
- Native Telegram integration

The application must feel like a native mobile application rather than a website.

---

# 2. TARGET AUDIENCE

Primary Region:

Russia

Architecture must support future worldwide expansion.

Primary Language:

Russian

The project must support internationalization (i18n) from the beginning.

---

Age:

14+

No premium functionality.

No paid subscriptions.

No advertisements.

---

# 3. CORE PRINCIPLES

The product must be:

- free
- fast
- intuitive
- modern
- responsive
- beautiful
- secure
- scalable

Every feature should require the minimum number of user actions.

---

# 4. PLATFORM

The application consists of:

- Telegram Mini App
- Telegram Bot
- Backend API
- Admin Panel

Users interact only with the Mini App and Telegram Bot.

---

# 5. USER AUTHORIZATION

Authorization uses Telegram Mini Apps.

Telegram ID is the primary identifier.

Registration is impossible without Telegram authorization.

---

# 6. USERNAME REQUIREMENT

Telegram @username is mandatory.

Before registration:

Check whether username exists.

If username is missing:

Registration is blocked.

Display instructions explaining that a username is required for communication after a match.

Username is automatically checked and updated every Mini App launch.

---

# 7. PROFILE CREATION

A user cannot use the application before completing profile creation.

Required fields:

- Name
- Gender
- Birth date
- City
- At least 3 photos
- About Me

Optional fields:

- Height
- Education
- Job
- Zodiac sign
- Smoking
- Alcohol
- Children
- Relationship goal
- Interests
- One video

---

# 8. GENDER

Available values:

- Male
- Female

---

# 9. SEARCH PREFERENCE

User chooses:

- Men
- Women
- Everyone

---

# 10. RELATIONSHIP GOALS

Available values:

- Serious relationship
- Casual relationship
- Friendship

---

# 11. INTERESTS

Users choose predefined interests.

Custom interests are not allowed.

Maximum selected interests:

10

The application stores a predefined catalog containing approximately 50–100 interests.

---

# 12. PROFILE MEDIA

Photos:

Minimum:

3

Maximum:

6

Allowed formats:

JPEG

JPG

WEBP

Images are automatically compressed to Full HD quality.

Users may:

- reorder photos
- replace photos
- delete photos

Video:

Maximum:

1

Format:

MP4

Maximum duration:

10 seconds

Video autoplay is enabled.

---

# 13. LOCATION

Users manually choose their city from the Russian cities database.

GPS permission is optional.

GPS is used only to calculate distance.

If GPS permission is denied:

Matching works using city only.

---

# 14. DISCOVERY

Users browse profiles using swipe cards.

Actions:

Like

Reject

Like with message

Report

---

# 15. DAILY LIMITS

Likes:

100/day

Message Likes:

Share the same daily limit.

Reports:

Maximum:

3/day

---

# 16. MESSAGE LIKE

Instead of Super Like the application provides Message Like.

The user writes a short message.

Sending a message automatically counts as a Like.

The message appears above the profile description inside the Likes screen.

---

# 17. MATCHES

A Match occurs when two users Like each other.

After a Match:

Both users receive:

Telegram notification

Each user receives the other user's Telegram username.

No internal chat exists.

Communication continues in Telegram.

---

# 18. SWIPE LOGIC

Profiles are prioritized by:

1. Same city
2. Online users
3. Nearest users (GPS)
4. Remaining users

If there are no more available profiles:

Display an empty state.

Offer to restart profile discovery.

Previously rejected profiles may appear again during future discovery sessions.

Likes cannot be cancelled.

---

# 19. FILTERS

Available filters:

City

Radius

Gender

Relationship goal

Interests

Online status

Radius values:

5 km

10 km

15 km

20 km

Distances are rounded down.

---

# 20. ONLINE STATUS

Online:

Mini App currently open.

Offline:

Display last seen timestamp.

---

# 21. NOTIFICATIONS

Telegram Bot sends notifications for:

New Like

New Match

Moderation result

No in-app push notification system is required.

---

# 22. PROFILE VISIBILITY

Users may hide their profile.

Hidden profiles are excluded from discovery.

The profile owner retains access to the application.

---

# 23. ACCOUNT DELETION

Users may request account deletion.

Deletion process:

Profile becomes inactive immediately.

Permanent deletion occurs after 30 days.

---

# 24. REPORTS

Available report reasons:

Spam

Scammer

Fake profile

After exceeding the daily report limit:

Display an informational message.

The report button remains visible.

---

# 25. MODERATION

Automatic moderation is planned for a future version.

Current version includes only administrator moderation.

---

# 26. THEMES

Supported themes:

Light

Dark

Users may switch themes manually.

---

# 27. ANIMATIONS

Animations must be smooth.

Examples:

Card transitions

Image transitions

Screen transitions

Skeleton loading

Micro interactions

Bottom Sheet animations

Swipe animations

Page transitions

All animations should feel native.

---

# 28. ADMIN PANEL

The project includes a complete web administration panel.

Administrators can:

Manage users

Manage reports

Moderate profiles

View statistics

Send broadcasts

Manage cities

Manage interests

Manage relationship goals

Configure application settings

---

# 29. SCALABILITY

The architecture must support future implementation of:

Premium

AI moderation

Stories

Push notifications

Voice and video calls

Additional countries

Additional languages

Cloud storage

CDN

Without requiring major architectural changes.

---

# 30. SUCCESS CRITERIA

The project is considered complete when:

All documented functionality is implemented.

The application is production-ready.

The entire project builds successfully.

Documentation is complete.

No placeholder functionality exists.

No required feature has been omitted.

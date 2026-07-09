# ALGORITHMS

Version: 1.0

---

# PURPOSE

This document defines the core business algorithms of the application.

These algorithms are mandatory.

---

# DISCOVERY ALGORITHM

Priority:

1. Same city
2. Online users
3. Shortest distance
4. Recently active
5. Randomization inside equal priority

Exclude:

- Hidden profiles
- Deleted profiles
- Already liked profiles
- Current user
- Banned users

Rejected profiles may appear again only after discovery queue reset.

---

# MATCH ALGORITHM

User A likes User B

↓

Check if User B already liked User A

↓

If yes

Create Match

Store Match

Notify both users

Return Telegram usernames

↓

If no

Store Like only

---

# MESSAGE LIKE

Message Like is a normal Like with an attached message.

Consumes one daily like.

Message is displayed above the profile description.

---

# DAILY LIMIT RESET

Every day at 00:00 (server time)

↓

Reset:

likesToday

reportsToday

---

# ONLINE STATUS

Mini App opened

↓

Heartbeat every 30 seconds

↓

User = Online

↓

No heartbeat for 60 seconds

↓

User = Offline

↓

Store Last Seen

---

# DISTANCE

If GPS exists:

Calculate distance using Haversine Formula.

Display:

5 km

10 km

15 km

20 km

...

Round down to nearest 5 km.

If GPS unavailable:

Display only city.

---

# PROFILE QUEUE

Discovery queue generated on demand.

Never preload thousands of profiles.

Pagination required.

---

# REPORTS

Maximum:

3 reports/day

After limit:

Button remains active.

Backend rejects request.

Frontend displays warning.

---

# MEDIA

Maximum:

6 photos

1 video

Video <=10 sec

Images compressed to Full HD.

---

# NOTIFICATIONS

Events:

Like

Match

Moderation

Broadcast

Notifications sent through Telegram Bot only.

---

# ACCOUNT DELETION

Delete requested

↓

Profile hidden

↓

30-day timer

↓

Permanent deletion

↓

Cancelable before expiration.

---

# FUTURE

Algorithms must remain modular.

Future ranking or AI recommendations must replace only algorithm modules without changing overall architecture.

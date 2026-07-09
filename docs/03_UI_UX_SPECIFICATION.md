# UI / UX SPECIFICATION

Version: 1.0

---

# PURPOSE

This document defines every application screen, navigation rule, UI component, interaction pattern and animation.

The final implementation must visually match the Figma project.

The application must feel like a native mobile application.

---

# DESIGN PRINCIPLES

The interface must be:

- Minimal
- Modern
- Clean
- Fast
- Responsive
- Accessible
- Consistent

Navigation depth should always be minimal.

The user must reach any major feature in no more than two taps.

---

# NAVIGATION

Bottom Navigation contains 5 sections.

1. Discover
2. Likes
3. Matches
4. Profile
5. Settings

Bottom Navigation is always visible except during onboarding.

---

# SCREEN 1

## Splash Screen

Purpose:

Application initialization.

Contains:

- Logo
- Loading animation

Actions:

None.

---

# SCREEN 2

## Username Required

Shown only if Telegram username is missing.

Contains:

Title

Description

Illustration

Primary button

"I've added a username"

Button triggers username validation.

Navigation is blocked until validation succeeds.

---

# SCREEN 3

## Registration

Multi-step wizard.

Progress indicator always visible.

Steps:

Basic Info

↓

City

↓

Media

↓

Profile

↓

Finish

User cannot skip required fields.

---

# SCREEN 4

## Discover

Main application screen.

Contains:

Profile Card

Bottom Actions

Top Bar

---

Top Bar

Contains:

Application Logo

Filter Button

---

Profile Card

Contains:

Media Gallery

Indicators

Name

Age

City

Distance

Online Status

Optional Message

About

Interests

Additional Information

Profile content scrolls vertically.

Media remains fixed until user changes image.

---

Bottom Actions

Reject

Message

Like

Buttons remain fixed.

---

# PROFILE CARD

Displays:

Photos

Video

Indicators

Name

Age

Online

Distance

City

About

Height

Education

Job

Smoking

Alcohol

Children

Relationship Goal

Interests

Report Button

---

Photos

Swipe horizontally.

Tap opens fullscreen viewer.

---

Video

Autoplay

Muted by default

Loops continuously

---

Message Block

Visible only if sender used Message Like.

Position:

Above About section.

Styled differently from profile description.

---

About Block

Expandable.

Supports multiline text.

---

Interest Chips

Maximum:

10

Scrollable.

---

# SCREEN 5

## Filters

Presented as Bottom Sheet.

Contains:

Gender

Relationship Goal

City

Radius

Interests

Online

Buttons:

Apply

Reset

---

# SCREEN 6

## Likes

Displays users who liked current user.

Card layout identical to Discover.

Buttons:

Reject

Like Back

---

If message exists:

Display message above profile description.

---

# SCREEN 7

## Matches

Displays all active matches.

Each item contains:

Avatar

Name

Age

Last Seen

Telegram Username

Primary Button:

Open Telegram

---

# SCREEN 8

## Profile

Editable profile.

Sections:

Media

Basic Information

About

Additional Information

Interests

Danger Zone

---

Danger Zone

Hide Profile

Delete Account

---

# SCREEN 9

## Settings

Contains only:

Theme

Light

Dark

Switch applies instantly.

---

# SCREEN 10

## Empty Discover

Illustration

Title

Description

Primary Button

Start Again

---

# SCREEN 11

## Empty Likes

Illustration

Description

---

# SCREEN 12

## Empty Matches

Illustration

Description

---

# SCREEN 13

## Loading

Every screen supports:

Skeleton

Image Placeholder

Progress Indicator

No white screens.

---

# SCREEN 14

## Error

Contains:

Illustration

Title

Description

Retry Button

---

# DIALOGS

Delete Account

Hide Profile

Report

Message Like

Confirmation

All dialogs use Bottom Sheet.

No browser alerts.

---

# REPORT DIALOG

Reasons:

Spam

Scammer

Fake Profile

Submit

Cancel

---

# MESSAGE LIKE DIALOG

Text Input

Character Counter

Send

Cancel

Message length defined by backend configuration.

---

# PHOTO VIEWER

Fullscreen

Swipe

Zoom

Close

Supports all uploaded photos.

---

# VIDEO PLAYER

Fullscreen

Play

Pause

Replay

Mute

---

# ANIMATIONS

Required:

Screen Transition

Bottom Sheet

Modal

Swipe

Card Rotation

Image Fade

Button Press

Like Animation

Match Animation

Loading Skeleton

Empty State

Theme Transition

All animations use 60 FPS where possible.

---

# GESTURES

Horizontal Swipe

Vertical Scroll

Tap

Long Press (future)

Pull To Refresh

---

# MICRO INTERACTIONS

Button Scale

Card Elevation

Ripple

Opacity Transition

Animated Counters

Animated Chips

Animated Progress

---

# HAPTIC FEEDBACK

Supported actions:

Like

Reject

Match

Report

Delete

Hide Profile

Theme Change

---

# RESPONSIVE DESIGN

Support:

Small phones

Standard phones

Large phones

Tablet compatibility is optional.

---

# ACCESSIBILITY

Minimum touch target:

44x44 px

Readable typography

Proper contrast

Visible focus states

Semantic HTML

Keyboard accessibility where applicable.

---

# PERFORMANCE

Lazy loading

Image preloading

Video lazy loading

Virtualized lists

Optimized animations

Minimal re-rendering

---

# DESIGN CONSISTENCY

Every screen must follow the same:

Spacing

Typography

Corner radius

Shadow

Animation timing

Iconography

Interaction rules

No screen may introduce a different visual language.

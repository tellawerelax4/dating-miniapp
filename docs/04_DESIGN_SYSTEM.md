# DESIGN SYSTEM

Version: 1.0

---

# PURPOSE

This document defines the complete design language of the application.

Every screen, component and animation must follow this design system.

No visual element may be implemented outside of this specification.

---

# DESIGN PHILOSOPHY

The application should feel like a premium native mobile application.

Design inspiration:

- VK Dating
- Telegram
- iOS Human Interface Guidelines
- Material Design 3

The interface must not copy any existing product.

Only UX ideas may be reused.

---

# DESIGN PRINCIPLES

The UI must be:

- Minimal
- Soft
- Modern
- Elegant
- Fast
- Friendly
- Consistent

Avoid visual clutter.

Avoid unnecessary gradients.

Avoid oversized elements.

Whitespace is a design element.

---

# COLOR SYSTEM

The application supports two themes.

Light Theme

Dark Theme

All colors must be implemented using design tokens.

Hardcoded colors are prohibited.

---

# COLOR TOKENS

Primary

Primary Hover

Primary Active

Secondary

Accent

Success

Warning

Danger

Background

Surface

Surface Elevated

Border

Divider

Text Primary

Text Secondary

Text Tertiary

Placeholder

Disabled

Overlay

Skeleton

---

# TYPOGRAPHY

Single font family.

Modern sans-serif.

Support:

Latin

Cyrillic

Required styles:

Display

Heading Large

Heading Medium

Heading Small

Body Large

Body Medium

Body Small

Caption

Label

Button

---

# GRID

Use an 8px spacing system.

Allowed spacing:

4

8

12

16

20

24

32

40

48

64

---

# BORDER RADIUS

Use consistent corner radius.

Small

Medium

Large

Extra Large

Full

---

# SHADOWS

Three elevation levels.

Low

Medium

High

Use soft shadows.

Dark theme uses reduced shadow opacity.

---

# ICONOGRAPHY

Single icon library.

Outlined style.

Rounded corners preferred.

Icons must have consistent stroke width.

---

# BUTTONS

Types:

Primary

Secondary

Ghost

Danger

Icon Button

Floating Action Button (future)

States:

Default

Hover

Pressed

Disabled

Loading

---

# INPUTS

Text Input

Textarea

Search

Select

Date Picker

Segmented Control

Radio

Checkbox

Switch

Character Counter

Validation Message

States:

Default

Focused

Error

Success

Disabled

---

# CARDS

Profile Card

Match Card

Like Card

Statistic Card

Admin Card

Cards use:

Rounded corners

Soft shadow

Consistent padding

Animated appearance

---

# PROFILE CARD

Contains:

Media

Indicators

Information

Actions

Scrolling Content

Cards must support dynamic content height.

---

# MEDIA

Images

Progress indicators

Fullscreen mode

Zoom

Lazy loading

Video autoplay

Muted by default

---

# CHIPS

Interest Chips

Filter Chips

Selected Chips

Removable Chips

Animated selection.

---

# BADGES

Online

Verified (future)

Moderator

Administrator

Unread

---

# AVATARS

Small

Medium

Large

Extra Large

Circular only.

---

# DIVIDERS

Thin

Inset

Full Width

---

# BOTTOM NAVIGATION

Five items.

Persistent.

Animated selection.

Supports badges.

Safe Area compatible.

---

# APP BAR

Transparent while scrolling.

Solid after scroll threshold.

Supports blur.

---

# BOTTOM SHEETS

Used instead of browser dialogs.

Support:

Drag

Dismiss

Snap Points

Background Blur

---

# DIALOGS

Delete

Hide Profile

Message

Report

Confirmation

Animated appearance.

---

# LISTS

Virtualized.

Animated insert/remove.

Support pull-to-refresh.

---

# EMPTY STATES

Every empty state contains:

Illustration

Title

Description

Primary Action

No generic placeholders.

---

# LOADING

Skeleton Components:

Avatar

Text

Image

Card

List

Profile

Never display blank pages.

---

# ERROR STATES

Friendly illustration.

Human-readable message.

Retry action.

---

# NOTIFICATIONS

Snackbars

Toast Messages

Success

Warning

Error

Info

Auto dismiss.

---

# MOTION

Animation duration:

Fast

Normal

Slow

Use spring animations where appropriate.

Avoid abrupt transitions.

---

# PAGE TRANSITIONS

Fade

Slide

Shared Element (where applicable)

Theme Transition

Bottom Sheet Transition

---

# SWIPE ANIMATION

Reject:

Card rotates left.

Like:

Card rotates right.

Message Like:

Card rotates right with highlighted animation.

Animation must be smooth.

---

# MATCH ANIMATION

Full-screen celebration.

Soft particles.

Scale animation.

No excessive visual effects.

---

# MICRO INTERACTIONS

Buttons

Inputs

Cards

Switches

Chips

Navigation

Theme

Image Gallery

Every interaction provides visual feedback.

---

# HAPTICS

Support Telegram Mini Apps haptic feedback.

Light

Medium

Heavy

Selection

Notification

Use only where meaningful.

---

# RESPONSIVENESS

Layouts must adapt to:

Small devices

Medium devices

Large phones

Foldables (future-ready)

Safe areas must always be respected.

---

# ACCESSIBILITY

Minimum touch area:

44x44 px

Readable contrast.

Semantic elements.

Visible focus.

Support reduced motion if available.

---

# FIGMA REQUIREMENTS

The generated Figma project must contain:

Design System

Variables

Color Tokens

Typography Styles

Spacing Tokens

Corner Radius Tokens

Elevation Tokens

Auto Layout

Component Variants

Interactive Components

Responsive Constraints

Prototype Connections

Dark Theme

Light Theme

Developer-ready naming conventions.

---

# COMPONENT LIBRARY

Every reusable component must exist in Figma before implementation.

No duplicated components.

No detached instances.

All components must use variants whenever possible.

---

# IMPLEMENTATION REQUIREMENT

Frontend implementation must match Figma pixel-perfect.

No visual deviations are allowed unless explicitly documented.

Design System is the single source of truth for every UI component.

# CallMode
A context-aware Android call management app that silences non-urgent calls, sends automatic responses, and detects urgency through repeat-call logic.

Context-Aware Call Management System for Android

Overview

Smart Call Focus is an Android application designed to improve productivity and reduce unwanted interruptions by introducing context-based call management with urgency detection.

The application allows users to activate predefined modes such as Sleep, Driving, or Focus. When a mode is active, incoming calls are automatically handled through intelligent logic that balances interruption control with accessibility for urgent communication.

Problem Statement

Modern smartphone users frequently experience interruptions from non-urgent phone calls, including spam, customer service calls, and low-priority personal calls. Existing solutions such as Silent Mode and Do Not Disturb (DND) provide binary control:

Either allow all calls

Or silence all calls

These systems lack intelligent urgency differentiation and contextual communication.

There is no lightweight Android solution that simultaneously:

Silences non-urgent calls

Automatically informs callers of the user’s status

Detects urgency through repeat-call behavior

Overrides silence intelligently when necessary

Smart Call Focus addresses this gap.

Solution

Smart Call Focus introduces a context-aware call management mechanism with two core components:

Mode-Based Auto Response

Repeat-Call Urgency Detection

When a user activates a mode:

Incoming calls are silenced.

A predefined SMS is automatically sent to the caller.

If the same number calls again within 5 minutes, the system treats the call as urgent and allows it to ring normally.

This creates a balance between focus protection and critical accessibility.

Key Features

Manual Mode Selection (Sleep, Driving, Focus)

Automatic SMS response to incoming calls

Call silencing during active mode

Repeat-call detection within a configurable time window

Intelligent urgency override logic

Lightweight and minimal UI

How It Works

User activates a mode.

App listens for incoming calls using BroadcastReceiver and TelephonyManager.

On call detection:

Check if mode is active.

If active, send predefined SMS.

Silence ringtone.

Store caller number and timestamp.

If the same caller calls again within 5 minutes:

Allow call to ring normally.

Skip silencing.

Technical Architecture
Technologies Used

Kotlin

Android Studio

BroadcastReceiver

TelephonyManager

SmsManager

SharedPreferences

Permissions Required

READ_PHONE_STATE

SEND_SMS

RECEIVE_BOOT_COMPLETED

MODIFY_AUDIO_SETTINGS

The application follows Android’s runtime permission model.

Call Handling Logic Flow

Incoming Call
→ Check Mode Status
→ If Mode Active
→ Check Repeat Call History
→ If Repeat Within 5 Minutes
→ Allow Ring
→ Else
→ Silence + Send SMS
→ If Mode Not Active
→ Default Behavior

Installation

Clone the repository.

Open the project in Android Studio.

Grant required permissions when prompted.

Run on a physical Android device (recommended).

Note: Due to Android restrictions on SMS and call handling, testing on a real device is strongly recommended.

Limitations

Android policy restrictions on SMS and call monitoring.

Background execution limits in newer Android versions.

Manufacturer-specific battery optimization policies.

Requires runtime permissions for call and SMS handling.

Future Scope

This repository represents the MVP (Minimum Viable Product). Enhancements such as advanced scheduling, analytics, and intelligent prioritization can be explored separately.

-------------------------------

Developed an Android-based context-aware call management system implementing urgency detection using repeat-call threshold logic, enabling intelligent interruption control while preserving accessibility for critical communication.

License

This project is intended for educational and portfolio purposes.

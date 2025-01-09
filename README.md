# Expo Linking.addEventListener Inconsistency on Android

This repository demonstrates a bug in Expo's `Linking` API where the `Linking.addEventListener` for deep links is unreliable, particularly on Android. The issue lies in the inconsistent triggering of the event listener, leading to missed deep links.

## Problem

The `Linking.addEventListener` function is expected to trigger whenever a deep link is opened, regardless of whether the app is in the background or foreground. However, this is not always the case, especially on Android. The listener may fail to register, be prematurely removed, or simply not fire when a deep link is opened.

## Solution

The proposed solution includes improved handling of listener registration, ensuring it remains active across app states, and implementing fallback mechanisms to handle potential event misses.  It also provides more robust error handling.  The solution utilizes a combination of event listeners and a periodic check for initial URLs.
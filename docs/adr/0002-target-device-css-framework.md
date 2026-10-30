# ADR 002: Target Device and CSS Framework

**Status:** Accepted  
**Date:** 30th October 2026  
**Author:** Tofunmi Olutimehin

## Context

The assignment identifies Android as the default target device and Bootstrap as the default CSS framework, although the team is allowed to change these decisions.

Study Buddy must run on Android, and the chosen styling approach should work effectively with the React Native framework.

## Options Considered

### Target Device

**Android**

**Pros:**
- Required by the project guidelines
- Can be tested using Android devices or an emulator
- Works well with React Native

**Cons:**
- Does not prioritize iOS-specific testing

**iOS**

**Pros:**
- Supported by React Native
- Provides access to iPhone users

**Cons:**
- Not required for this project
- Would add extra testing requirements

**Android and iOS**

**Pros:**
- Provides broader compatibility

**Cons:**
- Increases testing and development effort
- Adds unnecessary scope for this course project

### Styling Approach

**Bootstrap**

**Pros:**
- Familiar from web development
- Provides predefined styling classes

**Cons:**
- Standard Bootstrap is designed for HTML and CSS
- It does not work directly with React Native components

**React Native StyleSheet**

**Pros:**
- Built directly into React Native
- Works naturally with native components
- No extra styling dependency is required

**Cons:**
- Styles must be created and maintained manually

**React Native UI or Styling Libraries**

**Pros:**
- Can provide reusable components and predefined styles

**Cons:**
- Adds extra dependencies
- May introduce additional learning for the team

## Decision

**Target Device:** Android

**Styling Approach:** React Native `StyleSheet`

## Rationale

Android will remain the target platform because the project guidelines require the application to run on Android.

React Native `StyleSheet` is a better fit for the chosen development framework than standard Bootstrap because React Native does not use traditional HTML and CSS elements. Using `StyleSheet` also keeps the project simple and avoids adding an unnecessary styling library.

## Consequences

The team only needs to prioritize Android testing, which reduces the amount of cross-platform testing required.

Using React Native `StyleSheet` keeps the styling approach compatible with React Native and avoids extra dependencies. However, the team will need to create and maintain the application's styles manually instead of relying on predefined Bootstrap classes.
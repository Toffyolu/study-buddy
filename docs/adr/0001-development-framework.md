# ADR 001: Development Framework

**Status:** Accepted  
**Date:** 30th October 2026  
**Author:** Tofunmi Olutimehin

## Context

Study Buddy requires a development framework that supports Android mobile development and allows the team to build features such as task management, reminders, student profiles, and study-partner matching.

The team has experience working with JavaScript, TypeScript, React, and React Native through coursework. The chosen framework should make use of those existing skills and be realistic to implement within the course timeline.

## Options Considered

### React Native
**Language:** JavaScript / TypeScript / React

**Pros:**
- Familiar to the team
- Supports Android development
- Works well with Expo and React Navigation
- Supports reusable components

**Cons:**
- Some native features may require additional packages

### Ionic
**Language:** HTML / CSS / JavaScript

**Pros:**
- Uses familiar web technologies
- Supports cross-platform development

**Cons:**
- Would require the team to learn a different development workflow

### Cordova
**Language:** HTML / CSS / JavaScript

**Pros:**
- Uses familiar web technologies

**Cons:**
- Relies heavily on plugins for native functionality
- Less suitable for the team's current React Native experience

### Framework7
**Language:** HTML / CSS / JavaScript

**Pros:**
- Provides ready-made mobile UI components

**Cons:**
- Less familiar to the team
- Would introduce additional learning

### NativeScript
**Language:** JavaScript / TypeScript

**Pros:**
- Supports native mobile development

**Cons:**
- The team has less experience with NativeScript

## Decision

We will use **React Native** as the development framework.

## Rationale

React Native fits the team's current skills and the course timeline because the team already has experience using React Native, JavaScript, TypeScript, and Expo. It supports Android development and provides access to libraries that can be used for navigation, notifications, storage, and reusable interface components.

This reduces the amount of new technology the team needs to learn and allows more time to focus on building Study Buddy's features.

## Consequences

Using React Native should make development faster because the team can reuse skills learned in class and create reusable components throughout the application.

Expo and other React Native packages will need to be installed and configured during the building phase. Some native functionality may require additional packages, but these should remain within the scope of the course.
# Survive Game Project

## Introduction
The **Survive Game** is a mobile game project assigned as part of a mobile security course. The goal is to reverse engineer the APK provided, fix any bugs, and uncover the logic that leads to successfully surviving and reaching the player's city. The game requires entering a valid ID, which determines the steps needed to navigate and win the game.

---

## Setup Instructions

### Step 1: APK Decompilation
- Utilize decompilation tools (e.g., JADX or APKTool) to extract the APK's resources and code.
- Analyze the following components from the decompiled APK:
  - **Manifest File:** Provides critical app information such as permissions and entry points.
  - **Source Code:** Reveals Java files and game logic for handling user input and gameplay.
  - **Resources:** Includes UI layouts (`res/layout`), drawable assets (`res/drawable`), and string resources (`res/values`).

### Step 2: Key Activities
1. **Activity_Menu:** Manages the ID input and serves as the launcher activity.
2. **Activity_Game:** Handles the core gameplay, navigation logic, and interactions.

---

## Debugging and Enhancements

### Identifying Issues
- **Bugs Detected:**
  - Incorrect toast messages in `Activity_Game`.
  - Errors in integer parsing for ID logic.
  - Broken external URL references in code.

### Fixes Implemented
1. **Improved Toast Messages:**
   - Updated success and failure messages to enhance clarity:
     ```java
     Toast.makeText(this, "You reached the city: " + cityName, Toast.LENGTH_SHORT).show();
     ```

2. **Corrected Integer Parsing Logic:**
   - Fixed ID-to-navigation step logic:
     ```java
     stepsArray[i] = Integer.parseInt(String.valueOf(id.charAt(i))) % 4;
     ```

3. **URL Fixes:**
   - Replaced the outdated URL with a functional one:
     ```java
     private static final String URL = "https://pastebin.com/raw/T67TVJG9";
     ```

---


## Example Gameplay

### Input and Steps
1. **Example ID:** `315006254`
2. **Derived Navigation Steps:**
   - **3 → Down**
   - **1 → Right**
   - **5 → Right**
   - **0 → Left**
   - **0 → Left**
   - **6 → Up**
   - **2 → Up**
   - **5 → Right**
   - **4 → Left**

### Steps to Follow
1. Enter the example ID at the start screen.
2. Follow the navigation prompts (`Down`, `Right`, `Left`, etc.) to reach your city.

---
### Video

https://github.com/user-attachments/assets/c4a867a1-d319-4daa-91bb-cd6474dfe1bf

## The state I reached is Pennsylvania.

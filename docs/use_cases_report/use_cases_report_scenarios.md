# Step-by-Step Interaction Through Code Components

## Scenario: User Logs In and Changes Company Number

### Step 1: User Logs into the System

**User Action:**
1. User enters login credentials and logs into the system.

**System Response:**
1. The system authenticates the user and verifies permissions.

### Step 2: System Retrieves User Data

**System Action:**
1. The system calls program `DSB002` to get user data from the user control file and place it in the LDA.

**Source Files Involved:**
- `DSB002` (ProgramLogic): Retrieves user data from the `BUUSERS` file.
- `BUUSERS` (PhysicalFile): Contains user control data.

**Behavior:**
- `DSB002` reads the `BUUSERS` file to fetch user-specific data.
- The retrieved data is placed in the Local Data Area (LDA).

### Step 3: System Displays Main Menu

**System Action:**
1. The system calls program `MNU003` with parameters `OUTQ`, `FRMENU`, and `TOMENU` to display the main menu.

**Source Files Involved:**
- `MNU003` (ProgramLogic): Handles the display of the main menu.
- `MNU003DSP` (DisplayFile): Contains the display attributes and record formats for the main menu.

**Behavior:**
- `MNU003` uses the data in the LDA to determine the user's profile and permissions.
- `MNU003DSP` is used to render the main menu on the screen with options based on the user's profile.

### Step 4: User Changes Company Number

**User Action:**
1. User presses `F11` to change the company number.

**System Response:**
1. The system calls program `MNU010` to handle the change of the company number.

**Source Files Involved:**
- `MNU010` (ProgramLogic): Manages the change of the company number.
- `MNU010DSP` (DisplayFile): Contains the display attributes and record formats for changing the company number.

**Behavior:**
- `MNU010` updates the company number in the LDA based on user input.
- `MNU010DSP` is used to display the interface for changing the company number.

### Step 5: System Updates Company Number

**System Action:**
1. The system updates the company number in the LDA.

**Source Files Involved:**
- `LDA` (DataStructures): Local Data Area where the company number is stored.

**Behavior:**
- The new company number is validated and updated in the LDA.

### Step 6: User Selects a Menu Option

**User Action:**
1. User selects a menu option from the main menu.

**System Response:**
1. The system evaluates the selected option.

**Source Files Involved:**
- `MNU003` (ProgramLogic): Evaluates the selected menu option.

**Behavior:**
- `MNU003` checks if the selected option is valid and if the user has the necessary permissions.

### Step 7: System Executes Menu Option

**System Action:**
1. If the option is valid, the system executes the selected menu option.

**Source Files Involved:**
- Appropriate program or command based on the selected option.

**Behavior:**
- The system calls the appropriate program or command to execute the selected menu option.

### Step 8: System Tracks Menu Option Usage

**System Action:**
1. The system captures the details of the selected option and writes a record to the `MNUUSG` file to track the usage.

**Source Files Involved:**
- `MNUUSG` (PhysicalFile): File to track menu option usage.

**Behavior:**
- The system logs the menu option usage details in the `MNUUSG` file for tracking purposes.

### Summary

This step-by-step interaction describes the flow of a user logging into the system, changing the company number, and selecting a menu option. The interaction involves multiple programs (`DSB002`, `MNU003`, `MNU010`), display files (`MNU003DSP`, `MNU010DSP`), and data structures (LDA, `MNUUSG`). Each step is linked to the corresponding use case and source files, providing a comprehensive view of the system's behavior.
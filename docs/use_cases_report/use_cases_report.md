# Functional System Use Cases

## Use Case 1: Display Main Menu

**Description**

Display the main menu with options based on the BUNZL menu system.

**Primary Actor**

User

**Preconditions**

- User is logged into the system.
- User has the necessary permissions to access the menu.

**Main Flow**

1. User logs into the system.
2. The system calls program `DSB002` to get user data from the user control file and place it in the LDA.
3. The system calls program `MNU003` with parameters `OUTQ`, `FRMENU`, and `TOMENU`.
4. The main menu is displayed with options based on the user's profile and permissions.

**Postconditions**

- The main menu is displayed with the correct options for the user.

**Extends or Includes**

- Includes: `DSB002` to get user data.
- Includes: `MNU003` to display the menu.

---

## Use Case 2: Change Company Number

**Description**

Allow users to change the company number.

**Primary Actor**

User

**Preconditions**

- User is logged into the system.
- User is on the main menu screen.

**Main Flow**

1. User presses `F11` to change the company number.
2. The system calls program `MNU010` to handle the change.
3. The system updates the company number in the LDA.

**Postconditions**

- The company number is updated in the LDA.

**Extends or Includes**

- Includes: `MNU010` to handle the change of company number.

---

## Use Case 3: Display Error Message

**Description**

Display an error message when an invalid option is selected.

**Primary Actor**

User

**Preconditions**

- User is logged into the system.
- User is on the main menu screen.

**Main Flow**

1. User selects an invalid option from the menu.
2. The system evaluates the option and determines it is invalid.
3. The system calls program `UT0500` to display the error message.

**Postconditions**

- An error message is displayed to the user.

**Extends or Includes**

- Includes: `UT0500` to display the error message.

---

## Use Case 4: Load Subfile Page

**Description**

Load a page of the subfile with menu options.

**Primary Actor**

User

**Preconditions**

- User is logged into the system.
- User is on the main menu screen.

**Main Flow**

1. User navigates through the menu options.
2. The system loads a page of the subfile with the next set of menu options.
3. The system displays the loaded page to the user.

**Postconditions**

- A new page of menu options is displayed to the user.

**Extends or Includes**

- None

---

## Use Case 5: Execute Menu Option

**Description**

Execute a selected menu option.

**Primary Actor**

User

**Preconditions**

- User is logged into the system.
- User is on the main menu screen.

**Main Flow**

1. User selects a menu option.
2. The system evaluates the selected option.
3. If the option is valid and the user has the necessary permissions, the system executes the option.
4. The system calls the appropriate program or command based on the selected option.

**Postconditions**

- The selected menu option is executed.

**Extends or Includes**

- None

---

## Use Case 6: Track Menu Option Usage

**Description**

Track the usage of menu options by users.

**Primary Actor**

System

**Preconditions**

- User is logged into the system.
- User selects a menu option.

**Main Flow**

1. User selects a menu option.
2. The system captures the details of the selected option.
3. The system writes a record to the `MNUUSG` file to track the usage.

**Postconditions**

- The usage of the menu option is tracked in the `MNUUSG` file.

**Extends or Includes**

- None

---

## Use Case 7: Display Handheld Menu

**Description**

Display a cut-down version of the menu for handheld devices.

**Primary Actor**

User

**Preconditions**

- User is logged into the system.
- User is accessing the system from a handheld device.

**Main Flow**

1. User logs into the system from a handheld device.
2. The system detects the device type.
3. The system displays a cut-down version of the menu suitable for handheld devices.

**Postconditions**

- A cut-down version of the menu is displayed on the handheld device.

**Extends or Includes**

- None

---

## Use Case 8: Add User Data to LDA

**Description**

Get user data from the user control file and place it in the LDA.

**Primary Actor**

System

**Preconditions**

- User is logged into the system.

**Main Flow**

1. The system calls program `DSB002`.
2. The system retrieves user data from the `BUUSERS` file.
3. The system places the retrieved data in the LDA.

**Postconditions**

- User data is placed in the LDA.

**Extends or Includes**

- Includes: `DSB002` to get user data.

---

## Use Case 9: Display Inquiry Menu Options

**Description**

Allow users access to inquiry menu options.

**Primary Actor**

User

**Preconditions**

- User is logged into the system.
- User has the necessary permissions for inquiry options.

**Main Flow**

1. User logs into the system.
2. The system checks the `SCINQUSR` file to determine if the user has inquiry permissions.
3. The system displays the inquiry menu options to the user.

**Postconditions**

- Inquiry menu options are displayed to the user.

**Extends or Includes**

- None

---

## Use Case 10: Display Help Screen

**Description**

Display a help screen for the current menu.

**Primary Actor**

User

**Preconditions**

- User is logged into the system.
- User is on the main menu screen.

**Main Flow**

1. User presses `F13` to display the help screen.
2. The system calls program `UT0303` to display the help screen.
3. The help screen is displayed to the user.

**Postconditions**

- The help screen is displayed to the user.

**Extends or Includes**

- Includes: `UT0303` to display the help screen.

---

## Use Case 11: Change Output Queue

**Description**

Change the output queue for printing.

**Primary Actor**

User

**Preconditions**

- User is logged into the system.
- User is on the main menu screen.

**Main Flow**

1. User enters a new output queue.
2. The system validates the new output queue.
3. If valid, the system updates the output queue.
4. The system changes the job's output queue to the new value.

**Postconditions**

- The output queue is updated.

**Extends or Includes**

- None
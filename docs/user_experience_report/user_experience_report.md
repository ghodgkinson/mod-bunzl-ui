### User Experience Model for AS400 Menu System

#### 1. Screen: Main Menu (MNU003)
**Screen Components:**
- **@CO#**: Company Number (Position: 1, 6)
- **@LOCN**: Location (Position: 1, 9)
- **@TITLE**: Menu Title (Position: 1, 13)
- **@MENU**: Menu Name (Position: 2, 38)
- **@MSG**: Message Area (Position: 4, 58)
- **@OPTION#**: Option Number (Position: 5, 2)
- **@ODESC**: Option Description (Position: 5, 7)
- **@SLCTOP**: Selected Option (Position: 21, 10)
- **@OUTQ**: Printer Output Queue (Position: 21, 67)
- **@F3MSG**: F3 Key Message (Position: 22, 2)
- **@F12MSG**: F12 Key Message (Position: 23, 47)
- **Command Keys**: F2, F3, F4, F5, F6, F7, F9, F11, F12, F15

**Navigation Flow:**
1. **Initial Display**: The main menu is displayed with options for the user to select.
2. **Option Selection**: User enters an option number in the `@SLCTOP` field and presses Enter.
3. **F3 Key**: Returns to the initial menu.
4. **F4 Key**: Opens a search function.
5. **F5 Key**: Opens settings.
6. **F6 Key**: Opens messages.
7. **F7 Key**: Opens jobs.
8. **F9 Key**: Opens output.
9. **F11 Key**: Allows changing the company number.
10. **F12 Key**: Cancels the current operation.
11. **F15 Key**: Edits menu data.

#### 2. Screen: Handheld Menu (MNU003C2)
**Screen Components:**
- **@CO#**: Company Number (Position: 1, 6)
- **@LOCN**: Location (Position: 1, 9)
- **@TITLE**: Menu Title (Position: 1, 13)
- **@MENU**: Menu Name (Position: 2, 8)
- **@SLCTOP**: Selected Option (Position: 14, 7)
- **@OUTQ**: Printer Output Queue (Position: 14, 47)
- **@F3MSG**: F3 Key Message (Position: 16, 2)
- **@F12MSG**: F12 Key Message (Position: 17, 47)
- **Command Keys**: F3, F4, F5, F6, F7, F9, F11, F12, F15

**Navigation Flow:**
1. **Initial Display**: The handheld menu is displayed with options for the user to select.
2. **Option Selection**: User enters an option number in the `@SLCTOP` field and presses Enter.
3. **F3 Key**: Returns to the initial menu.
4. **F4 Key**: Opens a search function.
5. **F5 Key**: Opens settings.
6. **F6 Key**: Opens messages.
7. **F7 Key**: Opens jobs.
8. **F9 Key**: Opens output.
9. **F11 Key**: Allows changing the company number.
10. **F12 Key**: Cancels the current operation.
11. **F15 Key**: Edits menu data.

#### 3. Screen: Error Message Subfile (MNU003SM)
**Screen Components:**
- **ESF_MSGKEY**: Error Message Key
- **@PGMQ**: Program Message Queue

**Navigation Flow:**
1. **Error Display**: When an error occurs, the error message subfile is displayed.
2. **Error Handling**: User acknowledges the error message and takes corrective action.

#### 4. Screen: Menu Settings (MNU004)
**Screen Components:**
- **Settings Fields**: Various fields for configuring menu settings.

**Navigation Flow:**
1. **Access Settings**: User presses F5 from the main menu to access settings.
2. **Modify Settings**: User modifies the settings as needed.
3. **Save and Exit**: User saves the changes and exits back to the main menu.

#### 5. Screen: Change Company/Location (MNU010)
**Screen Components:**
- **Company Number**: Field to enter the new company number.
- **Location**: Field to enter the new location.

**Navigation Flow:**
1. **Access Change Company/Location**: User presses F11 from the main menu to access this screen.
2. **Change Details**: User enters the new company number and location.
3. **Save and Exit**: User saves the changes and exits back to the main menu.

#### 6. Screen: Help Screen (UT0303)
**Screen Components:**
- **Help Text**: Various fields displaying help information.

**Navigation Flow:**
1. **Access Help**: User presses F13 from the main menu to access the help screen.
2. **View Help**: User views the help information.
3. **Exit Help**: User exits the help screen and returns to the main menu.

### Summary
The AS400 menu system provides a structured and navigable interface for users to interact with various menu options, settings, and error handling. The main menu serves as the central hub, with additional screens for handheld devices, error messages, settings, company/location changes, and help information. Users can navigate between these screens using function keys and menu options, ensuring a seamless and efficient user experience.
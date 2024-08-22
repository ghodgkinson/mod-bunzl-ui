# Overview Analysis of AS400 Source Code

## Files

### DSCOREG (PhysicalFile)
- **Description**: Corporate Company/Region File.
- **Fields**: Includes fields like `CRCO#`, `CRREG`, `CRCNM`, `CRDIV`, `CRIND`, `CREXD`, `CRCNTR`, `CRFL01`, `CRFL02`, `CRREGO`, `CR198O`, `CRMID#`, `CRLANG`, `CRDATF`, `CRARTC`, `CRVERT`, `CRVCO`, `CRSFA`, `CR$CD`, `CRRCY`, `CRHAZT`, `CRCLIB`, `CRRLIB`, `CRBLUM`, `CRBLWF`, `CRRPT`, `CRVIPQL`, `CRIMPF`, `CRBRID`, `CRACTG`, `CRBAPV`, `CRPBYC`, `CRCLNT`, `CRFIPT`, `CRMRCID`, `CRMRCREF`, `CRMRCTKN`, `CRMRCJSK`, `CRHRR`, `CRVRSDT`, `CRCHPCAR`, `CRPNPGRP`, `CRSDTRAR`, `CRSRVLIB`, `CRBCSPOD`, `CRC2FO`, `CRORDACK`, `CRCSTSNT`, `CRLYRADJ`, `CRIDLR`.
- **Keys**: `CRCO#`, `CRREG`.

### BUUSERS (PhysicalFile)
- **Description**: Contains user information from DSUSERS & FIUSERS.
- **Fields**: `USRNAM`, `USRCO#`, `USRLCN`, `USRLCR`, `USRCFL`, `USRLFL`, `USRLFR`, `USRCST`, `USRMCS`, `USRSHL`, `USRMNU`, `USRAUT`, `USFIRC`, `USRC01` to `USRC12`, `USRSIT`, `USRDFL`, `USRRFL`, `USRRGR`, `USXCO#`.
- **Keys**: `USRNAM`.

### BUUSERS1 (LogicalFile)
- **Description**: Logical view of BUUSERS by company number and user name.
- **Keys**: `USRCO#`, `USRNAM`.

### BZUSERS (PhysicalFile)
- **Description**: Contains user, company number, and default company.
- **Fields**: `BZZNAM`, `BZZCO#`, `BZZDFT`, `BZZLCN`, `BZZLCR`.
- **Keys**: `BZZNAM`, `BZZCO#`, `BZZDFT`.

### BZUSERS1 (LogicalFile)
- **Description**: Logical view of BZUSERS by user and default company.
- **Keys**: `BZZNAM`, `BZZDFT`.

### MENUOPT (PhysicalFile)
- **Description**: Bunzl system menu options.
- **Fields**: `MNUPGM`, `MNUOPTION`, `MNUTYPE`, `MNUDESCE`, `MNUDESCF`, `MNUDESCS`, `MNURUNCMD`, `MNUEFFDATE`, `MNUHIDE`, `MNUUPD`, `MNUUSAGE`.
- **Keys**: `MNUPGM`, `MNUOPTION`.

### MNUUSR (PhysicalFile)
- **Description**: Determines if a user is authorized to change generic attention key menu data.
- **Fields**: `MNAUSER`, `MNACHGUSR`, `MNAEDTDTA`, `MNAPGM`, `MNASHAU`, `MNALANG`, `MNAHIDE`, `MNAF11`, `MNACO#`, `MNAPOS`.
- **Keys**: `MNAUSER`, `MNACO#`.

### SCINQUSR (PhysicalFile)
- **Description**: Allows users access to inquiry menu options.
- **Fields**: `SCIICUS`, `SCIIDUS`, `SCIIACT`, `SCIIPGMR`.
- **Keys**: `SCIICUS`, `SCIIACT`.

### SCINQUSR1 (LogicalFile)
- **Description**: Logical view of SCINQUSR by development profile.
- **Keys**: `SCIIDUS`, `SCIIACT`.

### SCDATA (PhysicalFile)
- **Description**: Contains user data and group profile fields for single sign-on.
- **Fields**: `SCNAME`, `SCMENU`, `SCOPT#`, `SCXCO#`, `SCXGRP`, `SCEXPD`, `SCADUS`, `SCADDT`, `SCADTM`, `SCCHUS`, `SCCHDT`, `SCCHTM`, `SCFROM`.
- **Keys**: `SCNAME`, `SCMENU`, `SCOPT#`.

### SCDATA4 (LogicalFile)
- **Description**: Menu authorization file by company number, user, menu, and name.
- **Keys**: `SCXCO#`, `SCNAME`, `SCMENU`, `SCOPT#`.

### MENUOPT1 (LogicalFile)
- **Description**: MENUOPT file by run command, type, and option number.
- **Keys**: `MNURUNCMD`, `MNUTYPE`, `MNUOPTION`.

### MENUJMP (PhysicalFile)
- **Description**: Personal settings for menu.
- **Fields**: `JMUSER`, `JMDATA`.
- **Keys**: `JMUSER`.

### MNUUSG (PhysicalFile)
- **Description**: Menu option usage tracking file.
- **Fields**: `LOGCO#`, `LOGLOC`, `LOGNAM`, `LOGOPT`, `LOGRPT`, `LOGUSR`, `LOGDAT`, `LOGCMD`, `LOGTIMEST`.
- **Keys**: `LOGCO#`, `LOGLOC`, `LOGNAM`, `LOGOPT`, `LOGRPT`, `LOGUSR`, `LOGDAT`.

## CopyBook

### UT0500 (Prototypes)
- **Description**: Prototype for call to error message subfile program.
- **Parameters**: `P_Act`, `P_MsgId`, `P_Msg`, `P_Prog`.

## RPG Programs

### MNU003 (Program)
- **Description**: Replacement program for Bunzl menu system.
- **Modifications**: Includes various modifications for standardization, user selections, error handling, and additional functionalities.
- **Files Used**: `MENUOPT`, `MNUUSR`, `MENUHDR`, `SCINQUSR`, `SCINQUSR1`, `SCDATA4`, `SCDATA1`, `SCDATA`, `MENUOPT1`, `MENUJMP`, `MNUUSG`.
- **Subroutines**: `SFLNEW`, `FindGUAuth`, `SFLLOD`, `DSPLAY`, `ProcessJump`, `ChangeOutQ`, `Sflprc`, `CheckAuth`, `AddToList`, `SubFromList`, `WRITEMSG`, `REMOVEMSG`, `HelpScreen`, `SetJump`, `GETF3DATA`, `FindFromMenu`, `CHECK4RPT`, `GETLDA`.

### DSB002 (Program)
- **Description**: Gets user data from user control file and places it in LDA.
- **Modifications**: Includes modifications for adding flags and replacing files.
- **Files Used**: `BUUSERS1`, `BZUSERS1`, `DSCOREG`.

### UT0500 (Program)
- **Description**: Handles error message subfile program.
- **Subroutines**: `WriteMsg`, `RemoveMsg`.

## Screens

### MNU003FM (DisplayFile)
- **Description**: Displays a generic menu with options based on the Bunzl menu system.
- **Modifications**: Includes modifications for adding menu options, changing command key layout, and removing certain options.
- **Record Formats**: `MNU003S1`, `MNU003C1`, `MNU003M1`, `MNU003SM`, `MNU003CM`, `MNU003S2`, `MNU003C2`, `MNU003M2`.

## CL Program

### MNU003CL (Program)
- **Description**: Calls the DSB002 program to get user data and then calls the MNU003 program.
- **Modifications**: Includes logic to check the number of allowable sign-ons.
- **Variables**: `FRMENU`, `TOMENU`, `OUTQ`, `LIBTHERE`.

## Summary
The provided AS400 source code includes various files, programs, and display files that are part of a system for managing user data, menu options, and error handling. The code is well-documented with comments and modifications, indicating a history of updates and enhancements. The programs interact with multiple files to retrieve and display data, handle user inputs, and manage error messages. The display files define the layout and functionality of the user interface, while the CL program orchestrates the execution of the main programs.
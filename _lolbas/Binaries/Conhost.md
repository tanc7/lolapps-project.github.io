---
Name: Conhost.exe
Description: Console Window host
Author: Wietze Beukema
Created: 2022-04-05
Commands:
  - Command: "conhost.exe calc.exe"
    Description: Execute calc.exe with conhost.exe as parent process
    Usecase: Use conhost.exe as a proxy binary to evade defensive counter-measures
    Category: Execute
    Privileges: User
    MitreID: T1202
    OperatingSystem: Windows 10, Windows 11
Full_Path:
  - Path: c:\windows\system32\conhost.exe
Detection:
  - IOC: conhost.exe spawning unexpected processes
  - Sigma: https://github.com/SigmaHQ/sigma/blob/bea6f18d350d9c9fdc067f93dde0e9b11cc22dc2/rules/windows/process_creation/proc_creation_win_susp_conhost.yml
Resources:
  - Link: https://www.hexacorn.com/blog/2020/05/25/how-to-con-your-host/
  - Link: https://twitter.com/Wietze/status/1511397781159751680
Acknowledgement:
  - Person: Adam
    Handle: '@hexacorn'
  - Person: Wietze
    Handle: '@wietze'
---

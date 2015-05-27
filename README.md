SYNOPSIS

Mapping Generator Tool is a standalone macro script that will generate a XML file with metadata of Informatica Straight Move, SCD Type 1 objects which can be imported to Informatica tool to create these objects automatically.


DESCRIPTION

This script will generate XML file with metadata of Informatica objects (workflow, sources, targets, mappings and sessions). This script will prompt you for source and target database connection credentials and to select the table required to be used as source and target. From there, the script will then prompt you to choose the columns to be mapped from source to target

The mapping functionality will have two modules 
1. Straight Move (If Mapping Type is selected as "Straight Move")
2. SCD Type - 1 (If mapping type is selected as "SCD Type-1")

-----Straight Move--------







from a menu of different attacks, all with different persistence methods. Once an attack is chosen, it will then prompt you for your payload type. Currently, only HTTP and HTTPS are supported.

When naming the document, do not include a file extension.

These attacks use Invoke-Shellcode, which was created by Matt Graeber. Follow him on Twitter --> @mattifestation

ATTACK TYPES

Meterpreter Shell with Logon Persistence: 
This attack delivers a meterpreter shell and then persists in the registry by creating a hidden .vbs file in C:\Users\Public and then creates a registry key in HKCU\Software\Microsoft\Windows NT\CurrentVersion\Windows\Load that will execute the .vbs file on login.
Meterpreter Shell with PowerShell Profile Persistence: 
This attack requires the target user to have Administrator privileges but is quite creative. It will deliver you a shell and then drop a malicious .vbs file in C:\Users\Default\AppData\Roaming\Microsoft\Windows\Cookies\cookie.vbs. Once dropped, it creates an infected PowerShell Profile file in C:\Windows\SysNative\WindowsPowerShell\v1.0\ and then creates a registry key in HKCU\Software\Microsoft\Windows NT\CurrentVersion\Windows\Load that will execute Powershell.exe on startup. Since the PowerShell profile loads automatically when Powershell.exe is invoked, your code is executed automatically.
Meterpreter Shell with Microsoft Outlook Email Persistence: 
This attack will give you a shell and then download a malicious Powershell script to C:\Users\Public\. Once downloaded, it will insert your defined IP address, port, email address and trigger word. It will then create a malicious .vbs file and drop it in C:\Users\Default\AppData\Roaming\Microsoft\Windows\Cookies\. Once dropped, it creates a registry key that executes it on login. When the Powershell script is executed, it monitors the user's Outlook Inbox for an email containing the email address you specified as well as the trigger word in the subject. When it sees the email, it will delete it and send you a shell.
EXAMPLE

PS> ./Generate-Macro.ps1
Enter IP Address: 10.0.0.10
Enter Port Number: 1111
Enter the name of the document (Do not include a file extension): FinancialData

--------Select Attack---------
1. Meterpreter Shell with Logon Persistence
2. Meterpreter Shell with Powershell Profile Persistence (Requires user to be local admin)
3. Meterpreter Shell with Microsoft Outlook Email Persistence
------------------------------
Select Attack Number & Press Enter: 1

--------Select Payload---------
1. Meterpreter Reverse HTTPS
2. Meterpreter Reverse HTTP
------------------------------
Select Payload Number & Press Enter: 1
Saved to file C:\Users\Malware\Desktop\FinancialData.xls


# MappingGeneratorTool
VBScript code implementing Database and Informatica related automation tasks
automates the process of creating Straight Move, SCD Type 1 Informatica objects workflow, sources, targets, mappings and sessions with all the project standards, followed. The output of the tool is xml file, which on import to repository generates all the Informatica artifacts to the project folders. This tool helps in reducing the development time considering any number of columns. This is developed using Excel VBA.

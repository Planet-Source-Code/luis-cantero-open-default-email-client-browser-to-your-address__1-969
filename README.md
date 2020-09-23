<div align="center">

## Open default email client/browser to your address


</div>

### Description

Sometimes in the about box of your program you want to put your email address, and web site address, wouldn't it be great if at one click the default email client would open with your address in it?, or the default web browser to your address?, and a plus!, open any file to its association, all of this with no declarations, no APIs, and with ONE line of code? Sounds impossible? here's how:
 
### More Info
 
Email address or Web site address or File name to open with path.

Returns nothing, the good thing, it doesn't generate errors, if an association is not found it does nothing, just stays quiet, instead of crying "ERROR!, I don't know what to do!".


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Luis Cantero](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/luis-cantero.md)
**Level**          |Beginner
**User Rating**    |5.0 (5 globes from 1 user)
**Compatibility**  |VB 4\.0 \(32\-bit\), VB 5\.0, VB 6\.0
**Category**       |[Internet/ HTML](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/internet-html__1-34.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/luis-cantero-open-default-email-client-browser-to-your-address__1-969/archive/master.zip)





### Source Code

```
'Instead of writing declarations and everything to open a web browser to your page try this:
Shell "Start.exe " & "www.LCen.com", 0
'The program start.exe executes the shell for any program in windows95, try this:
Shell Start.exe " & "mailto:dummydummy111@dummyserver.com", 0
'The line above will open the default mail client with your address on it, also:
Shell "Start.exe " & "mailto:abcd@usa.com?Subject=Hello", 0
'With the subject "Hello" already filled.
'The following line will open an html file with the default browser:
Shell "Start.exe " & "c:\hellopage.htm", 0
'If you have a program with a filelist box, try this to open the shell of a file with a double click event:
Shell "Start.exe " & """" & Filelist1.Path & Filelist1 & """", 0
'Or try this, specially for WinNT (2000/XP, etc.):
Shell "Explorer.exe " & "www.LCen.com", 0
'The possibilities are endless, have fun!
<BR>
'Start.exe however doesn't work on WinNt/2000/XP, so use the following API which will always work:
Private Declare Function ShellExecute Lib "shell32" Alias "ShellExecuteA" (ByVal hWnd As Long, ByVal lpOperation As String, ByVal lpFile As String, ByVal lpParameters As String, ByVal lpDirectory As String, ByVal nShowCmd As Long) As Long
'Sample call:
ShellExecute hWnd, vbNullString, "mailto:dummydummy111@dummyserver.com?body=hello%0a%0world", vbNullString, vbNullString, vbNormalFocus
'In order to be able to put carriage returns or tabs in your text, replace vbCrLf and vbTab with the following HEX codes:
%0a%0d = vbCrLf
%09 = vbTab
'These codes also work when sending URLs to a browser (GET, POST, etc.)
'Luis Cantero
L.C. Enterprises
http://LCen.com
```


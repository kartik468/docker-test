

reference urla: 
https://github.com/martinlindhe/wmi_exporter#installation

https://docs.microsoft.com/en-gb/windows/win32/msi/command-line-options?redirectedfrom=MSDN

https://www.advancedinstaller.com/user-guide/msiexec.html


## WMI
Windows Management Instrumentation (WMI) is a set of specifications from Microsoft for consolidating the management of devices and applications in a network from Windows computing systems. WMI provides users with information about the status of local or remote computer systems.

Windows Management Instrumentation consists of a set of extensions to the Windows Driver Model that provides an operating system interface through which instrumented components provide information and notification. 

## wmi_exporter
Each release provides a .msi installer. The installer will setup the WMI Exporter as a Windows service, as well as create an exception in the Windows Firewall.

download url:
https://github.com/martinlindhe/wmi_exporter/releases

default port: 9182


install exporter with msiexec: 

```
msiexec /i "C:\IAG\wmi_exporter-0.11.1-amd64.msi"
```
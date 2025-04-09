<h1>Perform System Configuration Gap Analysis</h1>

<h2>Description</h2>
Identify the differences in configuration between Windows Server 2019 client "PC10" and a Microsoft security baseline template.
<br>
<br>
I used security templates to manage a Windows Server configuration, which included using the Microsoft Policy Analyzer to perform a security baseline template review and gap analysis.
<br/>

<h2>Tools and Languages Used</h2>

- <b>PowerShell</b> 
- <b>Microsoft Policy Analyzer</b>
- <b>Microsoft Security Compliance Toolkit 1.0</b>

<h2>Environments Used </h2>

- <b>Windows Server 2019</b> (1809)

<h2>Steps Taken:</h2>

<p align="center">
Using winver command, I noted the Windows Server 2019 version number was 1809 and the OS Build number 17763.4377: <br/>
<img src="https://i.imgur.com/cUDwlCi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
I retrieved the Policy Analyzer and Windows 10 Version 1809 and Windows Server 2019 Security Baseline.zip from 
the Microsoft Security Compliance Toolkit 1.0. 
<br />
<br />
  I copied the contents to C:\LABFILES from the disk it was saved to:
<img src="https://i.imgur.com/JnnAvr3.png" height="80%" width="80%"/>
<br />
<br />
Within Powershell, I extracted the folder contents with: Expand-Archive -Path PolicyAnalyzer.zip and Expand-Archive -Path "Windows 10 Version 1809 and Windows Server 2019 Security Baseline.zip". 
<br />
<br />
Then executed C:\LABFILES\PolicyAnalyzer\PolicyAnalyzer_40\PolicyAnalyzer.exe to run the application: <br/>
<img src="https://i.imgur.com/y1AzkR7.png" height="80%" width="80%"/>
<br />
<br />
Set Policy Rules sets in to: Windows 10 Version 1809 and Windows Server 2019 Security Baseline\Documentation
<br />
<br />
Selected 'MSFT-Win10-v1809-RS5-WS2019-FINAL' to view/compare:  <br/>
<img src="https://i.imgur.com/e3yRZLn.png" height="80%" width="80%"/>
<br />
<br />
At the bottom of the viewer, I noted LockoutBadCount was set to 10 and MinimumPasswordLength was set to 14.:  <br/>
<img src="https://i.imgur.com/A9mNcwu.png" height="80%" width="80%"/>
<br />
<br />
From there, I ran "Compare to effective State" to perform a gap analysis between the baseline security template file and the current in-use values of the local operating system.
<br />
<br />
Many items were highlighted in yellow, indicating differences in baseline vs effective policies. 
<br />
<br />
The Effective state value of LockoutBadCount is 0, and MinimumPasswordLength is 7, making the PC10 system not in compliance with the security template.
:  <br/>
<img src="https://i.imgur.com/uDB6fzO.png" height="80%" width="80%"/>
<br />
<br />
  From here we can adjust the configuration based on the organization's particular security goals and scope. 
</p>

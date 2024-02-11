<h1>Digital Forensics</h1>


<h2>Description</h2>

The target of this challenge is to analyze the content of an image of the user’s hard drive to find any evidence of malicious activity. There are 4 pieces of hidden information where each piece of evidence will contain the string like {1 of 4} or similar. I have been told that the most recent file on the hard-drive was an email file with an attachment in the “Saved Emails” directory. So the starting point should be that directory. For all four evidences, I need to find the following answers:


 - <b> What is the name of the file where the evidence was found? (filename and extension)</b>
 - <b> What is the name of the directory where this evidence was found?</b>
 - <b> What piece of evidence have you found?</b>
 

<h2>Skills Achieved</h2>

  - <b> Linux CLI navigation</b>
  - <b> Identifying incorrect file extensions</b>
  - <b> Identifying hidden files/folders</b>
  - <b> Steganography</b>
  - <b> Password cracking</b>

<h2>Tools/software  Used </h2>

- <b>Kali Linux</b> 
- <b>Challenge disk image (.zip file: J Harrison Disk image 10.09.2019)</b>


<h2>Project walk-through:</h2>

<p align="center">
<br/>
Please check below the image of the disk need to be checked  <br/>
<img src="https://github.com/msislam23/DigitalForensics/assets/157939065/da7d86a7-e4c0-48e8-92a0-4957490a35c7" height="80%" width="80%"/>
<br />
<br />
Evidence 1 of 4:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>

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
As per the above hints, for any zip file with password needs to be investigated. I used kali Linux CLI to navigate different folders and files of the disk image, I found a password protected zip file named “.a0415ns.zip” at /J Harrison Disk Image 10.09.2019/WebDev work/unfinished webpages/to-do and this file name starts with “.” (as suggested in the hints I should check all files including hidden ones as well). So I decided to investigate this file. 


 - <b> First I find out the password using the command: "fcrackzip –D –p /usr/share/wordlist/rockyou.txt –u .a0415ns.zip" </b> <br/> I have used dictionary approach to crack the file using the default rockyou.txt file for finding the password from the list in the text file.<br />
 
 - <b> I used the password to unzip the file and used "ls –a" commad to find all files in the current directory.</b>
 - <b> A new file named employeedump is detected</b>
 - <b> To determine what type of file is the new one, I used "file employeedump" command and it shows the file as text.</b>
 - <b> I renamed the file to a text file using the command "mv employeedump employeedump.txt"</b>
 - <b> Then I used "strings employeedump.txt" command to read the content of the file and which shows our first evidence {Part 1 of 4}</b>
 <br/> This was all employee information.<br />

<img src="https://github.com/msislam23/DigitalForensics/assets/157939065/367c92e3-7c80-4459-b923-908918fd93df"/>
<br />

<p align="center">
<br />
Evidence 2 of 4: <br/>
For evidence two, there are two steps. At first I investigated the saved email folder as per the suggestion in the hint. I have found the clue that the person has hidden the evidence using steganography in a .jpg file and the password to extract that file is “password”. I found this information inside Form1.jpg file inside “Saved Emails” at "/J Harrison Disk Image 10.09.2019/Saved Emails"
<img src="https://github.com/msislam23/DigitalForensics/assets/157939065/3f529930-7ece-4be9-b8da-2f5575924984"/>
<br />
<br />
At the last part I found the following information:  <br/>
<img src="https://github.com/msislam23/DigitalForensics/assets/157939065/20668a3d-5c8f-4cbf-8184-dac525b3f2da"/>
<br />
<br />
Then I navigated through the files and folders. Inside image folder at /J Harrison Disk Image 10.09.2019/Images, I found several images. As image files are used to hide other files using steganography. I used the command “steghide --extract -sf filename.jpg” using password “password” for several jpg files to extract hidden file inside. The image laptop.jpg returned a text file named passwords. And after extracting the content of the text file, I found my second piece of evidence {2/4}<br/>
<br />
This shows list of employee passwords<br/>
<img src="https://github.com/msislam23/DigitalForensics/assets/157939065/986c9eec-8603-4e51-b75b-92adf25b7ac9"/>
<br />
<br />
Evidence 3 of 4: <br/>
This third evidence was hidden inside a file by changing the file extension inside the directory "/J Harrison Disk Image 10.09.2019/Weekly Meeting Notes/Week 10". I used "file" command in kali Linux to detect the real file type and used "mv" command to change it back to its real file extension to find the evidence. This file was showing as an ".xml" but it was actually an image file. I converted it back to ".jpeg" format to find the evidence. 
<img src="https://github.com/msislam23/DigitalForensics/assets/157939065/b44ab694-f1c0-40a0-b435-071789f04b71"/>
<img src="https://github.com/msislam23/DigitalForensics/assets/157939065/e537e479-fc03-4fba-879b-eaca5c4a45a8"/>
<br />
<br />
And the evidence is: <br/>
<img src="https://github.com/msislam23/DigitalForensics/assets/157939065/e229d5a1-15d1-49ba-a01a-869ac2f5ab25"/>
<br />
This evidence represents office locations<br/>
<br />
<br />
Evidence 4 of 4:<br/>
This was hidden inside the "/J Harrison Disk Image 10.09.2019/WebDev work/unfinished webpages/templatemo_508_power/css".
I used "file" and "strings" commands to find the evidence in kali linux.

<img src="https://github.com/msislam23/DigitalForensics/assets/157939065/a59ee24f-9701-4a85-9ce7-3c992cae3342"/>
<br />
This is personal information of Colin Andrews
<br />
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

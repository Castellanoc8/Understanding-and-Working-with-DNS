<p align="center">
<img src="https://i.imgur.com/aq7snyV.png"/>
</p>


<h1>Building Intuition for DNS</h1>
This tutorial outlines examples of working with DNS.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- DNS
- Command Prompt

<h2>Operating Systems Used</h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>Excercises if working with DNS</h2>

- A-Record Excercise
- Local DNS Cache Excercise
- CNAME Record Excercise


<p>
<img src="https://i.imgur.com/ppFb0W4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/Xp004qH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/cIiqga1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Inside this lab, I worked with the DNS server and did a few different exercises while using it. A brief description of DNS is that it is used to convert computer names like "www.google.com" into IP Addresses, so humans do not have to memorize thousands of different IP Addresses. To begin this exercise, I logged back into both DC-1 and Client-1's Remote Desktops using the "mydomain.com\jane_admin" credentials from the previous lab. Next, I went into Client-1's Remote Desktop and tried ping "mainframe" but it failed. The reason it failed was because there is no DNS record of it yet. So that it would not fail, I had to go into DC-1's Remote Desktop and create an A-Record for "mainframe," and have it point to DC-1's Private IP Address. Once doing so, I went back into Client-1 and did another ping in the command prompt for "mainframe," resulting in the ping being successful this time.
</p>
<br />

<p>
<img src="https://i.imgur.com/bgdrStw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/BMG7hME.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/bhzzHbJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/dQ4bIIl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

In this exercise, I worked with the Local DNS Cache. I started off by going into DC-1 and changing the "mainframes" record address to 8.8.8.8. After doing that, I went back into Client-1 and using the command prompt, I typed "ping mainframe" again, but it still showed the old record address I had previously told it to use. So for it to ping the new record address successfully, I would have to "Flush" the DNS cache using the command "ipconfig/flushdns". Once I "flushed" the DNS cache, I typed "ping mainframe" again, and this time, it was successful in showing the new record address of 8.8.8.8
</p>
<br />

<p>
<img src="https://i.imgur.com/baADbmC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/XItnpiH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/RMoxkJv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

<p>
In this final exercise of working with DNS, I did a few things with the CNAME record this time. First, I returned to DC-1's Remote Desktop and created a new CNAME record that would point the host "search" to "www.google.com." After creating the new CNAME Record, I went into Client-1's Remote Desktop, and in the command prompt, I attempted to ping "search" and observed the results for the CNAME Record. The last thing I did was also type in the command prompt "nslookup search" and observed the results for the CNAME Record, which both ping and nslookup "search" showed "www.google.com" for the CNAME Record.
</p>
<br />

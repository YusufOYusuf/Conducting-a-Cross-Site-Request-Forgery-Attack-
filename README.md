<h1>Exploiting A Website Using SQL Injection </h1>


<h2>Description</h2>
In this lab, I learned to conduct a cross-site request forgery (CSRF) attack. Cross-site request forgery (CSRF) is an attack that takes place against authenticated web applications by using the Cookies. The attacker tricks a victim to make a request which the victim does not want to make.
<br />



<h2>Environments Used </h2>

- <b>Kali GNU/Linux Rolling</b> 

<h2>Utilities and Language </h2>

- <b>DVWA</b>

<h2>Program walk-through:</h2>

<p align="center">
From the left sidebar open Firefox ESR <br/>
<img src="https://i.postimg.cc/cJKxYX9Y/Screen-Shot-2022-12-28-at-4-10-26-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />
  
  
  
  
  
<br />
Type "localhost/dvwa" in the address bar then type in username and password <br/>
<img src="https://i.postimg.cc/BnryYpZ2/Screen-Shot-2022-12-28-at-4-12-56-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />



<br />
Scroll down and select DVWA Security  <br/>
<img src="https://i.postimg.cc/1t5KJVFp/Screen-Shot-2022-12-28-at-4-15-09-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />



<br />
In the DVWA Security window select a "low" security level and then click submit.  <br/>
<img src="https://i.postimg.cc/nVwCs9c6/Screen-Shot-2022-12-28-at-4-19-41-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />




<br />
In the left pane click "CSRF"
<img src="https://i.postimg.cc/sgsw0gtD/Screen-Shot-2022-12-28-at-4-47-57-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />






<br />
In the Vulnerability: cross site request forgery (CSRF) window right click the New password box and select Inspect Element Q:
<img src="https://i.postimg.cc/Gh5vvhd5/Screen-Shot-2022-12-28-at-5-11-39-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />



<br />
In the Inspector tab right-click on the form tag and select Edit As HTML
<img src="https://i.postimg.cc/g23rrYJR/Screen-Shot-2022-12-28-at-5-15-55-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />





<br />
Select all the contents in the form tag and copy it 
<img src="https://i.postimg.cc/7Y2ZQxSc/Screen-Shot-2022-12-28-at-5-18-27-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />





<br />
Close the inpsector tab, minimize the Firefox browser and then open the terminal
<img src="https://i.postimg.cc/59ZCtK3h/Screen-Shot-2022-12-28-at-5-22-45-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />



<br />
In the terminal window type the following commands <br>
cd /var/www/html <br>
touch csrf.php <br>
nano csrf.php <br>
below are the results of these commands <br>
<img src="https://i.postimg.cc/VvjnwX3r/Screen-Shot-2022-12-28-at-5-25-18-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />





<br />
In the csrf.php file paste the copied form content<br>
<img src="https://i.postimg.cc/HsYRN3Gy/Screen-Shot-2022-12-28-at-5-36-30-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />





<br />
Replace the "#" with "http://localhost/dvwa/vulnerabilities/csrf/" <br>
<img src="https://i.postimg.cc/Z5Tpk746/Screen-Shot-2022-12-28-at-5-48-04-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />




<br />
Press CTRL+X and then type y and press enter to save changes<br>
<img src="https://i.postimg.cc/yx0KTyGN/Screen-Shot-2022-12-28-at-5-59-04-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />





<br />
Open a new window and type "localhost/csrf.php" in the address bar and then type a password <br>
<img src="https://i.postimg.cc/JhgWVFVn/Screen-Shot-2022-12-28-at-6-01-54-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />





<br />
In the Vulnerability: cross site request forgery (csrf) window got to the left pane, scroll then logout <br>
<img src="https://i.postimg.cc/Pq00F8Yv/Screen-Shot-2022-12-28-at-6-03-49-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />





<br />
At the login page type in the credential you intially used to get in and you will observe you will NOT be able to log on <br>
<img src="https://i.postimg.cc/Bnkhqf6d/Screen-Shot-2022-12-28-at-6-07-14-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />



<br />
Now try logging in again with the new password that you created and you will observe that it worked<br>
<img src="https://i.postimg.cc/mgjmH1mW/Screen-Shot-2022-12-28-at-6-09-04-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />

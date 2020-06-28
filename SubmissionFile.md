## Week 16 Homework Submission File: Penetration Testing 1

#### Step 1: Google Dorking


- Using Google, can you identify who the Chief Executive Officer of Altoro Mutual is:![image-20200628124103113](Screenshots\image-20200628124103113.png)

- How can this information be helpful to an attacker:

  *This information can be useful to a hacker who can socially engineer for more information given that they know the identity of the individual. A second method is that this information can be used to send user specific phishing attacks.*


#### Step 2: DNS and Domain Discovery

Enter the IP address for `demo.testfire.net` into Domain Dossier and answer the following questions based on the results:

  1. Where is the company located: 

     *The company website says anywhere, Massachusetts but the whois record shows the following:*

     ![image-20200628130935216](Screenshots\image-20200628130935216.png)

  2. What is the NetRange IP address:

     ![image-20200628130324695](Screenshots\image-20200628130324695.png)

  3. What is the company they use to store their infrastructure:

     ![image-20200628131016657](Screenshots\image-20200628131016657.png)

  4. What is the IP address of the DNS server:

     ![image-20200628131042357](Screenshots\image-20200628131042357.png)

#### Step 3: Shodan

- What open ports and running services did Shodan find:

  ![image-20200628131349445](Screenshots\image-20200628131349445.png)

  ![image-20200628131436967](C:\Users\Ilham Buharie\AppData\Roaming\Typora\typora-user-images\image-20200628131436967.png)

#### Step 4: Recon-ng

- Install the Recon module `xssed`. 

  ![image-20200628131804312](Screenshots\image-20200628131804312.png)

  ![image-20200628131842095](Screenshots\image-20200628131842095.png)

  ![image-20200628131918797](Screenshots\image-20200628131918797.png)

- Set the source to `demo.testfire.net`. 

  ![image-20200628132030215](Screenshots\image-20200628132030215.png)

- Run the module. 

Is Altoro Mutual vulnerable to XSS: 

*Yes, Altoro Mutual is vulnerable to cross site scripting. See results below:*

![image-20200628132341938](Screenshots\image-20200628132341938.png)

### Step 5: Zenmap

Your client has asked that you help identify any vulnerabilities with their file-sharing server. Using the Metasploitable machine to act as your client's server, complete the following:

- Command for Zenmap to run a service scan against the Metasploitable machine: 

  *metasploitable machine Ip address is as shown below*

  ![image-20200628133019584](Screenshots\image-20200628133019584.png)

- Bonus command to output results into a new text file named `zenmapscan.txt`:

  ![image-20200628133447781](Screenshots\image-20200628133447781.png)

- Zenmap vulnerability script command:

  I

  ![image-20200628184509421](Screenshots\image-20200628184509421.png)

  *After running the 6 scripts in zenmap against the metasploitable box, the scripts return unsuccessfully because the metasploitable box is running a unix based OS. The samba vulnerabilities particularly affect windows machines.*

- Once you have identified this vulnerability, answer the following questions for your client:
  1. What is the vulnerability:

     - ![](Screenshots\image-20200628190357741.png)

       

     *The vulnerability is against Windows machines running Samba version 1.*

  2. Why is it dangerous: *This vulnerability is dangerous because it leaves the client susceptible to a WannaCry ransomware attack or any other attack that can be propagated through the EternalBlue exploit. The dangers of ransomware are self-explanatory and the client needs to address this with urgency.*

  3. What mitigation strategies can you recommendations for the client to protect their server:

     *The client can do the following to protect themselves from this attack:*

     - *Patch all operating systems especially those running Windows OS, and disable SMB on those machines. If SMB must be used for any reason, only enable SMB on the machines that need it and disable SMVv1 and v2. Force machines to use he latest version of SMB.*
     - *Disable NetBIOS on all the Windows machines.*
     - *Machines running any version of SMB should not be facing the public internet.*
     - *Install firewalls, IPS and IDS on the internet facing portion of the network.*
     - *Segment the network to limit propagation of the ransomware.*
     - *Backup important file storage systems at regular intervals.*

---
© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.  


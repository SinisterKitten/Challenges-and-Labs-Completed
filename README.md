# CTF Walk-Throughs
 * [OverTheWire](#overthewire)

 * [Portswigger](#portswigger)

   - [Labs Completed](#labs-completed)

   - [Demo](#demo)
  

   ## OverTheWire
    
   #### Bandit 0
     
  ![alt text](https://res.cloudinary.com/s1n1s73r-k1773n/image/upload/v1624315610/overthewire/Bandit0_thh95i.png)

   - The file was stored in the home directory readme
     
   - Use -ls to list file
    
   - Use -cat command to display contents of readme
    
   #### Bandit 1
    
  ![alt text](https://res.cloudinary.com/s1n1s73r-k1773n/image/upload/v1624315610/overthewire/Bandit1_yuupe5.png)

   - The file – is located in the home directory
   - Use ls to display 
   - Use ./ current directory to display files with – 

   #### Bandit 2
    
  ![alt text](https://res.cloudinary.com/s1n1s73r-k1773n/image/upload/v1624315606/overthewire/Bandit2_redh7q.png)

   - List files ls
   - Use cat with back slashes before spaces so that it doesn’t think there are 4 different files instead of one. 

   #### Bandit 3

  ![alt text](https://res.cloudinary.com/s1n1s73r-k1773n/image/upload/v1624315608/overthewire/Bandit3_xlhdms.png)

   - The password is in a hidden file. 
   -	Use ls to display contents, but it doesn’t show. 
   -	Need to use ls -la to display all files, including the hidden ones.
   -	Use ‘.’ at the beginning, to open the hidden file.
   
   #### Bandit 4
   
   ![alt text](https://res.cloudinary.com/s1n1s73r-k1773n/image/upload/v1624315608/overthewire/Bandit4_xeawe5.png)

   -	All files have a  - and it’s the only human-readable one
   -	Use the file cmd  and file* as a wild card 
   - Shows file 7 as the readable 
    
   #### Bandit 5
    
   ![alt text](https://res.cloudinary.com/s1n1s73r-k1773n/image/upload/v1624315609/overthewire/Bandit5_ecm9ay.png)

   -	ls to list files in inhere
   -	Since there were so many files within the files, use the "find" cmd
   -	Find cmd shows only one file that has the size given for the password
    
   #### Bandit 6

  ![alt text](https://res.cloudinary.com/s1n1s73r-k1773n/image/upload/v1624315609/overthewire/Bandit6_feef3s.png)

   -	On the server somewhere, so use find cmd
   -	You will find it displays too many files
   -	Narrow your search to size, user, and group
   -	You will find the /var/lib/dpkg/info/bandit7.password and displayed content
  
  ####  Bandit 7

  ![alt text](https://res.cloudinary.com/s1n1s73r-k1773n/image/upload/v1624315609/overthewire/Bandit7_r9zjqx.png)

   - Shows many lines of text
   - Use pipe to grep and find the word millionth
   - This will display one line that gives us the password

  ####   Bandit 8
  
  ![alt text](https://res.cloudinary.com/s1n1s73r-k1773n/image/upload/v1624315610/overthewire/Bandit8_rpxywo.png)

   - Need to use pipe and sort 
   - Sort the files and then pipe it to "uniq" to show the unique password
     
  ####   Bandit 9
  
  ![alt text](https://res.cloudinary.com/s1n1s73r-k1773n/image/upload/v1624315609/overthewire/Bandit9_wizfje.png)

   - The contents of the file is mostly human unreadable text
   - Use the strings cmd and grep to look for = signs

  ####   Bandit 10
  
  ![alt text](https://res.cloudinary.com/s1n1s73r-k1773n/image/upload/v1624315610/overthewire/Bandit10_ouriuo.png)

   - After displaying contents in the file, a base64 code is given
   - Use [CyberChef](https://gchq.github.io/CyberChef/) to decode it.
     
  ####   Bandit 11
  
  ![alt text](https://res.cloudinary.com/s1n1s73r-k1773n/image/upload/v1624315610/overthewire/Bandit11_w0n6zh.png)

   - The file contained a rot13 code
   - Decrypted with [CyberChef](https://gchq.github.io/CyberChef/). 



## Portswigger

### Labs Completed

  ![alt text](https://res.cloudinary.com/s1n1s73r-k1773n/image/upload/v1624843900/labs/portswigger/Russell_Portswigger_labs_Project_Page_2_g51upn.jpg)

  ![alt text](https://res.cloudinary.com/s1n1s73r-k1773n/image/upload/v1624842260/labs/portswigger/Slide2_lzkp8r.jpg)

### SQL Injection

##### SQL injection permits an attacker to manipulate the queries that the application makes with its database. This vulnerability allows attackers access to the data they are unauthorized to view. In the lab "SQL injection vulnerability allowing login bypass," the vulnerability is in the login function. To solve this lab, the user must perform an SQL injection attack and be able to log in as the administrator. I used Burp Suite and the SQL sequence "- -" to solve this challenge. Once Burp Suite intercepted the login request, I could modify the username parameter; then, the SQL comment sequence bypassed the password. 


  ![alt text](https://res.cloudinary.com/s1n1s73r-k1773n/image/upload/v1624842260/labs/portswigger/Slide4_xlrf5o.jpg)
 
### Cross-site scripting 

##### Cross-site scripting (XSS) is a vulnerability that lets the attacker camouflage themselves as the user and performs the actions of the user as well as access all of the user's data. In the lab "Reflected XSS into HTML context with nothing encoded," we practice reflected cross-site scripting. To solve this challenge, an XXS attack is performed that uses the "alert" script. I entered a simple command into the comment box of the website to execute the script.

  ![alt text](https://res.cloudinary.com/s1n1s73r-k1773n/image/upload/v1624842258/labs/portswigger/Slide5_xyivfc.jpg)
  
### Cross-site request forgery (CSRF)

##### Cross-site request forgery is a vulnerability that lets the attacker tempt users to do things that they did not intend to do. An attacker can use session cookies and set values and parameters to execute their attacks. In the lab "CSRF vulnerability with no defenses," there is a vulnerability in the email change functionality. To solve the challenge, we need to create HTML that includes a CSRF attack and change the email address to upload it into our exploit server. I proxied my traffic through Burp Suite and was able to get the method, body parameters, and the URL needed to create my HTML template for the attack. There are three aspects required for CSRF to be successful:
 
  - A relevant action: An action that the attacker wants to induce from the victim. The relevant action in this lab is to change the user's email on the account to mine. 
  -	A cookie-based session handling: The user session needs to rely on a cookie.
  - No unpredictable request parameters in the request like CSRF tokens: To change the user's email account address, all of the parameters need to be known. 

#### My strategy to solve this challenge:
  -	Use the update email functionality. 
  -	Verify the session is cookie-based. 
  -	Verify there are no CSRF tokens.
  -	There are no unpredictable parameters.
  -	Create the proof-of-concept exploit code.
  -	Execute the code on the exploit server.
  
  ![alt text](https://res.cloudinary.com/s1n1s73r-k1773n/image/upload/v1624842260/labs/portswigger/Slide6_kwydi0.jpg)
  
### Directory traversal

##### Directory traversal is a vulnerability that allows the attacker access to files such as application code and credentials. In the lab "File path traversal, simple case," the vulnerability is in the product images. To solve this lab, we needed to get the contents of the file /etc/passwd. My strategy in this lab was to use Burp Suite to intercept the product image request. I then sent the request to the repeater and was able to modify the filename parameter and view the contents of the file. 

  
 ![alt text](https://res.cloudinary.com/s1n1s73r-k1773n/image/upload/v1624842258/labs/portswigger/Slide7_qz9oaj.jpg)
        
### Demo

https://user-images.githubusercontent.com/50695633/123566039-8fe08900-d773-11eb-9df3-0655cfb36ee6.mp4


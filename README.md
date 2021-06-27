# CTF Walk-Throughs
 * [OverTheWire](#overthewire)

- [place holder](#place-holder)
  * [place holder](#rubber-ducky)
  * - [place holder](#tool-demo-s)
  

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

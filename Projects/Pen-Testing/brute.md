<div style="display: inline-block;">
  <a href="https://breachopen.github.io/Chas-Riley/">
    <img src="https://img.shields.io/badge/Home-3ba0e6" alt="Home">
  </a>
</div>

<div style="display: inline-block;">
  <a href="https://github.com/BreachOpen/Chas-Riley/" target="_blank">
    <img src="https://img.shields.io/badge/Github_Source-3ba0e6" alt="Github Source">
  </a>
</div>


---

# Enumeration & Brute Force Simulation

## Overview
This project involved completing the Enumeration & Brute Force room on TryHackMe, where I applied various enumeration techniques and brute force attacks to exploit vulnerabilities in web applications. The exercise provided hands-on experience in identifying potential security flaws and gaining unauthorized access through these methods. After this project, I have a better understanding of website security coding, how common brute force attacks are conducted, how vulnerable HTTP is compared to HTTPS, and how easily a system can be exploited if vulnerabilities are present.

## Tools Used
- Burp Suite
- Python
- Crunch
- Intruder
- Linux OS
- Ubuntu

---

## Tasks to Achieve

### Objectives
Method 1: **Enumeration in Authentication Forms:** Identify valid email addresses using enumeration techniques.
Method 2: **Exploiting Predictable Tokens:** Brute force vulnerable tokens to reset a password and gain access.
Method 3: **Exploiting HTTP Basic Authentication:** Using Burp Intruder to exploit Authorization header strings to assist with brute force attacks.

---

## Project Conclusion

This simulation created by TryHackMe (THM) gave me valuable knowledge and experience with enumeration and brute force attacks. After hands-on training with network security concepts, common attack methods, and identifying security flaws, THM gave me a better understanding of how to apply appropriate mitigation strategies, especially in coding.


---

## Method 1: Enumeration in Authentication Forms

1. **Navigate to the Enumeration Lab:**
   - URL: `http://enum.thm/labs/verbose_login/`
   - Screenshot: ![Enumeration Lab Login Page](path/to/screenshot1.png)

2. **Input Email Address:**
   - Enter an invalid email address to observe the error message.
   - Screenshot: ![Email Does Not Exist Error](path/to/screenshot2.png)

3. **Input Valid Email Address:**
   - Use the provided Python script to check for valid email addresses.
   - Command: `python3 script.py usernames_gmail.com.txt`
   - Screenshot: ![Valid Email Found](path/to/screenshot3.png)

4. **Record Valid Email Address:**
   - Answer: `canderson@gmail.com`

## Method 1 Conclusion
By identifying a valid email address in a database, I now have the information I need to continue further attacks. In this scenario, "C. Anderson" (not sure why I keep running into this same fake user in simulations) would now be my target. I could now target this user in phishing campaigns, attempt credential stuffing if I can find leaked credentials, or attempt to password crack from brute force or after building a researched user profile.

## Method 2: Exploiting Predictable Tokens

1. **Navigate to the Predictable Tokens Lab:**
   - URL: `http://enum.thm/labs/predictable_tokens/`
   - Screenshot: ![Predictable Tokens Lab](path/to/screenshot4.png)

2. **Password Reset Process:**
   - Enter `admin@admin.com` in the Email input field and click Submit.
   - Screenshot: ![Password Reset Success Message](path/to/screenshot5.png)

3. **Capture and Analyze the Token:**
   - Use Burp Suite to capture the request and send it to the Intruder.
   - Screenshot: ![Burp Suite Token Analysis](path/to/screenshot6.png)

4. **Generate Brute Force Payload:**
   - Use Crunch to create a list of numbers from 100 to 200.
   - Command: `crunch 3 3 -o otp.txt -t %%% -s 100 -e 200`
   - Screenshot: ![Crunch Payload Generation](path/to/screenshot7.png)

5. **Configure Intruder and Launch Attack:**
   - Load the generated payload file (otp.txt) in Intruder and start the attack.
   - Screenshot: ![Intruder Payload Configuration](path/to/screenshot8.png)

6. **Analyze Successful Response:**
   - Identify the response with the largest content length indicating a successful token.
   - Screenshot: ![Successful Token Response](path/to/screenshot9.png)

7. **Log in with the New Password:**
   - Use the obtained token to reset the password and log in.
   - Screenshot: ![Dashboard Flag](path/to/screenshot10.png)

8. **Record the Flag:**
   - Flag: `THM{50_pr3d1ct4BL333!!}`
   - Screenshot: ![Flag in Dashboard](path/to/screenshot11.png)
     
## Method 2 Conclusion
Method 2 demonstrated how easily weak or predictable tokens can be exploited to gain unauthorized access into a system. This simulated attack shows how important penetration testing really is. With just a small amount of training, bad actors will absolutely exploit improper coding.

---

## Method 3: Exploiting HTTP Basic Authentication

1. **Navigate to the Basic Authentication Lab:**
   - URL: `http://enum.thm/labs/basic_auth/`
   - Screenshot: ![Basic Authentication Lab Homepage](path/to/screenshot12.png)

2. **Input Credentials:**
   - Input any username and password in the pop-up and capture the Basic Auth request using Burp.
   - Screenshot: ![Random Login Credentials in the Popup](path/to/screenshot13.png)

3. **Capture the Request:**
   - Encoded login credentials in the HTTP Request Header.
   - Screenshot: ![Encoded Login Credentials](path/to/screenshot14.png)
   - Right-click the request and send it to Intruder.
   - Screenshot: ![Captured Request Context Menu](path/to/screenshot15.png)

4. **Decode the Base64 String:**
   - In Burp Intruder, go to the "Positions" tab and decode the base64 encoded string in the Authorization header.
   - Screenshot: ![Decoded Base64 Encoded String](path/to/screenshot16.png)
   - Highlight the decoded string and click the Add button in the top right corner.
   - Screenshot: ![Highlighted Text with Payload Highlight](path/to/screenshot17.png)

5. **Configure Payloads:**
   - Go to the Payloads tab and set the payload type to Simple list.
   - Choose your preferred wordlist (e.g., 500-worst-passwords.txt from SecLists).
   - Screenshot: ![Choosing a Wordlist](path/to/screenshot18.png)

6. **Add Payload Processing Rules:**
   - Add the first rule to automatically add a username to the password.
   - Screenshot: ![First Payload Processing Rule](path/to/screenshot19.png)
   - Add the second rule to base64 encode the combined username and password from the supplied list.
   - Screenshot: ![Second Payload Processing Rule](path/to/screenshot20.png)
   - Remove the character "=" from the encoding list.
   - Screenshot: ![Removing Equal Sign Due to Padding](path/to/screenshot21.png)

7. **Launch the Attack:**
   - Go back to the Positions tab and click the Start Attack button.
   - Screenshot: ![Starting the Attack](path/to/screenshot22.png)

8. **Analyze Successful Response:**
   - Identify the request with a Status code 200 indicating successful brute force.
   - Decode the encoded base64 string in the successful request.
   - Screenshot: ![Decoding the Successful Request Payload](path/to/screenshot23.png)
   - Use the decoded base64 string to log into the application.
   - Screenshot: ![Using the Credentials to Log In](path/to/screenshot24.png)

9. **Record the Flag:**
   - Flag: `THM{b4$$1C_AuTTHHH}`
   - Screenshot: ![Flag in Dashboard](path/to/screenshot25.png)
  
## Method 3 Conclusion
Method 3 targeted HTTP (Hypertext Transfer Protocol) vulnerabilities which is a more direct approach to acquiring a users login credentials. This attack gave me insight on why HTTPS is favored over HTTP due to HTTP containing authentication in its' header string and by only encoding a user's credentials in base64 encoding.

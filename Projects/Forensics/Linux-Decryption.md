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

# Linux Decryption

## Scenario
In this scenario, all of the files in your home directory have been encrypted. You’ll need to use Linux commands to break the Caesar cipher and decrypt the files so that you can read the hidden messages they contain.<br /><br />

## Tasks

**Task 1. Locate the New File**<br />
Commands I used: <br />
ls<br />
cat README.txt<br /><br />

![Locate File](../../assets/img/forensics/Linux-Decrypt/1.png)<br /><br />

**Task 2. Identify the Encrypted File**<br />

Commands I used: <br />
cd caesar<br />
ls -a<br />
cat .leftShift3<br />
cat .leftShift3 | tr "d-za-cD-ZA-C" "a-zA-Z"<br />
cd ~<br /><br />

![](../../assets/img/forensics/Linux-Decrypt/2.png)<br /><br />

**Command Breakdown**<br />
I feel that the scenario simulation skipped over some key information that would have been helpful for the user. The Caesar Cipher was one of the first recorded cryptographic tools used to hide (encrypt) and reveal (decrypt) messages during that time. The process was very simple and involved taking a letter and changing that letter a specified number of spaces to the left. For example, A:X, B:Y, C:Z, D:A, E:B, F:C, etc.<br /><br />
This scenario gives the user the exact command line needed and even offers hints such as the "caesar" directory and ".leftShift3" hidden file. Just so I could see the decryption process, I used the online tool [dCode](https://www.dcode.fr/caesar-cipher).<br /><br />
If ".leftShift3" was not the hidden file name, dCode would still have been able to see which caesar encryption technique was used since the online tool will run the encrypted text through many decryption formulas and return the most probable outcomes.<br />
<br />

![CAESAR CIPHER DECODER](../../assets/img/forensics/Linux-Decrypt/3.png)<br /><br />

![CAESAR CIPHER DESCRIPTION](../../assets/img/forensics/Linux-Decrypt/4.png)<br /><br />

**Task 3. Decrypt the File**<br />
Commands I used: <br />
openssl aes-256-cbc -pbkdf2 -a -d -in Q1.encrypted -out Q1.recovered -k ettubrute<br />
ls<br />
cat Q1.recovered<br />

![File Decrypted](../../assets/img/forensics/Linux-Decrypt/5.png)<br /><br />

**Command Breakdown**<br />
OpenSSL: A Linux command-line tool that is used a for a few different things. I've only used it for encryption, decryption, and hashing, but it can also be used for creating private keys and certificate creation/inquires.<br />  
aes-256-cbc: Advanced Encryption Standard (AES)/256-bit key/Cipher Block Chaining (CBC) mode<br /><br />
-pbkdf2: PBKDF2 or Password-Based Key Derivation Function 2 is a pretty common encryption algorithm that creates encryption keys from passwords through salting and hashing<br /><br />
-a: Specifies that the input/output is Base64-encoded<br /><br />
-d: Specifies that the function needed is to decrypt. "-e" is the opposite function: encrypt<br /><br />
-in Q1.encrypted: Specifies the input file<br /><br />
-out Q1.recovered: Specifies the output file. This is also creating a new file<br /><br />
-k ettubrute: This specifies that the password is "ettubrute"<br /><br />

**Resource Used**<br />
[dCode](https://www.dcode.fr/caesar-cipher) - dCode has encryption/decryption tools, converters, calculators, and numerous other tools that I have used for my other learning and university projects. I highly recommend the site.

--- 

### Homework [h3 - Hash](https://terokarvinen.com/trust-to-blockchain/#h3)
#### x) Summaries

###### Reference: Schneier 2015, [Applied Cryptography: Chapter 2 - Protocol Building Blocks](https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/10_chap02.html#chap02-sec003)
- One-way functions are easy to compute in one direction but very difficult to reverse, like breaking a plate into pieces. Trapdoor one-way functions are also hard to reverse, but have a secret "trapdoor" that allows the function to be computed easily in the other direction.

- One-way hash functions are a fundamental cryptographic tool that take variable-length inputs and produce a fixed-length "fingerprint" or hash value. These functions are designed to be easy to compute in one direction but computationally infeasible to reverse. Message Authentication Codes (MACs) are a type of one-way hash that also incorporates a secret key, allowing only the holder of the key to verify the hash.

<br/>  

###### Reference: Karvinen 2022, [Cracking Passwords with Hashcat](https://terokarvinen.com/2022/cracking-passwords-with-hashcat/)

This tutorial explains how to use Hashcat to crack password hashes. It demonstrates how password cracking works: since systems store passwords as hashes, Hashcat attempts to match a hash by converting dictionary words into hashes until it finds a match. The tutorial covers installing Hashcat, identifying hash types, using the RockYou dictionary, and successfully cracking the hash for the word 'summer'.

<br/>  

---

#### a) 

I’ll approach this systematically by testing different strings to find one that produces a hash starting with zero.

<img src='https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h3/a1.JPG'>

<img src='https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h3/a_meme.jpg' width="300">

 I found that adding "M6" to "hello" creates a hash starting with zero.
 
<img src='https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h3/a2.JPG'>
<br/>

---

#### b)

<img src='https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h3/b1.JPG'>
<br/>

The main observation is that even changing just one symbol (. to !) results in a completely different hash value.

---

#### c) Hashcat

Installing the apps
```
sudo apt-get update
sudo apt-get -y install hashid hashcat wget
```
Creating a new directory
```
mkdir hashed
cd hashed
```

Getting the Rockyou dictionary

<img src='https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h3/c1.JPG'>


Identifying hash type

<img src='https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h3/c2.JPG'>

Cracking the hash

<img src='https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h3/c3.JPG'>

```
Session..........: hashcat
Status...........: Cracked
Hash.Mode........: 0 (MD5)
Hash.Target......: 6b1628b016dff46e6fa35684be6acc96
Time.Started.....: Mon Oct 28 02:48:16 2024 (0 secs)
Time.Estimated...: Mon Oct 28 02:48:16 2024 (0 secs)
Kernel.Feature...: Pure Kernel
Guess.Base.......: File (rockyou.txt)
Guess.Queue......: 1/1 (100.00%)
Speed.#1.........:     3369 H/s (0.05ms) @ Accel:256 Loops:1 Thr:1 Vec:4
Recovered........: 1/1 (100.00%) Digests (total), 1/1 (100.00%) Digests (new)
Progress.........: 256/14344384 (0.00%)
Rejected.........: 0/256 (0.00%)
Restore.Point....: 0/14344384 (0.00%)
Restore.Sub.#1...: Salt:0 Amplifier:0-1 Iteration:0-1
Candidate.Engine.: Device Generator
Candidates.#1....: 123456 -> freedom
Hardware.Mon.#1..: Util: 94%
```

<img src='https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h3/c4.JPG'>



---

#### d) Dictionary attack

Cracking the hash

<img src='https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h3/d1.JPG'>

<img src='https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h3/d2.JPG'>

<img src='https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h3/d3.JPG'>



---

#### e)  How can you make a password that's protected against a dictionary attack?
- Use a long, random passphrase with a mix of uppercase letters, lowercase letters, numbers, and special characters
- Never reuse passwords across multiple accounts
- Use a password manager 

###### Reference: [How to Protect Against Password Dictionary Attacks](https://www.howtogeek.com/devops/how-to-protect-your-organization-against-password-dictionary-attacks/)

---

#### j) Installing John

Installing the tools

```
sudo apt-get update
sudo apt-get -y install micro bash-completion git build-essential libssl-dev zlib1g zlib1g-dev libbz2-1.0 libbz2-dev atool zip wget
```

Downloading John the Ripper

<img src='https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h3/j1.JPG'>

Configuring

<img src='https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h3/j2.JPG'>

Compiling

<img src='https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h3/j3.JPG'>

Running it

<img src='https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h3/j4.JPG'>



###### Reference: Karvinen 2023,[Crack File Password With John](https://terokarvinen.com/2023/crack-file-password-with-john/)


---

#### k)  Cracking the passwords with John

Get a sample ZIP file

```
wget https://TeroKarvinen.com/2023/crack-file-password-with-john/tero.zip
```

Trying to open it

<img src='https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h3/k1.JPG'>

**Cracking the ZIP password.**

Extracting the hash into a new file

<img src='https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h3/k2.JPG'>

Cracking the password with John. The password is there!

<img src='https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h3/k3.JPG'>

Enjoying the loot :-)

<img src='https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h3/k4.JPG'>



###### Reference: Karvinen 2023,[Crack File Password With John](https://terokarvinen.com/2023/crack-file-password-with-john/)

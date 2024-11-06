### h2 - Pubkey
#### x) Summaries

###### Reference: Schneier 2015, [Applied Cryptography: Chapter 2 - Protocol Building Blocks](https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/10_chap02.html#chap02-sec005)

- Public-key cryptography is a system where anyone can encrypt messages using a freely-shared public key, but only the holder of the matching private key can decrypt them.
- Combining digital signatures with public-key encryption ensures both message authenticity and confidentiality.
- There are many digital signature algorithms.
- Cryptographic applications require cryptographically secure pseudo-random sequences, which are both statistically random and computationally unpredictable, making them resistant to attacks. For true randomness, a generator must produce sequences that are unpredictable and irreproducible, qualities that are challenging to achieve on standard computers.

<br/>  

###### Reference: Rosenbaum 2019, [Grokking Bitcoin: Chapter 2. Cryptographic hash functions and digital signatures](https://learning.oreilly.com/library/view/grokking-bitcoin/9781617294648/OEBPS/Text/kindle_split_011.html#ch02lev1sec1)

- Cryptographic hash functions can be used to detect changes in a file or message, as the hash output would change if the input was modified.
- It is computationally infeasible to determine the original input (pre-image) that produced a given hash output.
- Digital signatures allow users to prove the authenticity of a bitcoin transaction, as only the rightful owner of the bitcoins can spend them using their private key.
- Verifying a digital signature does not require knowing the identity of the signer, just that the signature was created using the corresponding private key.
- To receive bitcoins or other cryptocurrency, you need a public key, which is derived from your privately-held private key.
- There are various strategies for securely storing private keys, ranging from simple mobile storage to more complex multi-device, encrypted solutions.
- The more secure a private key is against theft, the higher the risk of accidentally losing access to it, and vice versa.


<br/>  

###### Reference: Karvinen 2023, [PGP - Send Encrypted and Signed Message - gpg](https://terokarvinen.com/2023/pgp-encrypt-sign-verify/)

The tutorial shows how to use PGP encryption with the 'gpg' tool to send secure messages over the Internet. It demonstrates a practical example where two users exchange public keys, establish trust, and then user sends an encrypted and signed message. The tutorial emphasizes how PGP allows secure communication over untrusted networks by using public key cryptography - where encryption prevents others from reading messages and signing verifies the sender's identity.

<br/>  

---

#### a) Pubkey example

Visiting a website that uses an HTTPS protocol (e.g. bank service, email). **HTTPS (Hypertext Transfer Protocol Secure)** is a secure version of HTTP that encrypts data between a web browser and a website.

1. Browser checks the website's SSL/TLS certificate, which contains the site's public key.
2. Browser verifies the certificate is issued by a trusted Certificate Authority.
3. Browser uses the site's public key to encrypt a session key.
4. The site decrypts the session key using its private key.
5. All subsequent communication between browser and the site is encrypted using the session key.

###### Reference: [What is HTTPS?](https://www.cloudflare.com/learning/ssl/what-is-https/)
<br/> 

---

#### b) Messaging

Installing ‘gpg’ encryption tool, text editor ‘micro’ and ‘psmisc’:
```
sudo apt-get update
sudo apt-ge install gpg micro psmisc
```
Creating Maria's keypair:
```
gpg --gen-key
```
The keypair:

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h2/p1.png">

Exporting Maria's public key:

```
gpg --export --armor --output maria.pub
```
<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h2/p2.png">

Creating Alice:

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h2/p3.png">

Creating Alice's keypair:
```
gpg --homedir . --gen-key
```
<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h2/p4.png">



Alice copies Maria's public key:

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h2/p5.png">
<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h2/p6.png">

Alice checks the fingerprint to verify that this is Maria’s key:

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h2/p7.png">

Alice signs Maria’s key:

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h2/p8.png">

Verifying Maria’s key, Alice has full thrust on Maria’s key:

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h2/p9.png">

Now, Maria needs Alice’s public key to know it’s her:

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h2/p10.png">

Maria imports the key and verifies the fingerprint:
```
gpg --import alice.pub
```
<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h2/p11.png">

```
gpg --fingerprint
```
<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h2/p12.png">

Alice creates and encrypts the message:
<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h2/p13.png">

Maria decrypts and verifies the message:
<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h2/p14.png">


###### Reference: Karvinen 2023, [PGP - Send Encrypted and Signed Message - gpg](https://terokarvinen.com/2023/pgp-encrypt-sign-verify/)
<br/>  

---

#### c) Encrypt a message using a tool other than PGP

<br/>  

---

#### d) Eve and Mallory

Protection against Eve :
-	Uses recipient's public key to encrypt the message
-	Only recipient's private key can decrypt it
-	Even if Eve captures the message, she can't read it
-	In PGP command: -encrypt: encrypts with recipient's public key
  
Protection against Mallory:
-	Sender's private key signs the message (creates digital signature)
-	Recipient uses sender's public key to verify signature
-	If Mallory modifies anything, signature verification fails
-	In PGP command: -sign: signs with sender's private key




<br/>  

---

#### f) Password management

Bitwarden Password Manager Example:
-	Generate strong password
-	Save it in a vault in the cloud, encrypted end-to-end
-	Access with one master password

Benefits of using pass managers:
- Unique passwords
- Complex generated passwords
- No need to memorize multiple passwords
- Identifies compromised passwords stored in your vault to minimize risk and keep your credentials secure

**Attacks targeting poor password practices:**
- Phishing (email/SMS/call scams to trick users into revealing credentials)
- Man-in-the-Middle (intercepting communications between users/systems)
- Brute Force (attempting massive numbers of password guesses)
- Dictionary Attacks (using common words/phrases as password guesses)
- Credential Stuffing (reusing previously compromised credentials)
- Keyloggers (malware to record keystrokes and steal passwords)

 
###### Reference: [Bitwarden](https://bitwarden.com/products/personal/)
###### Reference: [Six Types of Password Attacks & How to Stop Them](https://www.onelogin.com/learn/6-types-password-attacks)
<br/>  

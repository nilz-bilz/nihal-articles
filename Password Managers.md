# Online Security Essentials (Part 1/2) : Password Managers

![Intro Image](https://shivering-isles.com/assets/images/2017/08/password-safes.jpg)

**A comprehensive 2 part guide on the bare essentials of securing your online presence**

## Introduction
Practically every service we use on the internet today requires a "user-name" & "password". Passwords have become the standard method of authenticating anyone across the internet since its earliest days, and not much has changed since in most cases. As time progresses, the number of services we use across the internet increase, as well as the passwords we have to keep track of. 

Security experts have warned people about the dangers of not using a secure password, and re-using them across multiple sites since the 90s, but in practice it can be very tedious to actually follow through with that, since there is only so much the human brain is capable of memorizing. <!--more-->

![XKCD](https://imgs.xkcd.com/comics/password_strength.png) 
The famous xkcd web comic “Password Strength” explained it best: “Through 20 years of effort, we’ve successfully trained everyone to use passwords that are hard for humans to remember, but easy for computers to guess.”

This eventually led to the norm we have today where people either use the same password everywhere, or use variations of the same password and end up clicking on the "forgot password" button every now and then. 
Creating & storing new passwords in a notebook isn't the worst idea, but a backup strategy with that is difficult.

The [2019 Google Online Security Survey](https://services.google.com/fh/files/blogs/google_security_infographic.pdf) found 52 percent of respondents reused the same password for multiple (but not all) accounts. 

According to the [2019 Verizon Data Breach](https://www.nist.gov/system/files/documents/2019/10/16/1-2-dbir-widup.pdf) Investigations report, 80 percent of data breaches are caused by compromised, weak, and reused passwords.

Using giant lists of stolen passwords (aka “dumps”) bought off the [dark web](https://blog.malwarebytes.com/security-world/2017/07/explained-dark-web/), cyber-criminals can [brute force](https://blog.malwarebytes.com/glossary/brute-force-attack/) their way into other sites or use old passwords to extort users in scams. This is the [data breach](https://www.malwarebytes.com/data-breach) domino effect. One breach leads to another and another and so on.

Password managers aim to solve exactly this.  

## What are Password managers?
One can think of them as a secure database of passwords protected by a single super secure ["Passphrase"](https://csrc.nist.gov/glossary/term/Passphrase). They are comparable to those diaries with mini locks that we might have used as kids. 
![Diary](https://i.ytimg.com/vi/Cvforgs2-iA/maxresdefault.jpg)
Only difference here is that instead of a lock, it is protected by a ["Passphrase"](https://csrc.nist.gov/glossary/term/Passphrase), and more importantly, it can ***GENERATE*** cryptographically secure passwords. This essentially lets a user generate random passwords for each account without having to remember ANY of them. All the user has to remember is the master passphrase to access the password manager, and just copy-paste it.

### Understanding Passphrases
You can think of passphrases as a sequence of words instead of random-ish gibberish that we normally use for "Passwords". For Example:  *"splice gauze overpower flagship litter"* can be a passphrase while *"N3HrMTEiKWb6M9"* or *"<'petname>@<'random year>"* are passwords. Passphrases are generally known to have more Entropy (measure of password stregnth), while being easier to remember. You can learn more about password entropy and other such concepts [here](https://sunknudsen.com/stories/exploring-the-password-policy-rabbit-hole/). 

If you're not comfortable with using random words for a passphrase, you could also use a sentence, but ideally it shouldn't be personally identifiable or too popular a statement/dialogue. [Dictionary Attacks](https://en.wikipedia.org/wiki/Dictionary_attacks) are often used to crack passphrases. If you speak a language other than English, especially one without a Latin derived script, one can use that language as it might not only have fewer data-sets to brute force with, but also the ["Transliteration"](https://www.vocabulary.com/dictionary/transliteration) is never standardized across regions.  

People with a more advanced security requirement should create a passphrase

## Benefits of using a password manager
For those who want a clear list of the actual tangible benefits it provides:

- **You don’t have to memorize all your passwords anymore:** Probably the biggest reason. Security and convenience often follow an inverse relationship, however this manages to provide both. You only need to remember the master password that unlocks your password vault. And if you opt for a cloud-based password manager, you can access your password vault anywhere, from any device.
- **They can auto-generate highly secure passwords for you:** This solves the problem of managing multiple passwords while keeping them secure.
- **They can alert you in case of a [phishing](https://www.malwarebytes.com/phishing) site**: Phishing is when fake websites and emails are made to look like their original counterparts in an attempt to steal your credentials. If you're using a Password Manager with a browser extension, then it wont attempt to auto-fill on those sites if you've saved the original site's URL in the manager.
- **Digital Inheritance:** In the event of your death, the process of passing on access to your accounts becomes much easier with password managers. One can simply hand over access to the vault itself
- **Password managers save time:** They just provide a great amount of sanity while using the internet without having the fear of not being secure. 
- **They help protect your identity:** By using a unique password for every site, you’re segmenting your data across each service you use. If a criminal hacks one of your accounts, they won’t necessarily be able to get into any of the others. This provides an additional layer of security that you’ll certainly appreciate in the aftermath of a data breach. And even after a password is breached, changing it isn't that much of a hassle. 

## Choosing a Password Manager
There are several factors one needs to consider before choosing a password manager. This depends on a person's ["Threat Model"](https://owasp.org/www-community/Threat_Modeling). One needs to choose how much convenience they want to, or need to give up for higher degree's of Security. To better understand "Threat Modeling", please watch [this](https://youtu.be/DHZRhboZhfI) video. 

### Criteria
1. **Open-Source:** The ***"source code"*** of an application is the actual lines of code that are used to build it. Most programs we use on a daily basis are ***"Proprietary"***, which means that the source code is not available to the public. On the other hand ***"open-source"*** application have their source code published publicly for anyone to individually audit, contribute to, or even clone and modify. This adds a layer of transparency that is absolutely critical when it comes to applications that have more sensitive use cases, such as Password Managers.  
Popular password managers that you may have heard of such as ["LastPass"](https://www.lastpass.com/), ["Dashlane"](https://www.dashlane.com/), & ["Nordpass"](https://nordpass.com/) are "Proprietary". While this may not inherently make them less secure, not knowing what's happening under the hood is not ideal when it comes to sensitive use cases.
-----------------------------------------------------------------------------
[LastPass](https://www.lastpass.com/) suffered a data breach in 2015. During the breach, cybercriminals made off with user emails but did not manage to steal any passwords. Even if they did, most password managers, including LastPass, use hardcore military-grade encryption to keep passwords safe.
Such vulnerabilities are often patched much sooner in open-source software since it is publicly auditable and anyone can create their own patch and request the administrators to incorporate it.
A popular free & open-source password manager that's accessible across all devices is ["Bitwarden"](https://bitwarden.com/). 

2. **End-to-end encryption (E2EE)**: [E2EE](https://en.wikipedia.org/wiki/End-to-end_encryption) is absolutely essential for any service where Privacy & Security is of paramount importance. Most password managers you may come across will most likely incorporate it by default. E2EE makes sure that the data (in this case passwords) are only decrypted on your device with only you having access to the private key (derived from your passphrase). No party in the middle will be able to access the contents of your data. This is especially important when using cloud enabled managers where you need to make sure that the information that they are storing has no chance of being readable on their end, or anywhere in between. 

3. **Sovereignty**: This is an important criteria to consider for people with higher "threat models". Some people feel the need to have more fine tuned control over how their data is handled, and more importantly WHO is handling it. In these cases, one can opt for a completely local password manager, where the database is created as an encrypted file, which they can manually handle. That file can then be uploaded to the cloud or be part of a more private offline backup scheme. The most popular choice for this workflow is [KeePass](https://keepass.info/). 

## Recommendations
The 2 main Password Manager recommendations based on the above criteria are:

1. [**Bitwarden**](https://bitwarden.com/): 
![BTW](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse3.mm.bing.net%2Fth%3Fid%3DOIP.SdNAM4Barg48yerTbrSLtQHaEo%26pid%3DApi&f=1)
 - Accessible on all devices (MacOS, Windows, Linux, Android, iOS) and through the web  vault
 - Syncs up through the cloud and makes it very easy and convenient to manage without compromising on Privacy & Security. This is due to its end-to-end encryption, and open-source nature that verifies the integrity of the encryption.
 - Perfect for beginners and experts alike
 - For advanced users who require more sovereignty, one can ["self host"](https://bitwarden.com/help/install-on-premise-linux/) the service on their own server. 

2. [**KeePass (Windows)**](https://keepass.info/) or [**KeePass XC (cross-platform)**](https://keepassxc.org/):
![KP](https://dashboard.snapcraft.io/site_media/appmedia/2020/09/database_view.png)
 - Local encrypted database stored as a .kdbx file. 
 - Great option for those who want more manual control how and where their passwords are being handled. 
 - KeePass is an open standard, hence it can be accessed through multiple clients depending on what device you're on. You can check the list of clients [here](https://keepass.info/download.html).  
 - The file can be synced with cloud services or can be used entirely manually. 
 - End-to-end encrypted and open-source
 - Practically the most secure option while compromising on some convenience
** Users can also choose to use this along with Bitwarden for storing passwords/ keys that are more sensitive. KeePass can also be used for storing other kinds of secrets. 

Both are secured using a passphrase, and both are capable of randomly generating passwords. The password generator on KeePass & KeePass XC also has an entropy count to know the exact "bits" of entropy, along with a comment on the strength of the password / passphrase. 

To learn all the features and tricks of KeePass, watch [this](https://youtu.be/sePT9AZauWs) video. 
-----------------------------------------------------------------------------

**I hope this guide was useful to you all, and i hope everyone reading this ends up configuring a password manager for themselves soon. The 2nd part of this guide will be about "2 factor authentication (2fa)", and how to enable & manage that properly.**

### References:
-> https://services.google.com/fh/files/blogs/google_security_infographic.pdf
-> https://www.nist.gov/system/files/documents/2019/10/16/1-2-dbir-widup.pdf
-> https://sunknudsen.com/exploring-the-password-policy-rabbit-hole/
-> https://www.youtube.com/techlore
-> https://xkcd.com/936/
-> https://csrc.nist.gov/glossary/term/Passphrase
-> https://en.wikipedia.org/wiki/End-to-end_encryption
-> https://owasp.org/www-community/Threat_Modeling
->  https://blog.malwarebytes.com/security-world/2017/07/explained-dark-web/
-> https://blog.malwarebytes.com/glossary/brute-force-attack/
-> https://www.malwarebytes.com/data-breach
-> https://www.malwarebytes.com/phishing

```Nihal Atwal 2022``` [*PGP Public Key*](https://write.as/g7kpl5o65j0l8gkk.md)

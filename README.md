# RXRTools Guide 

Welcome to RXRTools Guide by Moka.

![Logo](https://cdn.discordapp.com/attachments/261533084678225920/844517904682450944/logo.png)

***
# Contents
>## 1) Introduction
>## 2) Main Setup
>## 3) Email Recovery
>>### 3.1) What it Does?
>>### 3.2) Setup
>>>#### 3.2.1) Settings
>>>#### 3.2.2) Input Files
>>>#### 3.2.3) Output Files
>>### 3.3) How it Works
>## 4) Email Checker (WIP)
>>### 4.1) What it Does?
>>### 4.2) Setup
>>>#### 4.2.1) Settings
>>>#### 4.2.2) Input Files
>>>#### 4.2.3) Output Files
>>### 4.3) How it Works
>## 5) Important Information
>## 6) FAQ

***
# 1) Introduction
This is a guide for **RXRTools** made by **RUN_X_RAFFLE_G'S Developer Team**. This guide will explain thoroughly on how to properly configure the toolbox and how to work with it more efficiently.

***
# 2) Main Setup
* **Installation Guide**
> **Install** RXRTools by the **MEGA** link you can find on [our website](https://dashboard.rxrtools.com/dashboard) or in [RUN_X_RAFFLE_G'S Discord Server](https://discord.gg/CypkmpSzwk) in **RXRTools Download Channel**. When you downloaded the zip file, you should **unpack it** and open the folder. In the folder you will find multiple different files, but the RXRTools application will be the only **.exe** file. To try out if the application works, double click **RXRTools.exe** and enter your Authentication Key. 
```
 ____  __  ______ _____           _
|  _ \ \ \/ /  _ \_   _|__   ___ | |___
| |_) | \  /| |_) || |/ _ \ / _ \| / __|
|  _ <  /  \|  _ < | | (_) | (_) | \__ \
|_| \_\/_/\_\_| \_\|_|\___/ \___/|_|___/


Enter your authentication key:
```
If it worked, then it will prompt you with 
```
 ____  __  ______ _____           _
|  _ \ \ \/ /  _ \_   _|__   ___ | |___
| |_) | \  /| |_) || |/ _ \ / _ \| / __|
|  _ <  /  \|  _ < | | (_) | (_) | \__ \
|_| \_\/_/\_\_| \_\|_|\___/ \___/|_|___/


Enter your authentication key:RXRX-XXXX-XXXX-XXXX-XXXX
Key Authenticated!


(1.) Email Recovery
(2.) Email Checker (WIP)
(3.) Close All Chrome Windows
(4.) Exit.

```
After that, you can finally select the module you want to use.

* **Make Chrome the Main Browser**
> As for now, this is mostly a browser toolbox, so it uses the most popular browser: Google Chrome. In order for everything to work properly and the program to open correctly, Chrome must be selected as the main browser. You can do it in "Windows Settings", just open it, then click "Apps" and then "Default apps". On this page you can select your default "Web browser". There you should select "Google Chrome"

***
# 3) Email Recovery
## 3.1) What it Does?
"Email Recovery" is a RXRTools module created for recovering/checking broken emails.

**For example:** you have a list of emails, but you did not use them in a while, or just want to check if they are working. In this case, you will use the Recovery tool. It checks emails **if a user can log in to them and receive emails**. If they need a mobile phone authentication, then the module uses the **SMS-Activate API** (more API will be implemented later), which allows the module to send a SMS to a **temporary phone number**, and re-activate the gmail account. In the worst case, the gmail account that is checked can be **banned**. In this case, the Recovery Tool will save all the checked banned accounts in a specific **.csv file**, so you can later filter out your list.

## 3.2) Setup
### 3.2.1) Settings
In the main folder, you can find a ***settings.yml*** file. You can edit it with any **File Editing Software** (Notepad, Wordpad, Sublime Text, etc.). There you will see this:
```
#Main Settings
TABS: 5

#SMS Activate
SMS_API_KEY: ''
SMS_SERVICE: 'go'
SMS_COUNTRY: 0
TRIES: 40

#Sender Email
GMAIL: ''
GMAIL_PASSWORD: ''

#Sleeps
NEW_URL: 20
NEW_ACTION: 10
NEW_PAUSE: 2
```
Under ```#SMS Activate``` you can select proper settings. P.S. All of the settings are based by [SMS Activate API](https://sms-activate.ru/en/api2):

* *SMS_API_KEY* - SMS Activate API Key ([find it here](https://sms-activate.ru/en/api2))
* *SMS_SERVICE* - SMS Activate type of mobile phone which will be used (default: **go**, which stands for gmail)
* *SMS_COUNTRY* - Country which will be mainly used for Recovery module (default: **0**, **will be rewritten**)
* *TRIES* - Tries the app will take in order to try and activate the email (default: **40**, )

### 3.2.2) Input Files
In the ***Input*** folder, there are **2 main files** in order for the Recovery Module to work. 

* ***emails.csv***
>Here you should enter all the email you want **recovered/checked**. This file could be opened with Notepad, but Ron's Editor is preferred, as it will be easier to edit them. You should enter them like this:
>```
>email@gmail.com,password,recovery.mail@gmail.com,,
>```

* ***proxies.txt***
>Here you should enter all the **proxies you want to be used**. This file could be opened with Notepad, WordPad, Sublime Text, etc. You should enter them like this:
>```
>host:port:user:pass
>```

### 3.2.3) Output Files
In the ***SMS*** folder, there is **one file** for now, which will output **checked profiles**

* **accs.csv**
>*See more imformation as on to why there is only one file in **5) Important Information**.*\
>This file outputs all the emails that have been checked and recovered. They include:
>* Emails that were already **working perfectly**
>* Emails that have been **SMS recovered** and now work
>* Emails that are **banned** and no longer can work

## 3.3) How it Works
When you select ```Email Recovery``` by pressing **1** on your keyboard, you are prompted with this:

1) **Entering Tab Amount**
>```Enter your tab amount: ```\
>Here, you should enter your needed tab amount that will run simultaneously during the task. In simple turns, **how much emails you want recovering at one time?**. 
>* For **slower PCs**, or PCs with slow internet, the recommended amount is **5** (*can be changed*).
>* For **faster PCs** or Dedicated Servers, the recommended amount **10** (*can be changed*).

2) **Selecting preferred country**
>```
>Countries:
>(0) Russia
>(1) Ukraine
>Enter your preffered country:
>```
>Here, you should enter your **preferred country** the SMS Activate will start from (*In the future, more countries will be available for selection*). It means that if there will be an email that requires recovery, then the **country selected** phone number will be used. If it was used **too many times**, or there are **no available phones** in this country, then the country will be **rotated** to the next one.




***
# 4) Email Checker (WIP)
## 4.1) What it Does?

## 4.2) Setup

### 4.2.1) Settings

### 4.2.2) Input Files

### 4.2.3) Output Files

## 4.3) How it Works

***
# 5) Important Information
The information told here are the things which the user should do/not do while the app is in the **early development stage**. These errors are already **found by the developer** and will be fixed as soon as possible. If more smaller errors will be found by users, they will be written in the **FAQ part of the guide** (6 FAQ).

* **DO NOT USE YOUR KEYBOARD WHILE THE APP RUNS**
>The most important fact about RXRTools is that it uses [Virtual Keys](https://docs.microsoft.com/en-us/windows/win32/inputdev/virtual-key-codes), so it **interferes** with the main keyboard inputs. This problem should be **fixed soon** in next updates, as well as with headless mode. However for now, RXRTools is recommended to use on a **dedicated server**, so it can run in the background. This means, the app will do incorrect work if the user will type out something on the PC (doesn't matter if the user is tabbed out from the app), or if **modificators** are turned on, such as Ctrl, Shift, CAPS LOCK, etc.

* **The app will open up other Chrome Windows**
>Due to the toolbox being at most a browser app, as well as being in Alpha stage, it will **open up windows** which will run appropriate tasks. As headless mode is still not implemented (it will come very soon), the windows will be opened on the main screen. It is important **to not close or minimize the windows**, as it will affect the performance or even crash it.

* **Recovery Tool is not yet dividing the emails into separate files**
>There was a problem with the compilation of the toolbox, so for now, all the emails that have been checked will be saved in one file. Therefore, you can use it to recover accounts, but you will not yet know what account were these. This is already fixed in the dev version, so it will be updated when the new patch comes.

* **Problem with the spaces in SMS folder**
>In the first update, the recovery output file is saving files with one blank space in between them. This is already done in the next update, and will be fixed in the next patch.

* ***settings.yml***
>I heard that ***settings.yml*** is not a great format for users, so i'll change it to ***.txt*** for simplicity. As well as that, some settings in this file are unused, and therefore will be removed in the next update.

***
# 6) FAQ
There is nothing for now, when users will find something interesting, it will be posted here...

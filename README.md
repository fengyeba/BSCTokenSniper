TELEGRAM GROUP: https://t.me/joinchat/LivGs7b26iBkNWE0 - please join to assist in development, ask questions, share any successes etc.

# BSCTokenSniper v1.2 Beta

Improvements:

- Added code blacklist (code_exceptions.txt): the program will ignore any program with code that is in this file

- Added min liquidity checker (won't buy token unless it has certain amount of liquidity) - edit threshold in config.json

- Fixed issue with buy - saying transaction failed when it was fine

- Changed to websocketprovider instead of httpprovider - alot more reliable and also faster, should be less crashing as well

- You can now change websocketprovider node in config.json instead of being in code

- Some bits of code tidied up

(SpecifiedTokenSniper is not updated and still in v1.1 folder, will be integrated in main program and in GUI in future)

Also massive thanks to Christiaan Van AS, Muhammed Nurhaqqin and everyone else on Telegram for development and support with this project.


# BSCTokenSniper v1.1

Just a few improvements, but largely untested. Would greatly appreciate if you could give me feedback. Thanks!

Improvements:

- Added 'check for test' to ignore tokens which have 'test' in their name.

- Added 'try' and 'catch' clauses for buy token and listenForTokens function to avoid exiting with error

- Added function to detect WBNB pair in either pair 1 or pair 2 (currently only detects WBNB in pair 1 which potentially ignores alot of tokens)

- Created 'SpecifiedTokenSniper' script - this allows you to snipe a specific token at launch as soon as it gains liquidity, if you know the token address. 
If you're lucky (like the refinable bot) you could make huge amounts of money.

- You can now pick what liquidity pair address you would like. It is set to WBNB by default (recommended) but you can change to anything if you wish.

New config.json entries:

- "checkForTest": choose whether "test" is in the token's name. Only enable if checkSourceCode is enabled. Recommended.

- "liquidityPairAddress": Leave it unless you want to change the liquidity pair address.


# BSCTokenSniper v1.0


A bot written in Python to automatically buy tokens on the Binance Smart Chain as soon as liquidity is provided.

BSCTokenSniper is a bot written in Python to detect new PairCreated events in the Binance Smart Chain (when a liquidity pair has been created) and buy the token. It is quite reliable and works well but it is the first version, so if you find any problems/improvements/suggestions please let me know by raising an issue.

#Update


- Some user facing error when run this bot on Linux or MacOS, the error is because ctypes windll which is for windows. And there minor update to run in linux version. And runing perfectly.

- added run.py to make it simple for you. there 3 option you can run, 
-
- 1. Windows
- 2. Linux
- 3. Install Dependendency 
-
web3 nodejs not needed here.


Screenshot


![ss1](https://raw.githubusercontent.com/geeks121/BSCTokenSniper/main/images/simple.PNG)


Description

# Description


The aim of BSC Token Sniper is to buy new tokens with a specified amount of BNB, with the aim of the price rising Once the bot detects a PairCreated event, it is able to check the token (mini audit).

 It can check if:
-	Source code is verified.
-	If valid PancakeSwap v2 router is being used 
-	If a mint function exists
-	If it is a potential honeypot
-	PancakeSwap v1 router address is not being used.
-	check for solidity4 [credit](https://github.com/BytePhoenixData/BSCTokenSniper/issues/11#issuecomment-901779866)

The user can decide whether to enable the mini audit or turn it off (bear in mind you will likely be investing in a lot of scams if you don’t).
Once the token has/hasn't been through a mini audit the bot will then attempt to buy X amount of tokens with the specified amount of BNB.
The bot will buy the tokens directly through the Binance Smart Chain using the PancakeSwap v2 router and factory address, so it is much quicker than the PancakeSwap web interface.

By avoiding web interfaces & Metamask and directly with Ethereum & EVM Nodes you can snipe tokens faster than any of the web-based platforms. This allows tokens to be sniped almost instantly. During our testing we found the bot would typically be within the first 3 buy transactions of all tokens it finds.
The bot buys the tokens using the user's wallet address and private key. This information is kept secure, is only stored locally on your computer, and is only ever used to buy tokens (look through the code to see for yourself).

The bot does not incur any additional fees, only fees are BSC network transaction fees and PancakeSwap fees.

# Prerequisites

- Python 3 or later installed
- Node.js installed (easiest way) – Install windows version from https://nodejs.org/en/download/
- Web3 installed (in windows command line type: pip install web3)
- BscScan API key (completely free of charge, create an account on BscScan and generate a free API key)
- BSC wallet address and private key
- enough BNB in your wallet to snipe tokens.


Setup for Windows.

# Setup


1)	Install all dependencies (above)
2)	Edit config.json file with your wallet address, private key and BscScan API key.
3)	(Optional) if you are in windows, open the command prompt and right-click the title bar, click ‘properties’ and set screen buffer size height to 2500. This allows you to scroll through the history of your token snipes.
4)	In command prompt (assuming you are using windows) type 'python' and press enter, and check that it is recognized by the computer. If you get a message that says it isn't recognized, then change the 'launchBSCTokenSniper.bat' file and replace 'python' with the path to your python program's executable file (make sure the filepath is in "" quotes).
5)	Run ‘launchBSCTokenSniper.bat’ and you’re good to go!

  ## Supported OS
  1. Windows [tested and work]
  2. Linux [tested and work]
  3. Mac [tested and work]
  4.  Android [tested and work, need tricky web3 installation]
  
  # **INSTALLATION**
	

## Windows

   1. Download git [Git](https://git-scm.com/)
   2. Download python[Python](https://www.python.org/)
   3. Clone the repo : 
   - `git clone https://github.com/BytePhoenixData/BSCTokenSniper.git`
   4. Go to repo directory
   - `cd BSCTokenSniper`
   6. Install Web3
   - `pip install web3`
   If you facing error when web3 installation, you need microsoft visual studio build tool.
   use this [link](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019).
   ## Linux User
  Install package With `sudo`
Debian / Ubuntu : 
 1. install all dependency using command below.
   ` apt install git && apt install python3-pip && pip install web3 ` 
2. Clone repository and install web3
	    `git clone https://github.com/BytePhoenixData/BSCTokenSniper.git && cd BSCTokenSniper && pip install web3`

Fedora Linux / Centos
 1. install all dependency using command below.
   ` dnf git && dnf install python3-pip && pip install web3 ` 
2. Clone repository and install web3
	    `git clone https://github.com/BytePhoenixData/BSCTokenSniper.git && cd BSCTokenSniper && pip install web3`

Arch Linux
 1. install all dependency using command below.
   ` pacman -S git && pacman -S install python3-pip && pip install web3 ` 
2. Clone repository and install web3
	    `git clone https://github.com/BytePhoenixData/BSCTokenSniper.git && cd BSCTokenSniper && pip install web3`
- If you all find the error try this bellow command and may fix your problem.
`pip uninstall web3 && pip install web3`
or
`pip install -U web3`
## Android
  1. Install Termux [Link](https://play.google.com/store/apps/details?id=com.termux&hl=en&gl=US)
  2. Update
   `pkg update && pkg upgrade`
   3. Install dependency
    `pkg install git python3 python3-pip`
	4. Install web3 
    `pip install web3`
	`pip install -U web3`
	5. Clone the repo using git
	`git clone https://github.com/BytePhoenixData/BSCTokenSniper.git && cd BSCTokenSniper`

- note 
you may find the error when installing web3 in android you should install dependency needed by web3 manualy using pip.
	web3 version that work for this bot is web3 5.x.x if your web3 is 3.x.x the bot will not work.
## Run pythonscript
Assuming you are in BSCTokenSniper Directory.
`python3 BSCTokenSniper.py`
To use other version you need to directory needed and run python script.

Happy Sniping.

Setup for Linux & Mac User.
1) Run : python run.py
2) Select option 3 first.
3) Select for your own system.
4) Don't forget to setup config.json

Configuration File

# Configuration File


When you download the bot, you will find a config.json file. This is where you need to add the following data.

walletAddress: your BSC wallet address (e.g., Metamask)
walletPrivateKey: your private key of your wallet address (your private key is kept safe and not shared in any other place)
amountToSpendPerSnipe: The amount in BNB you want your wallet to spend on every new token. (e.g., 0.00025 means a new snipe will spend 0.00025 BNB on the new token)
transactionRevertTimeSeconds: Time to spend before transaction reverts. Recommended to leave at default.
gasAmount: amount of max gas to use per transaction. Recommended to leave at default.
gasPrice:  max price of gas to use per transaction. Recommended to leave at default.
bscScanAPIKey: Your API key from BscScan.
observeOnly: enabling this will disable buying of coins but allows you to observe how the bot audits tokens. Recommended to try this at the start to make sure the bot can scan for new tokens.

# Mini audit

The bot has an optional mini audit feature which aims to filter some of the scam coins (eg. wrongly configured, honeypots). Obviously, this is not going to be as good as a proper audit (eg. CertiK) but at least the coins the bot will buy will be higher quality and if you enable the options, you should be able to sell the tokens later on (provided it hasn’t been rugged).

The following json entries are for mini audit. Set all to false to disable mini audits, although beware you will probably be buying a lot of scam coins.
checkSourceCode: checks if source code is verified. This function is needed for all the other functions so if you disable this be sure to disable all the other audit options. Recommended.

checkValidPancakeV2: checks if the correct PancakeSwap v2 router address is used in the code. Be aware some contracts may externally set their router address so this function may reject a potentially good token. Not recommended.

checkMintFunction: checks if a mint function is present in the code. Recommended.

checkHoneypot: checks the code to see if it might be a honeypot (where you can buy tokens but cannot sell). Recommended.

checkPancakeV1Router: checks to see if the PancakeSwap v1 router address is used in the code. You will not be able to sell the tokens later on if PCS v1 router address is used. Highly recommended.

Note: be very careful when editing config.json and make sure to not alter the syntax. For mini audit options, either use “True” or “False” making sure to capitalise the 1st letter. Any other spelling will not work.

# Things to note

-	Do not worry if you are not seeing any new tokens being detected. There are often around 10-20 new tokens being created per minute but that can vary quite a lot. Sometimes no new tokens may be detected for a few minutes.

-	The bot only buys tokens whose liquidity is paired with Wrapped BNB (WBNB). You could alter the code to buy tokens paired with another currency if you wanted.

-	Please check that you have enough BNB in your wallet to afford sniping new tokens. If you don’t the bot will not work.
-	Please be careful when editing the config.json file. If you delete a comma or quotation mark etc. the bot will not work and throw an error.
-	To launch the bot, run the ‘launchBSCTokenSniper.bat’. The bot should then open in a cmd window and load.
-	Don’t left click in the cmd window as it will enable select mode and stop the output (you will see ‘Select’ in the title). If this happens right click your mouse to deselect it. 

# FAQs

I've sniped loads of coins - but how can I check which ones have made a profit?
-	For this go to poocoin.app, click 'Wallet' and connect your Web3 wallet that you are using for your bot (eg. Metamask).
-	It will then give you the list of tokens in your wallet and show you which ones have made the highest profit.
-	Click the descending arrow next to the balance tab to show highest to lowest tokens value.
-	Then you can manually sell the tokens which have made you a profit on PancakeSwap.

I keep getting ‘Transaction failed’ – what’s going on?
Either:
-	Gas amount / price too low
-	Wallet address / private key incorrect
-	Not enough BNB to pay for the token and TX fees

The bot isn’t sniping that fast (eg. couple seconds between detection and buying)
- This is mainly due to internet speed and computer processing power. 

# Risks:

Investing in BSC tokens / shitcoins is risky and be aware you could lose all your money. For this reason, do not invest more money than you are prepared to lose.
It is pretty much impossible to snipe bots very early and be sure it isn’t a rug pull. When people create tokens in most situations, they will manually create liquidity in PancakeSwap. This is when the bot will detect the token. If they burn / lock liquidity, they will then usually send their LP tokens manually to a deadcoin address or put them in a liquidity locker. Therefore, you can’t immediately snipe the tokens with 100% certainty they aren’t rugpulls.

The mini audit feature can’t be 100% accurate but aims to filter out the majority of scams / hacks and reduce the chance of losing your money.
If a programmer creates token code in a unique way, they may be able to bypass detection although this is generally quite rare, as the majority of tokens are forks of big projects with very little of the code having been changed e.g., Safemoon.

# Things to do / improve / fix:

- Clarify installation of web3 as alot of users had issues with it

- Improve honeypot detection (at the moment it is very simple and some tokens are rewriting their code to bypass the bot's detection), I have contacted bscheck.eu via twitter so hopefully they'll respond.
- Improve reliability (occasionally it can freeze)
- Use WebsocketProvider instead of HTTPProvider (faster so will snipe tokens quicker)
- Implement a feature that makes the bot only invest in tokens that have a certain amount of liquidity (ie. only invest in tokens that have min. 10 BNB liquidity)
- Implement a GUI? Maybe

 
- Improve honeypot detection (at the moment it is very simple and some tokens are rewriting their code to bypass the bot's detection), I have contacted bscheck.eu via twitter but they won't share their source code and admit their site is not always 100% correct.

- Look into rugpull detection
 
- Auto sell after certain profit reached?
 
- Make ETHTokenSniper that does the exact same but runs on the ethereum blockchain
 
- Are all tokens that haven't verified their source code bad? Probably not. But I'm currently just assuming that developers will verify their source code before adding liquidity. I can't tell if it's a scam or not if the source code isn't verified.
 
 - Also maybe an option to sell it at a certain price point. Look what happened to Refinable, a bot bought a huge chunk of the tokens and made an insane amount of money in a few minutes.

# If you’ve found this bot useful and have profited from it please consider donating any token to my BSC wallet address: 0xE75470B9a7c93038195ca116E342c42F6B3F758b

donation to geeks121 : 0xbeef1858cbddb48319893b028be9d914d45f51d9













# PHAROS TESTNET FULL AUTOMATIONS SCRIPT

### Description
Pharos testnet (Incentives) bot -- an automations python script to interact with the platfom like Check-in, Claim Faucet, Swap (All Pair), Add Liquidity (All Pair), send token, complete quest and Auto Referral.

![alt text](image/swap.png)


### Setup Instructions:
-  Python `3.7 or higher` (recommended 3.9 or 3.10 due to asyncio usage).

-  pip (Python package installer)

### Features
-  Multithread support: Run your bot faster (10 account with default setting completely in 5 minutes)

-  Faucet: Support auto claiming `official faucet`

-  Captcha Solver: Completing `captcha` for faucet

-  Check-in: Support Daily Checkin without missing a day

-  Proxy Support: Supports both mobile and regular proxies.

-  Auto Referral: Support to Register a new account with Referral

-  Wallet Handling: `Shuffle` wallets and `configure` pauses between operations.

-  Token Swaps: Supports `ALL PAIR` eg: `USDT-USDC, PHRS-USDT, PHRS-USDC, WPHRS-USDT, WPHRS-USDC` 

-  Liquidity : Support Deposit `ALL PAIR` eg: `USDT-USDC, WPHRS-USDT, WPHRS-USDC` 

-  WRAP/UNWRAP: Support Wrapping `PHRS to WPHRS` and Unwrapping `WPHRS to PHRS`

-  Quest Completion: Support automatic quest completions (must connect x)

-  Gas Refueling: Refill gas when it going to 0.

-  Access Token & User Agent: Support saving session for `AccessToken & UserAgent`

-  Configurable: You can setting all the things!

### Usage
#### Installation and startup

1. Clone this repository:
   ```bash
   git clone https://github.com/FckTestnet/pharos-testnet-bot.git
   ```
2. Navigate into the project directory:
   ```bash
   cd pharos-testnet-bot
   ```
3. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Add your Private Key on `private_key.txt`
   ```json
   your_private_key
   your_private_key
   ```
5. Add your Proxies on `proxies.txt`
   ```yaml
   http://login:pass@ip:port
   http://login:pass@ip:port
   ```
6. Add referral & wallet
   - Change `example.env` to `.env` and fill your referral code on `REF_CODE`
   - Fill the `wallet.txt` with your receiver token address
    
7. Run (first module, then second module):
   ```bash
    python main.py
   ```


### Configuration
All settings are in `.env`. Key options include:

#### General Settings
```yaml
ENABLE_DEBUG=true
BASE_URL="https://api.pharosnetwork.xyz"
RPC_URL="https://api.zan.top/node/v1/pharos/testnet/1761472bf26745488907477d23719fb5"
CHAIN_ID=688688
EXPLORER_URL="https://testnet.pharosscan.xyz/tx/"
```

#### Feature Settings
```yaml
AUTO_FAUCET=false

AUTO_LIQUIDITY=true
NUMBER_LIQUIDITY=1
AMOUNT_LIQUIDITY = [1, 5]  # This means 1%-5% of token0 will be used

AUTO_SEND=true
NUMBER_SEND=1
AMOUNT_SEND=[0.01,0.022]

AUTO_WRAP=false
AUTO_UNWRAP=true
NUMBER_WRAP_UNWRAP=1
AMOUNT_WRAP_UNWRAP=[0.1,0.21]

AUTO_SWAP=true
NUMBER_SWAP=1
AMOUNT_SWAP=[1,2]

AUTO_CHECKIN=true
```

#### Execution Setting
```yaml
REF_CODE="xxx"

DELAY_BETWEEN_REQUESTS=[5,15]
DELAY_TASK=[1,1]
DELAY_START_BOT=[3,10]
TIME_SLEEP=10

USE_PROXY=true 

MAX_THEADS=2

MAX_THEADS_NO_PROXY=1
```

#### Captcha Setting

```yaml
TYPE_CAPTCHA="2captcha"

API_KEY_CAPMONSTER="xxx"  
API_KEY_2CAPTCHA="xxx"  
API_KEY_ANTI_CAPTCHA="xxx"

CAPTCHA_URL="https://testnet.pharosnetwork.xyz/"
WEBSITE_KEY="6Lfx1iwrAAAAAJp_suDVjStYCUs0keW8tQ722uZR"
```


### Contributing

Submit pull requests or report issues. Ensure your code follows best practices.

### License

This project is open-source—modify and distribute as needed.

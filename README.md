### Summary

This documentation provides a comprehensive guide to creating an automated trading bot for placing trades in the UpVsDown game using the Playnance Game Token (USDP) or the Playnance Meme Token (USDB). The bot is designed to interact with a smart contract and automate trade placements based on a predefined strategy.


### Link to try out your strategy.

- https://bitprediction.fun/trade

#### Contents:

1. **Introduction**

   - **Overview:**
     In the UpVsDown game, the user can place trades by connecting their wallet, selecting the pool, choosing the investment amount, and clicking the UP or DOWN button during the place trade phase. The game consists of rounds, and each round has a time for placing trades and a time for expiry, depending on the selected pool.

   - **Purpose of the Bot:**
     If you are familiar with programming languages like Node.js, you can build a bot that will place trades automatically. The bot will use the private key of the wallet and place trades automatically according to your strategy. For placing trades, the bot will use a wallet address with USDP or USDB (depending on which pool it is running). You should fund the wallet with enough tokens. You can buy USDP with a credit card or bridge from other cryptocurrency.

   - **Example Code:**
     Under the `src` folder, there is a full example of a working bot that places trades with a random amount and random direction.
2. **Running the Bot**

   - **Example `.env` file:**
     ```plaintext
     RPC_PROVIDER=https://lb.drpc.org/ogrpc?network=playnance&dkey=AmsA2632Wk99pZ1Ym7OZe_uAtto4OHAR76bPhkHL9tz4
     PK=YOUR PRIVATE KEY
     ROUND_NOTIFICATIONS=wss://ds-proxy.playblock.io/sub?id=update_upvsdown_round_prod_v7_3
     SMART_CONTRACT_ADDRESS=0xAD8d5E8a201b49b2c7035Ea0f01875951297c213
     TOKEN_ADDRESS=0x73C3cDd1418c3F17D54A81148387d93122802E72
     POOL_ID=15:05:btc
     AVATAR_URL=https://storage.googleapis.com/betcioproduction/bit_logo.jpg
     COUNTRY_CODE=UK
     WHITE_LABEL_ID=75b94
     ```

     Keep the white label to get discounts on trading fees.

   - **Running the Bot with Docker:**
     To run the bot using Docker, follow these steps:

     1. **Build the Docker Image:**
        ```bash
        docker build -t trading-bot .
        ```

     2. **Run the Docker Container:**
        ```bash
        docker run --env-file .env trading-bot
        ```

     Ensure that you have the `.env` file in the same directory as your Dockerfile or provide the full path to the `.env` file.

3. **Configuration Parameters:**

   Detailed explanation of the configuration parameters:

   - **RPC_PROVIDER:** The RPC provider URL to interact with the PlayBlock chain.
   - **PK:** The private key of the wallet to be used for placing trades.
   - **ROUND_NOTIFICATIONS:** The WebSocket URL to listen for round phases. Trades can be placed only during the PlaceTradePhase.
   - **SMART_CONTRACT_ADDRESS:** The address of the smart contract used for placing trades.
   - **TOKEN_ADDRESS:** The address of the token contract (USDP or USDB).
   - **POOL_ID:** The ID of the pool where trades will be placed.
   - **AVATAR_URL:** URL of the avatar image to be used.
   - **COUNTRY_CODE:** The country code (ALPHA 2) of the user.
   - **WHITE_LABEL_ID:** The white label ID to be used (the default is 75b94).

   All the settings can be found here: [PlayBlock Game Tech Specs](https://github.com/josedasilva11/btc-binary-trading/blob/main/game_tech_specs/game_tech_specs.md)

4. **Advanced Usage**
   - With the provided example code, you can create different strategies, run multiple trades, and use USDP and USDB tokens on other pools.
   - The bot can be run locally or deployed to cloud providers like AWS, GCP, Azure, etc.
   - Best practice for storing the private key is using KMS and pulling the private key from there.

### Additional Information
- Every pool has a minimum and maximum investment setting. Ensure to adhere to these limits when configuring your bot.

________________________________________________________________________________
### Disclaimer

This automated trading bot is developed solely to facilitate access to the UpVsDown game platform. I am not promoting gambling, nor do I endorse any form of betting or trading activities. This bot is provided as a tool for users who wish to automate their trading strategies on the platform.

Please note:

- **No Promotion of Gambling:** This bot is not intended to encourage gambling. It is merely a technical solution for users who already participate in the UpVsDown game and wish to automate their trading process.
- **No Financial Advice:** I am not providing financial advice or trading strategies. The bot does not come with any pre-built strategies and any strategies implemented are entirely the responsibility of the user.
- **No Liability:** I do not take any responsibility for any financial losses or gains incurred while using this bot. The use of this bot is at your own risk.
- **No Share in Winnings or Losses:** I do not take any percentage of the winnings or losses. This bot is freely available and I do not benefit financially from its use.

By using this bot, you agree to take full responsibility for your trading activities and understand the risks involved in automated trading. Always trade responsibly and ensure that you are compliant with the laws and regulations of your jurisdiction.


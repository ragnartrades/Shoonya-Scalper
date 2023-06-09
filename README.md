Before proceeding, please read the entire document carefully.

After installing the Shoonya Scalper, navigate to the following directory: C:\ShoonyaScalper\Shoonya Scalper.

To ensure successful operation, populate the cred.yml file with valid credentials.

To modify the list of lots, please follow these steps:

Open the settings.yml file.
Locate the lots list.
Modify the list as desired.
Ensure that the indentation and spacing are maintained in the settings.yml file.
![image](https://user-images.githubusercontent.com/42057975/218642555-5bf8e9f9-c404-4683-a0f0-95153e3a59e5.png)

You can adjust the following settings:

SL Buffer: A negative value, such as -1, ensures that you offer to sell at a price one point lower than the SL trigger price. This improves the chance of order filling if the strike is illiquid.
Entry Buffer: If LMT is set as pricetype in settings.yml, you can use this to set the buffer. A negative value such as -1 means that the LMT order is placed at BestBuy-EntryBuffer. For example, if the LTP is 100 and the entry buffer is -1, the LMT order is placed at 99. The pricetype in settings.yml can be LMT or MKT. MKT places a market order and ignores the Entry Buffer setting.
SL Points: Stoploss in points. If set as 0, the SL and TSL features are disabled.
TSL Points: Stoploss is trailed by x points.
Target: Set the target in points. For example, if the target is 20 and the entry price is 100, the trade gets closed when the price reaches 120.
Lock Points (x) / Lock profit after (y): If the "lock profit after value" is more than 0, when LTP crosses y, the SL shifts to x points so that you lock some profit. For example, if SL is 20, TSL is 1, Lock Profit After is 10, and Lock Profit at is 5, when the LTP reaches 110 instead of the SL being at 90, it shifts the SL to 105. Now, 5 profit points are locked. Do not use this feature during high volatility.

![image](https://user-images.githubusercontent.com/42057975/218644556-1f8a9c87-08e7-4207-b5ae-35b84507ff9b.png)
To select the index, ATM offset, and lots, please follow these steps:

Use the panel above to set the risk management settings.
Select the index.

![image](https://user-images.githubusercontent.com/42057975/218645280-8e15fd1f-9136-4548-a439-52d576001ba2.png)

Set the ATM offset. This updates every 15 seconds based on the index move. -1 = ITM1 for both CE and PE. 1= OTM1 for both CE and PE.
Modify the lots in the settings.yml file.
Click the Long button to place a CE order or the Short button to place a PE order. The Straddle button creates a long straddle.
Remember that the risk management settings set in the panel above are considered for the trade, and any changes made later only affect the new trade.
To close all open positions, click the Exit All button. To cancel any open orders placed using an LMT order, click the Cancel All Open Orders button.

To view all open positions, use the panel above. To close an open position, select it and right-click on it. Alternatively, shift the SL to cost+1 (LTP should be higher than entry+1).

Please note the following:

TSL and relisting of open positions will not work if the app is restarted.
Ensure that you use a good internet connection or use this in a VPS environment.

If you are using the Telegram bot, please follow these instructions:
#https://medium.com/@ManHay_Hong/how-to-create-a-telegram-bot-and-send-messages-with-python-4cf314d9fa3e
#https://medium.com/@ganeshnagarvani/deploying-algorithmic-trading-strategy-part-3-telegram-updates-b22cd101a258


Paste the ID in the cred.yml file.
If you are not using the Telegram bot, please clear the field as follows:

telegrambottoken: ''
telegrambotchatId: ''
To generate a TOTP, please refer to this video: https://www.youtube.com/watch?v=yJi3SuQc_Xk.

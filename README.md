# Introduction
A chatbot is a communication software application that can store appropriate answers to questions on a server, create models that continuously develop correct answers through conversations with customers, control exceptions, and provide accurate answers (Hwang, S.; Kim, J., 2021). Chatbot, an interactive AI (where the user influences the system and the system influences the user), has been widely deployed in finance, retail, public, and manufacturing industries. Appleʹs Siri, Amazonʹs Alexa, Googleʹs OKgoogle, and Samsung Electronicsʹ Bixby are good examples of voice conversion personal assistant services (Karnam, M.,2019). A Chatbot for investing purposes is an interface that communicates with financial services to give information and advice to users. Chatbots are dominating the financial industry as a method of customer interaction. Established financial organizations are experimenting with chatbots, mainly in the retail banking, investment management, and wealth management sectors. Financial institutions have embraced this trend and experts predict that, within five years, bots will replace conventional online interfaces such as websites or mobile apps (Dasagrandhi, C. S., 2022). 

Investment Chatbot creates a dedicated relationship serving the investors with their investment management. The chatbot will crunch the numbers and do all the heavy lifting so that investors can focus their efforts on their investment (Botbot.AI, 2018). This service for the investor’s investments is tailored to the needs at any time of the day without worrying more about opening hours or having to consult investment personnel and enduring long waiting times.

# Why are Chatbots a More Significant Presence in Today’s Financial Environment?

Users sometimes have to invest a lot of time on the Internet to find relevant information regarding the investments in mutual funds, bonds, cryptocurrency, stocks, and portfolio management. To alleviate these problems, our Investment Chatbot is an innovative idea built on Dialogflow to provide personalized assistance in discovering important information about any type of investment, as well as help invest, forecast stock prices, and recommend the best investment strategies based on current market stock prices. It can be challenging for investors to maintain track of every stock, especially the ones they just want to monitor. There are potential chances that sometimes investors could miss out on a buy or a sell. So, it is important to build an Investment Chatbot to ensure proper management of their investment portfolio. Eventually, any investor can take advantage of such a multifunctional investment system to grow their wealth.

# Features
The objective of this project is to develop an Investment Chatbot that can assist users to learn how to invest wisely and provide a convenient approach to gather the necessary information and make proper financial investment decisions. The chatbot is task-oriented, which focuses on the pre-defined investment tasks and responds to very specific investment commands. The Investment Chatbot consists of four main components:

* Investment Education
  
  One of the most essential features of the investment chatbot is to provide definitions and tutorials for different investment options to users since not everyone has the financial knowledge and experience to make investment decisions. This chatbot can help users to learn different types of investment and provide them with plenty of additional resources for further learning. Whether it is mutual funds, bonds, stocks, or cryptocurrency, the Investment Chatbot can provide all aspects of information to assist users to make the right financial moves and planning for the future.

* Information Retrieval

  The investment chatbot provides information retrieval services such as suggestions for investment tools and real-time stock price querying. Even though the users have never invested a dollar or are already experienced investors, they can take advantage of the information retrieval feature. First-time investors can retrieve information on useful investment tools and start their journey. On the other hand, the stock price checking feature provides traders and active investors with more accurate information reflecting the market such as High Price, Low Price, Open Price, and Close Price of the stocks. The chatbot will display all the necessary information to support their financial decisions in real-time.

* Stock Price Forecasting
  
  The investment chatbot also provides stock price prediction services for S&P500 stocks. Forecasting the stock market's opening moves can be a useful tool. Investors can query about the particular stock they are interested in and get the forecast value for the next five days before making their decision to buy or sell, especially for the swing traders. 


* Stock Recommendation

  On any particular day, when the users want a recommendation for any S&P500 stocks, the chatbot shortlists the stocks to trade based on technical indicators such as ‘Based on Relative Strength Index (RSI)’ and ‘Based on Volume.’ Technical indicators are tools that help analyze the movement in the stock prices and whether the ongoing trend is either going to continue or reverse. It helps the traders make buy or sell a particular stock of interest. 
  
# Methodology
The investment chatbot leverages machine learning and NLP algorithms to meet the expected features mentioned above. The development process consists of five steps:

* Chatbot Development

  The foundation of the system is to build a chatbot agent that can understand natural human language and provide the requested information. Instead of building our own agent from scratch, we decided to utilize Dialogflow, an existing chatbot development platform powered by Google, to build the conversational agent for the system. Similar to building the chatbot by using NLP tools, Dialogflow offers a friendly user interface to define the key components of a Chatbot such as Agent, Intents, Entities, and Fulfillment (D3Vtech, 2021). Besides, it utilizes Google's machine learning models and NLP to train the agent once we predefined the mentioned components. 

  The following NLP techniques are used by Dialogflow to enable the chatbot to process human conversations:
  1.	POS Tagging - to identify entities in the user input sentence.
  2.	Tokenization - to split the text into meaningful words.
  3.	Stemming - to reduce inflected words to their base form.
  4.	Stop Words - to filter out high-frequency words from the user input sentence.
  5.	Term Reinforcement - to give higher weight to certain phrases in a sentence.
  
  For chatbot deployment, because Dialogflow is fully integrated with ‘Google Assistant,’ we decided to take advantage of the voice chat functionality and deploy the investment chatbot to ‘Google Assistant.’ Thus, the chatbot can handle either text-based or voice-based communication.

* Chatbot Fulfillment and Webhook

  The regular chatbot can handle the general rule-based conversion. However, for our project, it cannot answer questions related to real-time stock queries and stock price prediction. For these scenarios, chatbot fulfillment and webhook need to be built. Fulfillment is a key component of a chatbot that allows an agent to take actions based on the user’s expression and send dynamic responses. In our case, we want the chatbot to send dynamic responses regarding stock prices, stock predictions, and recommendations.
  Since Dialogflow supports the fulfillment feature, a webhook application is developed by using Python with Flask Framework. Besides, we set up a cloud environment in ‘Pythonanywhere,’ a web hosting service, and host the webhook application there. Thus, if users request sophisticated responses like real-time stock price and machine learning model results, the chatbot can send a request with user input entities to our webhook, then the webhook will perform necessary actions and send back the result.

* Text Summarization

  In order to train our chatbot to respond and provide the requested knowledge for investment, web scraping and text summarization techniques are applied for developing this chatbot. Web scraping can collect the required content of different investment options from authoritative investment websites. Then, to provide concise investment educational content for the users, the text summarization model can extract the essential information from the scraped content.
  In our project, we have carried out web scraping using BeautifulSoup, text cleaning, and text summarization using Gensim summarization. Gensim summarization works with the TextRank algorithm. This algorithm utilizes the extractive text summarization technique to examine the original text and extract the highest-ranked sentence based on the sentence similarity. Thus, it best conveys the ideas contained in the text without losing too much meaning. If users want to learn more beyond the summary, they can access the original content by redirecting to the external website link provided on the chatbot interface.

* Stock Price Forecasting

  It is important to make the data stationary before we can us the Autoregressive Integrated Moving Average (ARIMA) model. The ARIMA model has been widely utilized in banking and economics since it is recognized to be reliable, efficient, and capable of predicting short-term share market movements (Dhaduk, H., 2021). In our Investment Chatbot, we use the historical data of S&P500 stocks collected from ‘Yahoo Finance API’ to forecast the stock prices. The ARIMA model is trained for S&P500 ‘Close Price’ data for the duration of 2 years. The model forecasts the Close Prices of the stock for the next 5 days and returns the result to the user in the form of a table. 

* Stock Recommendation

  The Stock Recommendation feature is designed so that the investor can make an informed decision after getting the recommended stocks and their close price/volume (based on a selected indicator). It shows the present movement of stocks in the stock market. In our Investment Chatbot, we used the historical data of S&P500 stocks collected from ‘Yahoo Finance API’ to recommend the stocks based on technical indicators RSI and Volume. RSI is a Relative Strength Indicator essentially used as a momentum indicator.  It measures the magnitude of recent price changes to evaluate overbought or oversold conditions in the price of a stock (Fernando, 2022). The RSI is displayed as an oscillator and can have a magnitude of momentum from 0 to 100. Trading volume is a measure of how much a given financial asset has traded in a period of time (Mitchell, C., 2022). For stocks, volume is measured in the number of shares traded. 
  In our Investment Chatbot, we recommend stocks with RSI less than 30 (Oversold stocks) and the stocks with a higher average volume over the last 2 years in the sampled data.

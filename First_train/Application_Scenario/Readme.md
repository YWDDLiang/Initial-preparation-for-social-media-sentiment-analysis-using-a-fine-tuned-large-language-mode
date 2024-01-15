# Application Scenario
This project integrating Alpaca-LoRA to fine-tune the LlaMA2 model revolutionizes how journalists decipher social media sentiment. This study collects real-time data from virtual currencies and forums and processes them to make them fit the needs of the model. Alpaca-LoRA steps in, optimizing the LlaMA2 model to grasp the nuances of social media discourse, amplifying its relevance in sentiment analysis. The model undergoes a meticulous fine-tuning process, absorbing key insights from the adapted framework. This cutting-edge methodology not only refines large language models but reshapes the approach to dissecting social media sentiments related to news events. Journalists now access a tool that swiftly decodes public reactions, aiding in crafting more resonant stories. Moreover, researchers find a goldmine for social studies, unraveling the intricate tapestry of societal responses to news through these refined sentiment analyses.

Our raw input variables: The historical time-series data of the monetary value of Aave, and the tweets with specific hashtags.
  - **Cryptocurrency Data**: Our data set comprises daily market prices (AAVE–USD exchange rates) from [Alpha Vantage API](https://www.alphavantage.co/documentation/#currency-daily). We include open price, high price, low price, close price, and daily volume of AAVE from Oct 2020 to Dec 2022 in the dataset.
  - **Social Media Data**:  We collect tweets that contained the hashtag (#Aave/#AAVE) from [Snscrape API](https://github.com/JustAnotherArchivist/snscrape). The timestamp is also from Oct 2020 to Dec 2022.
# Telegram Chat Bot History Explorer

# Problem Statement:
1. Write a Telegram Chat bot that logs discussions to a database. Telegram bots are special Telegram accounts, please read https://core.telegram.org/bots. Telegram bot API is defined in https://core.telegram.org/bots/api.

2. Implement a service that provides REST API to perform filtered search for the discussion history. Ideally API should allow searching at least by user, date and provide also free text search.

3. Web UI for the search.

# Solution:

**Telegram Bot details**

**Name** - Telegram chat Bot

**Username** - @message_detector_bot

Telegram bot API Provides two Methods to Receive data.

1.getupdates()
  - This API helps to retrieve from Telegram database. But we have to keep on polling to get contents.

2.setWebHook()
-  This method sends an HTTPS POST request to the specified url, containing a JSON-serialized Update. In case of an unsuccessful request, This makes reasonable amount of attempts.

-       setWebHook
https://api.telegram.org/bot367274256:AAFh1eeLfF8QIqC7XH0KcoR4pIIK7o_7Y_k/setWebhook?url=https://vast-dusk-62970.herokuapp.com/crawl/store

-       deleteWebHook
https://api.telegram.org/bot367274256:AAFh1eeLfF8QIqC7XH0KcoR4pIIK7o_7Y_k/deleteWebhook?url=https://vast-dusk-62970.herokuapp.com/crawl/store

**REST APIs**

-       ExploreByKeyword 
https://blooming-eyrie-34141.herokuapp.com/v1/search/exploreByKeyword/

Sample Request:
{
"keyword": "Good"
}


-       ExploreByUserName 
https://blooming-eyrie-34141.herokuapp.com/v1/search/exploreByUserName/

Sample Request:
{
"username": "s_kalai"
}


-       ExploreByDate

https://blooming-eyrie-34141.herokuapp.com/v1/search/exploreByDate/

Sample Request:
{
"query_date": "2017/04/09"
}


**Heroku Application** 

https://blooming-eyrie-34141.herokuapp.com/

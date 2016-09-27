Measure What You Want to Imporve  
第一節  
作者以他在google的search team的經驗，講述metric的重要  
  
  
Goolge search面臨到的問題是說，如何知道用戶用的開不開心，喜不喜歡  
開心是一個很抽象的概念，用戶通常search可愛狗狗的話，通常想要看到的是圖片；search中國和美國的關係的話，想看到的是新聞  
search餐廳名稱的話，想要看到的是地圖以及評價，種類繁多，到底用戶怎麼樣的行為，他才是覺得開心？  
最後他們歸納出一個關鍵的行為：long clicks，假如用戶滿意search result的話，他就會停留在search完的頁面很長的一段時間  
如果用戶不開心的話，他就會回到search頁面，點擊其他結果，或者換關鍵字，這個long clicks就是他們的key metrics  
  
  
本章重點在於介紹什麼是metrics, 他的重要性，以及如何挑選，引導到我們在安排task的時候，如果有好的metrics的話  
更能全面的知道目前的狀況，進而安排事情的輕重緩急  
  
  
  
  
第二節  
Use Metrics to Driven Progress  
Metrics好棒棒，可以幫你  
1. 找到對的事情  
2. 減少未來regression test的次數  
3. 規劃未來的progress  
4. 測量工作的effectiveness  
雖然量化metrics，並不是這麼簡單  
有些明顯的bugs，修完之後，輕易的看出改善的結果  
有些system level的bug，影響的是長遠的效能  
並不是說很難去測量metrics的話，就代表那件事情不值得去做，只是你沒有找到好的量測方法而已  
  
  
常常問自己下面這兩個問題  
1. Is there some way to measure the progress of what I am doing?  
2. If a task I'm working on doesn't move a core metric, is it worth doing? Or is there a missing key metric?  
  
  
  
  
第三節  
Pick the Right Metric to Incentivize the Behavior You want  
選對Metrics很重要，本節在講如何選對好的Metrics  
給個例子，什麼是好的Metrics  
1. Hours worked per week vs. productivity per week.  
2. Click-through rates vs. long click-through rates.  
3. Average response times vs. 95th or 99th percentile reponse time.  
4. Bugs fixed vs. bugs outstanding.  
5. Registered users vs. weekly growth rate of registered users.  
6. Weekly active users vs. weekly active rate by age of cohort.  
  
  
挑選Metrics的三個指標  
1. maximize impact  
  看你的目標是什麼，選對於目標有最大影響的metrics  
2. actionable  
  其實沒有很確定他講的是什麼，他說這個指標指的是平常team努力的成效  
  像是page views, signup conversion rate, the percentage of registered users that are actively weekly over time  
  指是應該是平常一些明顯的量化指標  
3. responsive  
  可以快速看出結果的指標，像是某個改變是對用戶有正面或者負面的影響  
  像是track每小時performance的改變，但是這個track切記要robust  
  像是track每分鐘performance的改變，就沒有什麼意義了，因為變動性太大了  
  
  
好好選對Metrics吧  
  
  
第四節  
Instrument Everything to Understand What's Going On  
Dashboard很重要，有好的工具可以即時監測目前的Metrics正不正常  
  
  
dashboard tool  
Etsy: Graphite, StatsD  
Google: Borgmon  
Twitter: Observability  
LinkedIn: inGraphs  
Open-source: Graphite, StatsD, InfluxDB, Ganglia, Nagios, Munin  
New Relic, AppDynamics  
  
  
第五節  
Internalize Useful Numbers  
知道一些關鍵的數值很重要，可以幫助你快速評估目前的狀況  
假如你要建立一個系統的話，要是你知道一些數值，像是平均從Memory讀取1MB的資料，大概要花250us  
、平均從硬碟讀取1MB的資料，大概要花30ms、平均從網路讀取1MB的資料，大概要花10ms  
你可以就快速粗估整個系統所會花費的平均執行時間，然後比較已經建立好的系統的執行時間  
可以大略的知道問題是出在哪邊  
作者提供了大略幾個數值，可以觀察並紀錄  
1. the number of registered users, weekly active users, and monthly users  
2. the number of requests per second  
3. the amount and total capacity of data stored  
4. the amount of data written and accessed daily  
5. the number of servers needed to support a given service  
6. the throughput of different services or endpoints  
7. the growth rate of traffic  
8. the average page load time  
9. the distribution of traffic across different parts of a product  
10.the distribution of traffic across web browsers, mobile devices, and operating system versions  
  
  
第六節  
Be Skeptical about Data Integrity  
引用數據 -&gt; 驗證並調整方向 -&gt; 好的結果  
用到錯誤的數據 -&gt; 災難的發生  
我們習慣用自己喜歡的方式去詮釋資料，容易造成了非常大的誤解  
所以我們要隨時的去懷疑我們觀察到的數據到底是正不正確的  
錯誤的數據比沒有數據還要差勁  
通常大家都會很輕忽數據正不正確的原因有三點  
1. deadline很趕  
2. 只有驗證happy case  
3. 我有寫unit test, 不會有錯的啦  
  
  
作者列了幾個方法來提高數據的可靠度  
1. Log data liberally, in case it turns out to be useful lateron.  
2. Build tools to iterate on data accuracy sooner.  
3. Write end-to-end integration tests to validate your entire analytics pipeline.  
4. Examine collected data sonner.  
5. Cross-validate data accuracy by computing the same metric in multiple ways.  
6. When a number does look off, dig in to it early.

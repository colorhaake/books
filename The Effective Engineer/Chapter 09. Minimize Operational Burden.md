Minimize Operational Burden  
  
  
Instagram剛上架的時候，在短短幾個小時之內，下載數量就超過10000次；在接下來的幾個月，用戶數量爆增  
一年半以後，Facebook以1B的價格收購了Instagram，用戶數達到40M  
  
  
但是在Instagram被收購的時候，整個公司居然只有13個員工，他們是怎麼做到在短短一年半的期間，來應付高達40M使用者的服務？  
他們在開發的過程當中，需要應付：  
  
  
1. 保持系統運行  
2. 擴大系統來支援更多的使用者  
3. 解決bugs  
4. 新進員工的教育  
  
  
為了降低開發及維護的成本，他們選擇了最穩定的做法，例如選擇可靠穩定的解決技術，而不是最新最熱門的方法；因為可以降底維護新技術的成本  
像是他不用最新流行的NoSQL，而是選擇傳統的PostgreSQL, Memcache及Redis  
  
  
本章目的在講的是如何最小化執行時所會遇到的成本  
  
  
  
  
Embrace Operational Simplicity  
  
  
當產品逐漸成長的時候，為了應付隨之而來的流量，系統也會愈變愈複雜來提升流量的需求、反應的速度及品質  
新的架構、程式語言或者工具，可以用來改善前句描述的痛點，可能會被工程師們多加考慮使用。  
  
  
用新的東西，固然有好有壞；好的是可以解決當前的問題；壞的是也會引申許多接續的問題。  
比如說：  
1. Engineering expertise gets splintered acros multiple systems.  
2. Increased complexity introduces more potential single points of failure.  
3. New engineers face a steeper learning curve when learning and understanding the new systems.  
4. Effort towards improving abstractions, libraries, and tools gets diluted across the different systems.  
  
  
選擇一個最簡單的解決方案，既可解決當前的問題，也可以處理後續維護的問題，才是答案  
  
  
Steve Jobs曾說過 "When you first start off trying to solve a problem, the first solutions you come up with are very complex, and most people stop there. But if you keep going, and live with the problem and peel more layers of the onion off, you can oftentimes arrive at some very elegant and simple solutions. Most people just don't put in the time or energy to get there"  
  
  
這一節的重點簡單說就是：用新東西固然爽爽，但是維護及學習成本可能很高，用傳統的解法看似麻煩，或許你只是沒仔細思考而已，另外的成本可能不會像新東西那麼高  
  
  
  
  
  
  
Build Systems to Fail Fast  
大部分的工程師把Crash當作是系統穩定度的一個指標，因此盡可能用很多種方法的讓系統不會Crash  
比如說接受到格式不對的欄位，就轉為預設值；try catch所有的exception  
但是這種方法只會讓你的系統晚點failed，因為你沒有解決真正的問題，這種做法只是迴避問題而已，資料還是錯的  
使用者最後還是會發現，雖然系統沒有crash，但是資料是有問題。  
並且這種迴避的方法會讓你更難發現哪邊有問題，很多的try catch，反而是更難往回找真正發現crash的地方；  
log系統忽略所有有問題的資料，只看結果很難發現哪裡出了問題。  
  
  
如何解決這種問題？答案就是：就直接讓他crash吧！只有讓系統crash，你才會發現盡早發現哪邊出了問題；也方便讓工程師容易的找到源頭。  
這種測試方法稱作為failing test，舉例來說  
1. Crashing at startup time when encountering configuraiton errors  
2. Validating software inputs, particularly if they won't be consumed until much later  
3. Bubbling up an error from an external service that you don't know how to handle, rather than swallowing it.  
4. Throwing an exception as soon as possible when certain modifications to a data structure, like a collection, would render dependent data structures, like an iterator, unusable  
5. Throwing an exception if key data structures have been corrupted rather than propagating that corruption further within the system  
6. Asserting that key invariants hold before or after complex logic flows and attaching sufficiently descriptive failure messages.  
7. Alerting engineers about any invalid or inconsistent program stae as early as possible  
  
  
也是不讓真正上線的時候，要讓使用者遇到crash；有個混合的方法就是，產了一個最外層的cather，只要最外層的cather收到exception的話  
就用log把他給記錄下來，並且回傳到開發者的身上，在介面上提供訊息，請使用者重新啟動或者什麼的，那你就可以讓使用者不會遇到crash，並且知道發生exception的地方  
  
  
  
  
Relentlessly Automate Mechanical Tasks  
開發自動化腳本去降低手動的成本  
一般工程師都做不到的原因大概為：  
1. They don't have the time right now.  
2. They suffere from the tragedy of the commons.  
  人很多的話，每個人輪到的時間很短  
3. They lack familiarity with automation tools.  
4. They underestimate the future frequency of the task.  
5. They don't internalize the time savings over a long time horizon.  
  可能覺得手動花個10s就解決了，但是一旦次數增加，利用自動化可以節省更多時間  
  
  
但是開發自動化程式還是需要經過仔細考慮  
因為他前期的開發成本還是過高  
  
  
Two types of automation:  
1. Automating the mechanics of a sequence of steps tends to be straightforward and testable.  
2. Automating the right decisions to make, particularly in the context of building systems that can heal and repair themselves when things go wrong, turns out to be much more challenging.  
  
  
  
  
  
  
Make Batch Processes Idempotent  
  
  
如果決定要撰寫自動化腳本的話，盡可能的讓你的腳本能夠Idempotent  
Idempotent指的是，無論執行多少次，執行結果都有一樣；就算執行的過程當中發生了錯誤，腳本也盡可能的重試，或者修復那些錯誤  
  
  
如果撰寫Idempotent的腳本成本太高的話，那就次一級，考慮讓你的腳本能夠retryable或者reentrant  
一個retryable或者reentrant的腳本指的是，當你腳本執行到一半的時候，就算忽然中斷出去執行別的命令，回來繼續執行的結果還會是一樣的  
因為有些腳本執行的時候會汙染了全域的狀態，當系統中斷出去執行指令的時候，又會破壞那些狀態，因此導致回來繼續執行腳本的結果會是錯誤的  
  
  
另外就是需要執行時間非常長或者執行頻率比較低的腳本，盡可能的盡可能的重試，或者修復那些錯誤  
  
  
如果撰寫Idempotent的腳本成本太高的話，那就次一級，考慮讓你的腳本能夠retryable或者reentrant  
一個retryable或者reentrant的腳本指的是，當你腳本執行到一半的時候，就算忽然中斷出去執行別的命令，回來繼續執行的結果還會是一樣的  
因為 t³本執行的時候會汙染了全域的狀態，當系統中斷出去執行指令的時候，又會破壞那些狀態，因此導致回來繼續執行腳本的結果會是錯誤的  
  
  
另外就是需要執行時間非常長或者執行頻率比較低的腳本，盡可能的盡可能的重試，或者修復那些錯誤  
  
  
如果撰寫Idempotent的腳本成本障，或者是故意讓某些service被killed掉，遇到這種該怎麼處理。  
愈是去探清那些不確定性，愈能減少系統出現錯誤，或者增快回復的速度。  
我個人覺得這個本來就是一般QA必須去測試了解的部分。  
  
  
Key Takeaways  
1. Do the simple thing first.  
2. Fail fast to pinpoint the source of errors.  
3. Automate machanics over decision-making  
4. Aim for idempotence and reentrancy  
5. Plan and practice failure modes.

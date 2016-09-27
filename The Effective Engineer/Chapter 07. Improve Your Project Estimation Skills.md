第一節  
Ooyala曾經想要提升video player的效能和穩定性，決定花費4個月的時間，重新撰寫video player  
評估上來說，需要花費4個月的時間，但是實際執行上遇到了：任務指派不明確，居然有同一個人同時要去處理兩個專案  
；用來做資料分析的工作Thirft，沒有支援ActionScript，所以要花費時間撰寫compiler；Adobe's core module對於整理video state是buffering或者playing不明確。諸如此類的疑難雜症，導致他們花了9月的時間才完成。這段期間，許多所有的事情，像是新feature的開發  
都沒有辦法執行。後來發現原來不只Ooyala有同樣的問題，Windows Vista拖延了3年、Netscape 5.0 delay了2年、Daikatana原本7個月內要上線，拖了好幾次  
本章是在講述專案評估的重要性，如果你發現專案上線的時間會比一開始評估的時間還要長的話，那你是不是會改變策略，像是減少專案的幅度，漸進式的在把功能補齊等等方式來減少問題。  




Use Accurate Estimated to Drive Project Planning  
一個好的評估在於：  
"A good estimate is an estimate that provides a clear enough view of the project reality to allow the project to hit its tragets"  


如果評估的時間和老闆期望的時間是不一樣的，該怎麼處理？  
如果老闆或者客戶很愛加feature或者改spec.怎麼辦？  




預估的時間幾乎會比實作的時間還長  
因為有的時候會怕評估的時間過長，老闆會問為什麼  
所以通常預估的都是理想的時間，而不是考慮到有一定的機率會遇到問題  
然後會花過長的時間  


平均一天會專心花在工作的時數：4個小時  
所以以一天4個小時間方式去預估專案所會花費的所有時間  


下列這些方法可以來幫助提高評估專案所花費時間的準確度  
1. Decompose the project into granular tasks.  
通常一次評估龐大的專案的執行時間，一定會不準，把他拆成好幾個小的任務來評估會比較準確  


2. Estimate based on how long tasks will take, not on how long you or someone else wants them to take  
真的是去評估真正的執行時間，而不是老闆想要的deadline  


3. Think of estimates as probaility distributions, not best-case scenarios.  
因為專案還沒開始，有太多的不確定性了，與其給於固定的完成時間，不如真正的跟他說最好的情況以及最壞的情況所需要的時間  
不過通常老闆要的是一個固定的時間，所以要如何去讓老闆了解，也是一個難題  
"There's a 50% likelihood that we can deliver the feature 4 weeks from now, and a 90% chance that we can deliver it within 8 weeks"  
會被老闆幹爆的  


4. Let the person doing the actual task make the estimate.  
讓真正在做事的人去評估時間，而不是老闆或者專案經理去算  


5. Beware of anchoring bias.  
老闆自行估一個時間出來，要你研究看看，但是通常我們會受到那個數字的影響，來加減一點時間，當作自己的評估時間  
而不是真的專案可能的執行時間  


6. Use multiple approaches to estimate the same task.  
7. Beware the mythical man-month  
"Don't assume that adding more people will shorten a project timeline"  


8. Validate estimated against historical data.  
用歷史資料來評估不一定會準，上一季成長25%，不代表下一季同樣有機會會成長25%  


9. Use timeboxing to constrain tasks that can grow in scope.  
不是評估這件事會需要花費多少時間，而是算說我有一個固定的時間，可以做多少事  


10. Allow others to challenge estimates  
通常老闆第一個會質疑你  


就是因為專案還沒開始，有太多的不確定性。根據經驗法則，你可以把預估的時間x2來當作真正的執行時間  
然後依照這次執行的結果和預估的做比較，來調整下一次專案執行時間的評估  






Budget for the Unknown  
專案的進行中有太多的未知數了，並不是說評估一個月會完成的工作，真的是每天每個小時都在進行工作  
有太多太多的interruption在干擾專案的進行  
比如說：同事生病沒有辦法工作、server因為要進行維護，所以沒有辦法存取、老闆叫你去面試新人，帶新人、開會等等  
也有正向的未知數可以幫忙專案進行，像是：寫unit test、統一coding style、採用別人寫好的library等等  
這些總總都是一般在評估專案的時候，沒有考慮進去的。  
所以說在評估專案的時候，更要考慮這些不確定性。以Asana來說，他們把預估一天會完成的工作，把他當成兩天才會完成  
多的那一天就是為了那未知數。  






Define Specific Project Goals and Measurable Milestones  
"Define specific goals to reduce risk and efficiently allocate time, and outline milestones to track progress. This allows us to build alignment around what tasks can be deferred and decreases the chance that a project inadvertently grows in scope"  




Reduce Risk Early  
專案剛開始的時候一定會有許多的不確定存在，例如這樣的功能設計，不知道到最後會不會有問題；為了避免最後才發現有這個問題  
也就是說要及早發現及早治療，如果可以及早的獲得可更多的資訊，那些不確定性就可以降低了  
比如說盡早的撰寫end-to-end testing就可以避免system integration的時間  




Approach Rewrite Projects with Extreme Caution  
"Trying to rewrite stuff from scratch - that's the cardinal sin."  
工程師很容易犯的錯之一就是看到不太懂的code，或者邏輯很複雜的code，就想要從頭重新寫一份  
這不僅花費時間，專案的進度停滯，甚至會產生一堆的bug  
如果可以的話，嘗試去refactor，而不是重寫  
真的要重寫的話，就用incremental rewrite的方式去重寫，這樣一來好處就是可以同時去撰寫新的功能，解決bug  
專案還是可以繼續進行下去  
不過有可能沒有辦法incremental rewrite  
所以就要明確的把事情分各個階段，step 1, step 2, ...  
每個step都有他的milestone  




Don't Sprint in the Middle of a Marathon  
Sprint是只能用到專案的最後一個時刻，意思就是衝刺到終點  
如果你在專案進行到一半的時候，就進行衝刺，每週工程由40個小時，增加25%，到50個小時  
但這不代表會增加25%的產出，因為人員是會累的  
每當工時逐漸增加，效率也會跟著降低，反而犯錯機率會提高  
並且員工們犧牲休息時間來工作，減少時間去陪伴家人、情人或者休息，反而會增加對於團隊的不信任感  
總而言之，除非你到了專案的最後一刻，或者說專案delay的話，後果非常嚴重；不然的話，盡量不要這樣做  
如果必須sprint的話，那就要確保：  
1. 每個人都要知道delay的原因及後果  
2. 重訂實際的sprint計劃  
3. 如果sprint完還是會delay的話，那就可能要準備放棄sprint，改訂定別的計劃  




Key Takeaways  
1. Incorporate estimates into the project plan  
2. Allow buffer room for the unknown in the schedule  
3. Define measurable milestones  
4. Do the riskiest tasks first  
5. Know the limits of overtime

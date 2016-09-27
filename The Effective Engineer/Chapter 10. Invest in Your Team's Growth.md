Effective engineer不單單只評估你在工作上的效率，而是也會計算你對於整個團隊的影響力  

You're a staff engineer if you're making a whole team better than it would be otherwise.  
You're a principal engineer if you're making the whole company better than it would be otherwise.  
You're a distinguished if you're improving the industry.  


畢竟人們會比較傾向於相信一個來自於成功公司/團隊的工程師；而不是來自失敗/沒名氣的公司  


作者也感悟到當他剛從Google離開，加入到新創團隊Ooyala的時候，面對於不熟悉的程式語言、專案的技術債、緊迫的Deadline  
讓他每週花了80個小時的工作時間，才完成兩週內要交付的任務。如果那個時候有更好的Onboarding流程，可以使新進的員工更能了解公司的工作上的環境及流程的話，那就可以增加整個團隊的生產力。  


所以說投資在團隊的onboarding流程，也就是團隊的成長來說，是一項非常有報酬的任務  
本章的目的在於介紹說，如何促使整個團隊的成長  

Make Hiring Everyone's Responsibility  
面試對於工程師來說是一個冗長、麻煩又花費時間的東西，讓人無法專心在專案身上，面試完還要鉅細彌遺的記錄每個面試者的特點，符不符合公司的期待  
但對於一個公司來說，面試是一個有非常高leverge的工作，他可以幫助工程師的效率提高。怎麼說呢？  
如果專注在找好的工程師 -&gt; 每年公司的產能可以增加2000多小時  
找到一般或者不適合的人 -&gt; 產生低落，又要花費時間處理人事問題  
人事問題可不是用機器自動能夠處理的問題  


下一步就是說，既然面試是一個高leverage的事情，但是又相對的花費時間  
那我們要如何設計一個高效率的面試流程呢？  


首先先來想一下面試的目標是在哪邊？作者認為一個好的面試是要達到兩點目標  
1. 反映出面試者的特質，是不是對於團隊的成長有幫助  
2. 讓面試者可以喜歡整個團隊、任務以及文化。就算面試者沒有辦法得到offer，他也會推薦其他人來這邊面試  

為了有效率的達到這個目標，你必須把你要問的問題或者面試的題目設計成具有 high signal-to-noise  
換句話說就是每分鐘面試者所回答的資訊(signal)，是可以滿足上述要達到的兩點目標，略帶一些比較不相關的東西(noise)  

傳統一般的大公司像是Google, Microsoft, Facebbok和Amazon會要求面試者在白板上回答一些演算法和程式設計的問題  
但是這種制式的問題通常只能反映出面試者的computer science的知識而已，不能知道是不是真正在工作上面，可以確實的把任務完成  

近年來一些公司逐漸把面試的題目改成實際的上機測驗。給你一個題目跟一台筆電，你可以用任何方法 google, open source tool, stackoverflow  
等等方法來解決問題，考驗你解決問題的能力、debug技巧、code的組織與架構  

另外作者分享了他面試超過500次的經驗來說，一些有用的面試技巧為  
1. 花時間和你的團隊討論什麼樣的特質是團隊所要的，例如coding aptitude, mastery of programming languages, algorithms, data structures, product skills, debugging communication skills, culture fit等等  
2. Iterate你的面試流程，是否還需要改進的地方  
3.設計不同難度的問題，當覺得某些題目對於面試者來說太難的話，立刻換次一級的題目給他，針對他目前感覺到的能力，找幾個適合他的題目，來測驗他真正的能力。另外也可以建位一個面試題目的資料庫，可以快速搜尋題目  
4. 掌控好面試的步調，不可以讓面試者太輕鬆、也不可以讓他卡太久；可以給予他一點提示，讓他可以繼續往下進行  
5. 穿插一些重要並且答案很短的題目  
6. 找另外其他team的同事來一起面試  
7. 也可以用一些非傳統的方式來面試，來試試面試者是不是符合公司的其他需求  

Design a Good Onboarding Process  
一個好的onboarding program可以讓新進員工  
1. 更快了解開發流程及環境  
2. 快進上手，有產出  
3. 更了解學習的方向  
4. Mentor可以把一些冗雜的事先給新進員工練習，而可以更專注在更重要的工作上面  

一個不好的onboarding program會讓  
1. 整個團隊的效率降低  
2. Code quality下降，假如新進員工用錯abstractions或tools，或者不熟悉coding style  
3. 新進員工會花太多時間在讀document跟design  
4. 難辨認新進員工是本來工作效率就低，還是只是因為不熱悉工程流程跟環境  
5. 新進員工表現不好，壓力也會跟著來  

一個重點：Investing in your team's success means that you are more likely to succeed as well.  

如何創造一個好的onboarding流程：  
1. identify the goals that your team wants to achieve.  
2. construct a set of mechanisms to accomplish these goals.  

無論你的資歷如何，你都可以為onboarding program提出建議  

作者參考了Google's EngEDU training program和Facebook's 6-week Bootcamp onboarding program 來編製Quora的onboarding program  

Quora's onboarding program的四個目標：  
1. Ramp up new engineers as quickly as possible.  
2. Impart the team's culture and values.  
3. Expose new engineers to the breadth of fundamentals needed to succeed.  
4. Sociallly integrate new engineers onto the team.  

針對這四個目標，Quora onboarding program建立了四個主要流程  

1. Codelabs  
為自己的產品建立了一個實驗環境，裡面包含文件說明軟體的架構、程式的抽象是怎麼做的  
新進員工可以練習組織一下從頭到尾建立整個產品  
2. Onboarding talks  
3. Mentorship  
4. Starter tasks  

最後Building a good onboarding program is an iterative process.  

Share Ownership of Code  
並不是成為一個唯一能夠對產品負責的人，才能突顯出你的價值  
遇到緊急狀況的時候，你也會變成唯一火在燒的人  

試著去讓其他人也可以一起分擔產品的責任  
"Any one thing can be done by multiple people, and that allows you more degress of freedom, more flexibility in development , and fewer constraints for on-call and support"  

如何做到share ownership of code，作者列了一些方法  
1. Avoid on-person teams.  
2. Review each other's code and software designs.  
3. Rotate different types of tasks and responsibilities across the team.  
4. Keep code readable and code quality high.  
5. Present tech talks on software decisions and architecture.  
6. Document your software, either through high-level design documents or in code-level comments.  
7. Document the complex workflows or non-obvious workarounds necessary for you to get things done.  
8. Invest time in teaching and mentoring other team members.  

Build Collective Wisdom through Post-Mortems  
通常我們一直在忙著專案的進行，一個專案結束之後，緊接著下一個專案，卻忘了事後檢討上一個專案進行的成效。  
事後檢討並不是批鬥大會，而是仔細的分析好的地方以及不好之處。好的結果繼續維持下去，壞的地方研究如何改善。  
沒有最好，只有更好  

要達到最好的檢討品質，  
首先要確定一個清楚的專案目標，才能剖析過往  
第二就是要誠實的面對過去，那邊不好，就得承認，唯有接受錯誤，才有下次改善的可能。  
再者，要保留事後檢討的時間，不要讓新的專案掩蓋過去寶貴的經驗。  
人們可能一直處於低落的狀況，有些人可能會離開，經驗就會這樣流失  

NASA把過去的經驗編製成了一本Flight Rules，裡面記載著過往的錯誤，以及往後遇到錯誤該如何改善  
我們雖然不是在做發射太空船的工作，但同樣的我們也可以編錄一本過往專案的成功與錯誤的經驗  

該如何去編製一本我們版本的Flight Rules，Amazon和Asana用了類似Toyota的"Five Whys"來找到發生錯誤的根本原因  
舉例來說，當一個網站壞掉的時候，我們會問說“為什麼網站會壞掉“，答案可能是因為“某些伺服器過載“；“為什麼伺服器會過載？“  
可能是某些不成比例的流量流到那些過載的伺服器上；“為什麼伺服器所接收到的流量如此不平均？“，因為那些過載的流量都來自同一個用戶  
因為那個用戶的資料都存放在那些過載的機器上面。  
利用Five Whys，我們可能盡可能找到發生的根本原因，接著進行改善。  

最後要把這種事後檢討的行為融入到整個公司的文化是非常困難的；可以先從小的專案做起，慢慢累積經驗  
接著進行到較大的專案，最後可以導到整個公司內部  

Build a Great Engineering Culture  
建立一個好的文化吧  

作者認識一個好的文化包括  
1. Optimize for iteration speed.  
2. Push relentlessly towards automation.  
3. Build the right software abstractions.  
4. Focus on high code quality by using code reviews.  
5. Maintain a respectful work environment.  
6. Build shared ownership of code.  
7. Invest in automated testing.  
8. Allot experimentation time, either through 20% time or hackathons.  
9. Foster a culture of learning and continuous improvement.  
10. Hire the best.  

你會發現上述幾點的文化，其實座落在這本書的全部章節上  
可以試著講述自己公司有或者你期許什麼的文化  

一個好的文化並不是一天造成的，一開始是由最初的團隊成員帶起，隨著時間及專案的過去，逐漸由團隊成員塑型而成  
我們並不要只成為了個effective engineers；更要建立一個effective engineering culture。  

Key Takeaways  
1. Help the people around you be successful.  
2. Make hiring a priority.  
3. Invest in onboarding and mentoring.  
4. Build shared ownership of code.  
5. Debrief and document collective wisdom.  
6. Create a great engineering culture.

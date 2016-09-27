Part 3: Build Long-Term Value  
  
  
Part 1在講理解和增加效率的一些mindset，記得我們談到leverage這件事  
Part 2在講執行，要有效率的執行一些high leverage的事情時，有哪些方法可以用  
Part 3就在講長遠的目標  
  
  
  
  
  
  
  
  
  
  
Chapter 8. Balance Quality with Pragmatism  
  
  
Goolge對於工程師來說有非常好的coding制度，每項code commit都需要經過一連串的自動化審查  
最後需要經過同事間的review；這麼做的好處是可以增加每項code的品質；缺點就是降低了iteration的進度  
對於任何實驗性質的code，都需要花費大量的時間來refactor，萬一實驗失敗了，等於先前refactor的時間不就白費  
尤其這樣的做法對於新創或者小型的公司來說是玩不下去。  
本章的目的是在於如何在建立code品質上和iteration速度上如何取得平衡  
  
  
  
  
  
  
  
  
Establish a Sustainable Code Review Process  
  
  
Code review好處多多  
1. Catching bugs or design shortcomings early.  
  早點發現bug或者設計上的缺失  
2. Increasing accountablility for code changes.  
  不想要爛code給別人看，覺得丟臉，所以會想要負責把code寫好  
3. Positive modeling of how to write good code.  
  大神的code寫的好好喔，快看他的code來學習  
4. Sharing working knowledge of the codebase.  
  你看過我的code，應該大概知道我在幹麻，如果我請假的時候發生bug，你有機會可以先幫我解決  
5. Increasing long-term agility  
  review完的code，品質應該都還不錯，比較少會出bug  
  
  
既然code review好處多多，大家嘴巴上面講很棒，可以實際工作上卻很少落實呢？  
因為大家常常面臨到一個問題：案子太趕了，光做都做不完，還要解一大堆的bug，哪有時間code review呢？  
並且明明功能都可以動了，如果要改的話，等到發生bug在說。  
  
  
"Despite that, the company was able to build a strong engineering team and a compelling product with tens of million of users, before they had to institute code reviews to help scale code quality"  
他們是怎麼做到的？？  
  
  
Code review並不是只有要review和不要review這兩種，你可以選擇部份review  
只review最重要的部分就好，可以減少時間review其他不重要的部分  
  
  
Square and Twitter用pair programming的方式來code review  
  
  
Ooyala只需要review核心部分的code，UI相關的code都不review  
為了增加iteration的速度，他們常常是code上線之後，才開始review  
你說他們這樣上線之後遇到了問題怎麼辦？通常在上線之前是會要先通過測試  
所以上線的code是已經確保功能是正常的  
不過非常核心的功能在commit前要先review  
而且為了確保code的標準是一致的，菜鳥的code要常常被review  
  
  
好的工具也可以加速code review  
GitHub和Phabricator都是不錯的選擇  
  
  
Lint - 靜態分析工具，可以幫助你檢查coding style, 和code的語法錯誤  
  
  
  
  
Manage Complexity through Abstraction  
  
  
好的抽象很棒，讓員工可以專注在開發business logic就好，可以解決很多問題，像是：  
1. It reduces the complexity of the original problem into easier-to-understand primitives.  
  幫你把前置作業全部準備好，你只要專心做重要的部分就好  
2. It reduces future application maintenance and makes it easier to apply future improvements.  
  維護也好維護，只要處理business logic就好  
3. It solves the hard problems once and enables the solutions to be used multiple times.  
  Don't Repeat Yourself(DRY)  
  大家都用同一套，只要改同一套，大家都受益  
  
  
但是過度投資在抽象上面反而會遇到很多問題，像是：花太多時間在抽象上，主要產品反而沒有時間去撰寫  
  
  
好的抽象應該有下面幾點特性  
1. easy to learn  
2. easy to use even without documentation  
3. hard to misuse  
4. sufficiently powerful to satisfy requirements  
5. easy to extend  
6. appropriate to the audience  
  
  
滿重要的概念  
"Simple abstractions avoid interweaving multiple concepts, so that you can reason about them independently rather than being forced to consider them together. Techinques such as avoiding mutable state, using functional rather than imperative programming, preferring composition over inheritance, and expressing data manipulations declaratively rather than imperatively"  
  
  
// declarative programming   
List&lt;int&gt; collection = new List&lt;int&gt; { 1, 2, 3, 4, 5 };  
  
  
// imperative programming   
List&lt;int&gt; results = new List&lt;int&gt;();  
foreach(var num in collection)  
{  
    if (num % 2 != 0)  
          results.Add(num);  
}  
  
  
  
  
最後可以去看一下open source的專案，他們抽象是怎麼做的，可以跟他們學習  
  
  
  
  
  
  
  
  
Automate Testing  
  
  
自動化測試可以幫助快速找到bug, 減少重覆的手動工作，也可以幫助開發，還是可以當開發文件  
一樣的目的，幫助你準備好所有的前置作業，然後你只需要專心做核心的功能就好  
  
  
雖然自動化測試很重要，但是也不是每個功能都需要自動化測試  
  
  
test case大概分成下面等級  
Release Acceptance Test(RAT)  
Functional Acceptance Simple Test(FAST)  
Task-Oriented Function Test(TOFT)  
Force-Error Test(FET)  
Boundary Test  
Volume Test  
Stress Test  
  
  
RAT &gt; FAST &gt; TOFT = Boundary = FET &gt; Volume = Stress   
  
  
參考  
[http://blog.codylab.com/testcase-categorization/](http://blog.codylab.com/testcase-categorization/)  
  
  
寫automate testing要花很多的時間，還要mock data什麼的，但是成效不一定都是好的  
有的時候automate testing寫完之後，結果卻非常少被執行  
有的時候autoamte testing跑太久了  
或者automate testing太難維護了，每次都要花大量時間去修復  
介面常改的話，test幾乎都會失敗  
  
  
Repay Technical Debt  
  
  
技術債通常指的是為了省時間而去做的workaround或者hotfix，比較差的解法  
通常隨著專案的進行，這些一點一點累積的技術債有可能一次爆發，阻疑後面專案的進行  
所以需要週期性的去解決這些技術債  
  
  
Google會有Fixit day的制度，那day專門就是用來解決技術債  
  
  
解技術債的時候，就會暫時讓專案停滯下來，沒有辦法讓專案進行下去，而且解完也有可能會衍生新的問題  
通常只有有限的時間可以去解技術債，並不是每個hoest幾乎都會失敗  
  
  
Repay Technical Debt  
  
  
技術債通常指的是為了省時間而去做的workaround或者hotfix，比較差的解法  
通常隨著專案的進行，這些一點一點累積的技術債有可能一次爆發，阻疑後面專案的進行  
所以需要週期性的去解決這些技術債  
  
  
Google會有Fixit day的制度，那day專門就是用來解決技術債  
  
  
解技術債的時候，就會暫時讓專案停滯下來，沒有辦法讓專案進行下去，而且解完也有可能會衍生新的問題  
通常只有有限的時間可以去解技術債，並不是每個hotfix都是很好處理  
很好處理就不會用hotfix去改，所以要好好的評估一下解這些技術債的時間  
  
  
  
  
常常需要讀，並且被修改的code才是有價值去特別處理的技術債  
不常更動的code就算有技術債，也不值得去處理  

  
  
Key Takeaways  
1. Establish a culture of reviewing code.  
2. Invest in good software abstractions to simplify difficult problems.  
3. Scale code quality with automated testing.  
4. Manage your technical debt.

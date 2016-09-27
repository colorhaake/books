Invest in Iteration Speed  
第一節  
全面性的講解iteration speed的重要性  
作者引述他在Quora使用continuous deployment來達到快速驗證code  
  
  
作者敘述他在Quora利用continous deployment來每天release 40~50次的code到production server  
並且維持著高品質以及高可靠度。原因是因為這些release，每次都會花大約7分鐘的時間來經過數千條的自動化測試驗證  
而不必花費任何人工來處理。不同以往傳統release的流程，它們往往都是週期性、一季一季或者一年才release一次而已  
所以傳統的release通常會包含著1個以上的change，萬一當有bug發生的時候，很難從這數種以上的change中，找到是哪次的change  
所引發的問題  
  
  
第二節  
Move Fast to Learn Fast  
快速前進，不要害怕去犯錯，從前進中或者錯誤中才知道哪個是有用，哪個是錯誤，這樣學習才是最快  
但也不代表任意犯錯，對於錯誤，反應速度要更快  
以Facebbok最嚴重的例子，最多也停止服務2.5小時左右  
continuous deployment只是Move Fast的其中一項工具而已，你可以針對自己去找到更適合Move Fast的工具  
像是調整自己的work flow, debugging flow等等  
切記，其他公司沒有辦法成功的原因，就是太過於保守，太害怕犯錯了  
  
  
第三節  
Invest in Time-Saving Tools  
作者訪問各家大公司的工程師們，發現好的工具可以帶你上天堂，埋頭苦幹只會讓你住套房  
好的工具，假如可以讓你每天省下10分鐘的話，一個月就可以省下5個小時的時間  
但是也不是一直都在做工具就好了，正確的做法是在每個iteration當中，發現最花費時間的地方  
想新的辦法來改善他，工具只是其中一種而已  
並且，好的辦法可以帶入新的思維，新的工作流程  
例如，假如building的時間可以改善成非常快的話，哪我們就不必花費大量的心力去一行一行檢查程式有沒有錯誤  
直接compile之後，讓機器告訴你就好了  
除此之外，用interactive language, code hot reload, continuous integration等等有諸多的例子  
  
  
另外大家都知道工具的重要，但是如何跟老闆談開發工具的時間呢  
而且也想辦法要說服大家用新工具  
  
  
第四節  
Shorten Your Debugging and Validation Loops  
工程師debug和驗證要花很多時間 -&gt; 改善它吧  
如果有一個好的workflow的話，就可以減少走過許多的冤望路  
比如說找到最小reproduce bug的steps  
或者說假設app的flow是A -&gt; B -&gt; C，你已經大概猜到bug是發生在B上面  
那就想個法子，run code的時候，可以直接跑到B去重現bug，那就不用花時間在經過A的上面  
  
  
第五節  
Master Your Programming Environment  
改善你的開發環境吧! 能自動化就盡量自動化，能熟悉快速的工具，就盡量去學，減少手動的時間  
雖然一開始是滿不順的，但是時間一過去，你就會愈來愈熟悉的  
  
  
熟悉列表:  
Code Navigation, Search, Formatting  
Documentation Lookup  
Hotkeys for system, text editors, and any other tools  
  
  
Tracking changes in version control  
Compiling or building code  
Running a unit test or program  
Reloading a web page on a development server with new changes  
Testing out the behavior of an expression  
Looking up the documentation for a certain function  
Jumping to a function definition  
Reformatting code or data in text editor  
Finding the callers of a function  
Rearranging desktop windows  
Navigating to a specific place within a file  
  
  
Get proficient with your favorite text editor or IDE  
Learn at least one productive, high-level programming language  
Get familar with UNIX (or Windows) shell commmands  
Prefer the keyboard over the mouse  
Automate your manual workflows  
Test out ideas on an interactive interpreter  
Make it fast and easy to run just the unit tests associated with your current changes  
  
  
第六節  
Don't Ignore Your Non-Engineering Bottlenecks  
很多時候，我們花費最多的時間反而不是coding，而是其他有關於人的bottlenecks  
像是主管、客戶亂來，spec說改就改，之前花費的時間都白費了  
像是code卡在其他team，但是team完全不急的樣子  
像是來回email的溝通，比不上直接打電話的快  
像是決定卡在上頭, 你只能乾瞪眼  
等等  
及早發現及早治療，所有的事情不要拖到最後一刻  
建議把事情排程好，分成好幾個iteration，每個iteration都要思考觀察接下來改怎麼處理  
有哪些flow是不平順的，要用全面去看  
  
  
這樣你才會有一個豐富美好的人生

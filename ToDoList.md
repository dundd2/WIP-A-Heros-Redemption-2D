# A Hero's Redemption 2D TO DO LIST Before V1.0

1.edit在戰鬥模式中敵人攻擊移動的特效,現時戰鬥模式時敵人圖片分為的戰鬥圖片,以及普通站立圖片,改為只存在站立圖片,然後在敵方攻擊的時候敵人的站立圖片會向左移動一下然後再回到原位,象徵著敵人向玩家攻擊

2.新增讓遊戲裏面的按鈕都可以用滑鼠選擇而不只是鍵盤

4.幫我調節所有鍵盤操控選項卡的速度我認為他們現在太快了很難正確選擇,尤其是在主頁以及等級選擇裏面,也請你讓遊戲支援使用wasd操控以及鍵盤上的箭咀操控

5.幫我看看為什麼故事模式裏面故事的對話並不能夠正確出現在遊戲裏面,so far 只有看到說話角色的圖片以及他們的名稱,對話內容的文字顏色應該要是黑色的,而且要像跑馬燈一樣走出來,修改在故事模式時,普通關數也就是除了第一的以及第十關之外,每關開始之前的敵人(enemy_name_xxx)對話的圖片都是直接使用同一個關卡的敵人站立的圖片,

6:Error
main.lua:1595: attempt to perform arithmetic on global 'dt' (a nil value)
Traceback
[love "callbacks.lua"]:254: in function 'handler' main.lua:1595: in function 'drawStoryPageUI' main.lua:1363: in function 'draw' 
[love "callbacks.lua"]:195: in function <[love "callbacks.lua"]:171> [C]: in function 'xpcall',d Error: main.lua:2315: attempt to index a nil value stack traceback: 
[love "boot.lua"]:461: in function '__index' main.lua:2315: in function main.lua:2237 [love "callbacks.lua"]:181: in function <[love "callbacks.lua"]:171> [C]: in function 'xpcall'

9.請你根據現時的代碼重新修改並且增加音效播放的觸發點,例如要是當我暫停遊戲之後重新開始戰鬥音樂卻不會重新開始

10修改從主頁進入遊戲故事頁面的時候出現故障以及當選擇中文的時候進入故事頁面之後只有中文的標題但沒有顯示內文

Turn-based RPG using Love2D Framework. Personal demo for better understand the challenges in a larger Unity 3D group project later this year

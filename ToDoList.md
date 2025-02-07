# A Hero's Redemption 2D TO DO LIST Before V1.0

1.敵人尺寸與位置校正及攻擊動畫調整 (Enemy Size, Position Correction & Attack Animation Adjustment):
任務: 修正戰鬥模式中敵人的圖片顯示。
細節:
敵人最大尺寸設定: 在 enemyData 結構中，為每個敵人配置設定最大圖片尺寸的參數，確保在不同螢幕解析度下敵人圖片不會過大或過小。
敵人圖片顯示範圍: 檢查並修正敵人圖片在戰鬥場景中的渲染位置 (positions.enemy)，確保圖片完全位於遊戲可見區域內。
敵人位置固定: 確認敵人在戰鬥場景中的位置是靜態固定的，除非執行特定動畫（例如攻擊）。
敵人攻擊動畫 (左移效果): 實作當敵人選擇攻擊時的視覺效果：
在 animations.enemy 中，修改或新增 "attack" 動畫狀態，使其在動畫的短暫時間內將 animations.enemy.x 的值向左偏移，然後快速恢復原位 (animations.enemy.originalX)，模擬攻擊動作。
玩家攻擊特效覆蓋: 檢查當玩家攻擊敵人時，產生的特效（例如 hitEffect 粒子系統）的渲染邏輯，確保特效圖層正確地疊加在敵人的圖片之上，不會被遮擋或顯示錯位。


2.故事模式對話顯示問題排查 (Story Mode Dialogue Display Debugging):
修復故事模式中對話內容無法正確顯示的問題。
細節:
對話內容顯示排查: 檢查故事對話的渲染函數 (drawStoryDialogue)，確認以下幾點：
文字渲染邏輯: 檢查文字渲染函數是否正確調用 getText 函數獲取當前語言的對話文本，並使用 love.graphics.print 或 love.graphics.printf 進行渲染。
文字顏色設定: 確認對話內容的文字顏色已設定為藍色 (love.graphics.setColor(0, 0, 1, 1))。
字體設定: 檢查是否已正確設定用於對話內容的字體 (resources.fonts.ui 或 resources.fonts.chineseUI)。
數據綁定: 確認 getCurrentDialogue 函數能正確從 story.levelIntros 或 story.ending 中獲取對話數據，並將文本傳遞給渲染函數。
現有顯示元素驗證: 已知角色圖片和名稱可以顯示，請驗證問題是否出在文本渲染部分，例如字體載入失敗、顏色設定錯誤、或文本數據獲取異常。

3.請你根據現時的代碼重新修改並且增加音效播放的觸發點,例如要是當我重新開始level,戰鬥音樂卻不會重新開始,以及多我重新回到主頁之後主頁的音樂不會播放

4.故事頁面中英文混雜問題修正 (Story Page Chinese/English Mix Issue):
修正故事頁面在中文語言設定下，標題為中文但內容仍為英文的問題。

細節:
文本數據源檢查: 確認 storyPageState.storyText 在中文語言設定下，正確載入的是 story.text.zh.game_full_story 的內容，而不是 story.text.en.game_full_story。
語言切換邏輯驗證: 檢查 setCurrentLanguage 函數和 getText 函數的語言切換邏輯，確認當 currentGameLanguage 設定為 "zh" 時，getText("zh", "game_full_story") 能正確返回中文文本。
初始化設定: 檢查遊戲啟動時的默認語言設定 (currentLanguage = "en") 和語言初始化函數 (initText)，確保語言設定流程正確。


5.故事模式敵人圖片與對話框佈局限制 (Story Mode Enemy Image & Dialogue Box Layout Constraints):
任務: 調整故事模式中敵人圖片的顯示，使其位於對話框內，並限制其最大尺寸。
細節:
敵人圖片容器化: 在 drawStoryDialogue 函數中，為敵人的圖片創建一個容器區域（例如計算好的 dialogBoxX, dialogBoxY, dialogBoxWidth, dialogBoxHeight 內部的一個矩形區域）。
圖片尺寸限制: 在渲染敵人圖片時，計算並限制圖片的最大寬度和高度，使其完全位於上述容器區域內，不超出對話框邊界。 可以參考 drawStoryDialogue 中主角頭像圖片 (portraitImage) 的尺寸限制和佈局邏輯。
圖片位置調整: 根據設計需求，調整敵人圖片在對話框內的相對位置，例如可以放置在對話框內容區域的左側或右側，確保與對話文本佈局協調。
主選單 (Main Menu)


6.新增項目介紹與製作人員頁面 (Add Project Introduction & Staff Page):
任務: 在主選單中新增一個選項，進入項目介紹和製作人員頁面。
細節:
主選單選項新增: 修改 menuState.options 數組，新增一個選項，例如 menu_about (文本鍵值)，對應的 action 函數設定為切換遊戲狀態到新的 "aboutPage" 狀態。
"aboutPage" 遊戲狀態創建: 創建一個新的遊戲狀態 "aboutPage"，並在 gameState 變量和相關的狀態處理邏輯中加入 "aboutPage" 狀態。
"aboutPage" UI 繪製函數 (drawAboutPageUI): 創建 drawAboutPageUI 函數，負責渲染項目介紹頁面的 UI：
頁面佈局: 設計頁面佈局，包括標題、文本區域、圖片區域、鳴謝列表區域等。
作者圖片顯示: 在頁面頂部渲染作者的圖片 (resources.images.authorPortrait，如果有的話)。
項目介紹文本: 使用 getText 函數獲取項目介紹文本 (例如新增 story.text.en.about_project, story.text.zh.about_project 文本數據)，並使用 love.graphics.printf 渲染到文本區域。
製作人員與鳴謝列表: 將製作人員和鳴謝名單數據 (可以硬編碼在 Lua 文件中或從外部文件載入) 渲染到頁面的相應區域。
返回主頁按鈕: 在頁面左上角或適當位置添加一個返回主頁的按鈕，點擊後將遊戲狀態切換回 "menu"。可以複用故事頁面的返回按鈕 UI 和邏輯。

7.戰鬥模式操控 (Battle Mode Control)
戰鬥選單鍵盤向上選擇錯誤修正 (Battle Menu Keyboard Up Selection Bug Fix):
任務: 修正戰鬥模式中，玩家回合時使用鍵盤向上方向鍵 (up 或 w) 選擇戰鬥選項時出現的錯誤。
細節:
輸入處理函數檢查: 檢查 handleBattleInput 函數中處理鍵盤輸入的部分，特別是向上方向鍵的邏輯。
邊界條件判斷: 確認向上選擇選項時，對選單索引的邊界條件判斷是否正確。例如，當當前選項為第一個選項 (battleState.currentOption == 1) 時，再次向上選擇應該循環到最後一個選項 (battleState.currentOption = #battleState.options)。
代碼邏輯錯誤排查: 仔細檢查向上選擇的索引遞減邏輯，確保沒有邏輯錯誤導致索引值超出有效範圍或出現其他異常。
向下選擇邏輯對比: 對比向上選擇和向下選擇的代碼邏輯，找出差異，判斷是否是某個條件判斷或變量更新在向上選擇的路徑上缺失或錯誤。

8.選項頁面擴展 (Options Page Expansion)
任務: 擴展選項頁面的功能，增加更多可供玩家設定的選項，並考慮加入作弊選項。
細節:
新增選項功能: 在 optionsState.options 數組中新增更多選項，並實現其功能，例如：
字體大小設定: 新增選項允許玩家調整遊戲中使用的字體大小。可以新增一個數值調整選項，修改 resources.fonts.ui 和 resources.fonts.battle 等字體的尺寸參數，並在 UI 渲染時動態應用新的字體尺寸。
解析度選項 (已存在，可優化): 優化現有的解析度選項，例如增加更多常見解析度選項，或允許玩家自定義解析度 (如果技術上可行)。
全螢幕/視窗模式切換: 新增選項允許玩家切換全螢幕和視窗模式 (love.window.setMode)。

作弊選項 (Cheat Options) 新增: 考慮在選項頁面中新增作弊選項，例如：
無限生命值: 設定 player.hp = player.maxHp 或修改傷害計算函數，使玩家永遠不會受到傷害。
選項 UI 更新: 相應地更新選項頁面的 UI 渲染函數 (drawOptionsUI)，確保新增加的選項能正確顯示和操作。


9.更徹底的模組化:

將遊戲狀態管理獨立模組: 目前 gameState 變數是全局的，可以考慮使用更結構化的狀態管理模式，例如使用一個狀態機 (State Machine) 模組，來更清晰地管理和切換遊戲的不同狀態 (menu, battle, story, options 等)。這能減少全局變數的依賴，提高程式碼的組織性和可維護性。

戰鬥系統模組化: 將戰鬥系統的核心邏輯 (傷害計算、技能效果、AI 決策、回合管理等) 封裝成獨立的模組或類別。這樣可以讓 love.update 和 love.draw 函數更簡潔，戰鬥邏輯也更容易測試和擴展。

UI 元素模組化: 將 UI 元素 (按鈕、選單、對話框、血條等) 創建成可重複使用的模組或類別。例如，可以創建一個 Button 類別，包含繪製、點擊檢測、文字設定等功能，方便在不同介面中使用。

10.資料驅動設計的深化:

外部化遊戲設定: 目前 enemyData, skillInfo, battleBackgrounds 等資料已經以 Lua 表格形式存在，但可以更進一步將這些資料移動到外部檔案 (例如 JSON 或單獨的 Lua 檔案) 中載入。這樣修改遊戲內容 (例如調整敵人數值、新增技能、更換背景) 時，無需修改程式碼，只需編輯資料檔案即可，極大提高維護和擴展性。

故事劇情資料化: 將故事對話、角色設定、關卡劇情等內容也資料化，儲存在外部檔案中。這樣可以更方便地編輯和管理故事內容，甚至可以製作劇情編輯器。

使用設定檔: 將遊戲的各種可配置參數 (例如音量、文字速度、UI 佈局參數、動畫時間等) 提取到一個設定檔中。方便調整遊戲平衡性和使用者體驗，也方便製作多種難度模式或自訂選項。

11.程式碼風格一致性與靜態分析:

使用 Lua 程式碼風格指南: 遵循業界通用的 Lua 程式碼風格指南 (例如 Lua Style Guide) 可以提高程式碼的可讀性和團隊協作效率。

引入 Lua Linter: 使用 Lua Linter 工具 (例如 luacheck) 可以自動檢測程式碼中的潛在錯誤、風格問題和效能瓶頸，幫助你及早發現並修正問題，提高程式碼品質。

12.效能優化
避免在 love.draw 中進行複雜計算: 將複雜的計算邏輯移動到 love.update 函數中，love.draw 函數只負責繪製，保持繪製函數的效率。

_____________________
Turn-based RPG using Love2D Framework. Personal demo for better understand the challenges in a larger Unity 3D group project later this year

#使用COLAB環境執行程式

先前失敗原因: • Carracing 這個遊戲的action為連續動作,方向為(-11) 油門為(01) 煞車為(0~1),連續動作使用sarsa模型訓練需要先將動作離散化,但這會消耗大量的效能以及影響準確度。

改進方法: 使用DQL 模型進行訓練。

程式執行步驟:

導入BOX.2D套件
導入相關函式庫
導入Video 相關套件
宣告ExperienceHistory
宣告Agent
宣告test_experienceHistory
執行Main主程式
主程式說明 (程式有分為兩個部分)

重新訓練


![image](image/1579087454989.jpg)


load_checkpoint代表是否載入過去訓練資料。 checkpoint_path為此次訓練資料之名稱與路徑資料夾(data)。 輸出結果: 第一階段:會先開始訓練,按Enter鍵可以結束訓練並進入第二階段。 第二階段:會開始玩遊戲,並持續輸出每次玩的結果,按下Enter鍵結束。

採用過去訓練資料


![image](image/1579087430063.jpg)



checkpoint_path 是將訓練資料放入data資料夾內再colab上的話需要再content內自創data資料夾,並將訓練資料的資料夾放入。 train_episodes是選擇要不要接續訓練,這裡為0所以輸出會自動跳過訓練階段,並直接顯示第二階段玩遊戲的結果。

結果評估
使用隨機策略玩5回合的結果為


![image](image/1579090083507.jpg)



使用DQL模型的遊戲結果


![image](image/1579087000633.jpg)




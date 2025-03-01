# 作業1 負評救星-當機等候網頁
## 設計理念
選擇網站： [Github](https://github.com)

當Github網頁崩潰時，對工程師們來說，是件非常痛苦的事情。

因此，我們需要一個網頁，在當Github網頁崩潰時，可以和可愛的貓咪一起玩鬧一下

~~當然，請先確保老闆/教授不在你身後~~


<img src="https://github.com/user-attachments/assets/8bbda675-c993-46d9-a083-cbc4fbfcec3a" width="500">
<img src="https://github.com/user-attachments/assets/33d44293-73e2-4516-b61f-c7ee2d8d2cba" width="500">

## 系統結構
```
rock-paper-scissors/
│
├── index.html          # 包含所有HTML、CSS和JavaScript的主文件
│
└── img/               # 圖片文件夾
    ├── 1.png          # 石頭圖片
    ├── 2.png          # 剪刀圖片
    └── 3.png          # 布圖片
```
## 使用技術
- 前端:HTML、CSS、javaSprics
- 伺服器:Github Pages
## 技術說明
<img src="https://github.com/user-attachments/assets/5d7eca9c-63b9-4b97-bc6c-4d48556ed245" width="200" align='right'>

### 1. HTML部分
#### 本部分架構了網頁基本框架，使用了
- lang="en" 設定文件為英文
- 於<head>中定義CSS樣式
- 於<body>區放置遊戲畫面骨架，以利遊戲時頁面切換
  
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <style>
        /* css部分 */
    </style>
</head>

<body>
    <div class="container">
        <div class="score">
            <span>Player: <span id="playerScore">0</span></span>
            <span style="margin: 0 20px;">|</span>
            <span>Cat: <span id="catScore">0</span></span>
        </div>
        <div class="title">ERROR!!</div>
        <div class="sorry-text">Sorry, the webpage is too busy. Please try again later.</div>
        <!-- 更多的HTML-->
    </div>
    <script>
        /* js部分 */
    </script>
</body>
```

<img src="https://github.com/user-attachments/assets/396c3484-b54e-4291-8ba9-0b5767a7350a" width="200" align='right'>

### 2. CSS部分
#### 本部分用來美化、控制網頁中元素、動畫相關效果，使網頁看起來與Github更為相似
- 藉由"body"、".container"控制網頁 背景顏色、網頁範圍、字體，使風格更統一
- 利用"style="display: none;" 對指定Class進行開關，達成遊戲畫面切換
- 利用"@keyframes"讓等待畫面產生動畫效果
- 使用"justify-content: space-between;"使按鈕、圖片橫向並排

```css
    body{
        margin: 0;
        font-family: sans-serif;
    }
    .container{
        background-color: #0d1117;
        user-select: none;
        height: 100vh;
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    /* 更多的CSS */ 
```

<img src="https://github.com/user-attachments/assets/ea367f00-38c2-42e8-ad62-e360b58dfb12" width="200" align='right'>

### 3. JavaScript部分
#### 本部分為網頁提供了互動，包含
- 遊戲頁面切換、剪刀石頭布按鈕狀態偵測
- 計分動畫的輔助呈現
- 遊戲勝負判斷
```js
    /* 更多JavaScript部分 */
    function determineWinner(playerChoice, computerChoice) {
        const scoreElement = document.querySelector('.score');
        
        // Show score
        scoreElement.classList.add('show');
        setTimeout(() => {
            scoreElement.classList.add('hide');
        }, 3000);

        if (playerChoice === computerChoice) return "Draw!";
        if (
            (playerChoice === "1" && computerChoice === "2") ||
            (playerChoice === "2" && computerChoice === "3") ||
            (playerChoice === "3" && computerChoice === "1")
        ) {
            playerScore++;
            playerScoreElement.textContent = playerScore;
            return "You Win!";
        }
        catScore++;
        catScoreElement.textContent = catScore;
        return "Cat Wins!";
    }
    /* 更多JavaScript部分 */
```

### commit 次數
![image](https://github.com/user-attachments/assets/73e6e874-f144-4409-b341-36a444b30f28)

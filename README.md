<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FAQ 常見問題</title>
    <style>
        /* 基礎設定 */
        body { 
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; 
            background: #f0f2f5; 
            display: flex; 
            justify-content: center; 
            align-items: center; 
            height: 100vh; 
            margin: 0; 
        }

        /* 模擬手機容器 */
        .phone-container { 
            width: 360px; 
            height: 640px; 
            background: white; 
            border-radius: 30px; 
            overflow: hidden; 
            box-shadow: 0 10px 25px rgba(0,0,0,0.1); 
            position: relative;
            display: flex;
            flex-direction: column;
        }

        /* 紅色標題列 */
        .header { 
            background: #ff5252; 
            color: white; 
            text-align: center; 
            padding: 20px 0; 
            font-size: 1.2rem; 
            font-weight: bold; 
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }

        /* 選單列表 */
        .menu-list { 
            padding: 20px; 
            flex-grow: 1;
            overflow-y: auto;
        }

        /* 選單按鈕樣式 */
        .menu-item { 
            background: #f1f1f1; 
            margin-bottom: 15px; 
            padding: 15px; 
            border-radius: 50px; /* 橢圓形狀 */
            text-align: center; 
            cursor: pointer; 
            font-weight: 500;
            color: #333;
            transition: all 0.2s ease;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
        }

        .menu-item:hover { 
            background: #e0e0e0; 
            transform: translateY(-2px);
        }

        /* 內容顯示區塊 */
        .content-view {
            display: none;
            padding: 20px;
            animation: fadeIn 0.3s ease;
        }

        .content-text {
            background: #f9f9f9;
            padding: 20px;
            border-radius: 15px;
            min-height: 200px;
            color: #666;
            line-height: 1.6;
        }

        /* 返回按鈕 */
        .back-btn {
            display: inline-block;
            margin-top: 20px;
            color: #ff5252;
            cursor: pointer;
            font-weight: bold;
        }

        /* 動畫 */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body>

    <div class="phone-container">
        <div class="header" id="nav-title">常見問題</div>

        <div class="menu-list" id="main-menu">
            <div class="menu-item" onclick="openPage('出貨時間', '本商店商品皆為現貨，下單後約 2-3 個工作天出貨。')">出貨時間</div>
            <div class="menu-item" onclick="openPage('訂單問題', '您可以透過會員中心查詢訂單進度，若有異常請聯繫客服。')">訂單問題</div>
            <div class="menu-item" onclick="openPage('預購說明', '預購商品通常需要 14-21 個工作天，請耐心等候。')">預購說明</div>
            <div class="menu-item" onclick="openPage('退換貨政策', '提供 7 天鑑賞期，請保持商品包裝完整即可辦理。')">退換貨政策</div>
            <div class="menu-item" onclick="openPage('客服聯絡方式', 'Line 客服：@shop_helper<br>服務時間：10:00 - 18:00')">客服聯絡方式</div>
        </div>

        <div class="content-view" id="detail-page">
            <div class="content-text" id="detail-content"></div>
            <div class="back-btn" onclick="goBack()">← 返回選單</div>
        </div>
    </div>

    <script>
        const navTitle = document.getElementById('nav-title');
        const mainMenu = document.getElementById('main-menu');
        const detailPage = document.getElementById('detail-page');
        const detailContent = document.getElementById('detail-content');

        // 開啟詳情頁
        function openPage(title, text) {
            navTitle.innerText = title;
            detailContent.innerHTML = text;
            mainMenu.style.display = 'none';
            detailPage.style.display = 'block';
        }

        // 返回選單
        function goBack() {
            navTitle.innerText = '常見問題';
            mainMenu.style.display = 'block';
            detailPage.style.display = 'none';
        }
    </script>

</body>
</html>

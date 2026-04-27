<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Layout</title>
    <style>
        /* 基本頁面重置與背景設定 */
        body {
            margin: 0;
            padding: 20px;
            background-color: #6caaf5; 
            font-family: sans-serif;
            display: flex;
            justify-content: center;
        }

        /* 白色主容器 */
        .container {
            background-color: white;
            width: 100%;
            max-width: 800px;
            padding: 10px;
            display: flex;
            flex-direction: column;
            gap: 10px; 
            box-sizing: border-box;
        }

        /* 頂部綠色區塊 */
        .header-box {
            background-color: #b5d56a;
            width: 100%;
            aspect-ratio: 3 / 1; /* 維持寬扁的比例 */
        }

        /* 中間藍綠色區塊容器 (3 欄) */
        .middle-section {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
        }

        .middle-box {
            background-color: #5bc0cc;
            aspect-ratio: 3 / 4; /* 【關鍵修改】設定為直立長方形 (寬3:高4) */
        }

        /* 底部灰色區塊容器 (4 欄) */
        .bottom-section {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }

        .bottom-box {
            background-color: #eef1f3;
            aspect-ratio: 1 / 1; /* 【關鍵修改】設定為正方形 (寬1:高1) */
        }

        /* 響應式設定：小於 480px 時套用 */
        @media (max-width: 480px) {
            .header-box {
                aspect-ratio: 2 / 1; /* 手機版頂部稍微加高 */
            }

            /* 中間區塊變成 1 欄 */
            .middle-section {
                grid-template-columns: 1fr;
            }
            .middle-box {
                aspect-ratio: 4 / 1; /* 手機版變成圖(a)的橫向扁長方形 */
            }

            /* 底部區塊變成 2 欄 2 列 */
            .bottom-section {
                grid-template-columns: repeat(2, 1fr);
            }
            .bottom-box {
                aspect-ratio: 2.5 / 1; /* 手機版變成圖(a)的橫向長方形 */
            }
        }
    </style>
</head>
<body>

    <div class="container">
        <div class="header-box"></div>

        <div class="middle-section">
            <div class="middle-box"></div>
            <div class="middle-box"></div>
            <div class="middle-box"></div>
        </div>

        <div class="bottom-section">
            <div class="bottom-box"></div>
            <div class="bottom-box"></div>
            <div class="bottom-box"></div>
            <div class="bottom-box"></div>
        </div>
    </div>

</body>
</html>

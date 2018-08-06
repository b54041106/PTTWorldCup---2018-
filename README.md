#【2018世足PTT淺析】

##摘要
四年一度的世界盃足球賽今年(2018)在俄羅斯盛大舉辦，期末考期間是否有跟著熬夜看球嗎？七月中冠軍戰落幕之後，世足網路聲量產生怎樣的變化呢？本文以PTT Worldcup版進行鄉民討論度分析，藉由爬蟲取得2014年8月1日-2018年7月31日，總共7933篇文章，作為資料樣本。欲回答以下問題：

1. 鄉民關注度是否隨著傳統強隊爆冷淘汰而下滑？鄉民關注度是否僅在世足賽舉辦期間呢？賽季與非賽季的討論熱度差異？
    - 2018年每日發文量折線圖(半年)
    - 2014-2018年推文量分布直方圖(半年、一年、一年、一年、半年)
    - 2014-2018年發文量比例圓餅圖

2. 鄉民文章的標題關鍵字有哪些？
    - 關鍵字排名表格
    - 關鍵字文字雲

-----

##資料取得&處理
    Usage:
    python hw2.py
藉由requests和beautifulsoup爬取PTT世足版上的作者名稱、推文量、文章標題、發文日期，總共爬取500頁，共9998筆。
已被刪除的文章回傳Nan。
透過pandas以匯出為worldcup.csv

-----

##圖表繪製
1.  2018年每日發文量折線圖(半年)
    Usage:
    > linechart_posts.py
2. 2014-2018年推文量分布直方圖(四年、半年、一年、一年、一年、半年)
    Usage:
    > histogram_recommends.py
    > hist_2018.py 
    經由資料觀察，更改資料選取區間，並繪製分布直方圖。
        爆：表示推文量大於100
        --：表示該文章已被刪除
    - 2018:csv_data.iloc[:7279,1]     --7279筆 #2018俄羅斯世足賽
    - 2017:csv_data.iloc[7279:7498,1] --219筆
    - 2016:csv_data.iloc[7499:7622,1] --124筆
    - 2015:csv_data.iloc[7623:7866,1] --244筆
    - 2014:csv_data.iloc[7866:,1]     --2136筆 #2014巴西世足賽

3. 2014-2018年發文量比例圓餅圖
    Usage:
    >linechart_posts.py
        藉由歷年發文總量的數字，繪製圓餅圖。
4.  關鍵字(#未完成!!!)
    先將worldcup.csv(CSV逗號分隔)另存為keyword.py(CSV UTF-8逗號分隔)
    Usage:
    > keyword.py
    使用jieba套件並匯出關鍵字語詞頻至key.csv
    #完成一半吧，尚須解碼，目前無法顯示繁體中文。
    以關鍵字製作文字雲(#問題：無法使用字型)
    Usage:
    > wordcloud.py #參考五月天文本分析
    > dict.txt     #自定義的詞庫
    > chinese.txt  #停用字

## 論點結果分析


## 延伸

你為何選擇分析這些資料？
回答內容可以包含但不限於:
你的目標為何？你想了解什麼或回答什麼問題？
為何選擇從這(些)網站取得資料？
這份分析可能有什麼用途，帶來什麼影響？
這份分析可能的價值，意義… 07/26 +
你從這些資料中觀察到什麼(例如現象或關聯)? 對此你有什麼看法？

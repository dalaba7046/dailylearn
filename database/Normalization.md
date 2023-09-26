## 前言
碩一晚上的資料庫概論老師說正規化聽聽就好，但是在實作上還是很重要的吧！！
做過正規化的資料表可以大大提昇查詢效能，減少IO。

## 概述
資料庫正規化，又稱正規化、標準化，是資料庫設計的一系列原理和技術，以減少資料庫中數據冗餘，增進數據的一致性。關係模型的發明者埃德加·科德最早提出這一概念，並於1970年代初定義了第一正規化、第二正規化和第三正規化的概念，還與Raymond F. Boyce於1974年共同定義了第三正規化的改進正規化——BC正規化。

現在資料庫設計最多滿足3NF，普遍認為正規化過高，雖然具有對數據關係更好的約束性，但也導致數據關係表增加而令資料庫IO更易繁忙。

## 為什麼要正規化？
1. 提昇資料庫效能與儲存的效率
2. 減少重複資料
3. 增加可維護性以降低維護成本

## 特性
經過正規化後的資料庫，應具備以下特性：

1. 欄位唯一性：每個欄位只儲存一項資料
2. 主關鍵欄位：每筆資料都擁有一個主鍵，來區別這些資料
3. 功能關聯性：欄位之間的關聯應該要明確
4. 欄位獨立性：欄位之間不應存在遞移相依

## 正規化步驟
sample

![image](https://github.com/dalaba7046/dailylearn/assets/49179942/91923523-79a7-4d54-a0cb-3df5bf0eade8)

## 異常
以上未符合正規化的表格具備以下問題：
1. 表格1具備同性質重複的欄位
2. 表格1與表格2都有單一個欄位內有超過1個以上的值
3. 缺乏主鍵(Primary Key)


### 第一正規化
1. 要求每個欄位只能有1個值
2. 決定主鍵
3. 消除意義上重複的欄位

![image](https://github.com/dalaba7046/dailylearn/assets/49179942/1b44226e-4762-4405-b8bd-c3e8831f0d17)


## 異常
1. 過多重複的資料

### 第二正規化
1. 消除部份相依

透過建立新的table來儲存一直出現的欄位並用外鍵進行關聯

![image](https://github.com/dalaba7046/dailylearn/assets/49179942/c3b35e7f-0bc4-4d2b-bcd4-a5150a10263c)
![image](https://github.com/dalaba7046/dailylearn/assets/49179942/e20d09b7-2446-4d7f-a9c8-c0e3dcda03d8)
![image](https://github.com/dalaba7046/dailylearn/assets/49179942/288519a5-071b-40a5-9c11-c90a4ac96226)


### 第三正規化
1. 檢查表格之間的遞移關係
2. 將遞移關係的欄位分割出去,另外組成資料表

* 以範例為例：
  PK為訂單編號，而總金額和非主鍵欄位商品、數量存在遞移相依

![image](https://github.com/dalaba7046/dailylearn/assets/49179942/462b39b4-ce24-4d29-9863-d247fbc53b53)
![image](https://github.com/dalaba7046/dailylearn/assets/49179942/23e1b59b-fa2d-46e4-839b-8eb97ef73ea2)
![image](https://github.com/dalaba7046/dailylearn/assets/49179942/b288208c-9c69-4575-a682-02dbe22a7d0b)



### 結論
* 每一段正規化都會需要解決一個問題
* 第一正規化：去除重複資料
* 第二正規化：去除部份相依
* 第三正規化：去除遞移相依

* 設計不良的表格可能會造成CRUD異常


Ref:

[維基百科](https://zh.wikipedia.org/zh-tw/%E6%95%B0%E6%8D%AE%E5%BA%93%E8%A7%84%E8%8C%83%E5%8C%96)

[資料庫正規化](https://ithelp.ithome.com.tw/articles/10229472)

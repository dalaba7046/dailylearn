1. SELECT 語句少用*去查詢欄位，雖然它很方便
2. 刪除重複記錄的語句：
   * DELETE FROM REVIEW_RAW T WHERE T.ROWID (SELECT MIN(T.ROWID) FROM REVIEW_RAW X WHERE X.SITE_REVIEW_ID = T.SITE_REVIEW_ID)
3. 刪除資料的時候使用truncate取代delete（總覺得有點危）
   * 使用delete時資訊會被紀錄在rollback中，再沒有commit之前都來得及放棄，但使用truncate是不會把資訊紀錄在rollback裡面的，因此所耗費的資源較少，速度也較快，但是就沒有反悔的機會了
   * 什麼情況下才會去追求刪除資料的效能？
4. 使用count記數效率：count(具備索引的欄位) > count(*) > count(1)
5. 在進行許多表格的查詢中，為了滿足某個條件，可能會需要針對其他表格做連結，因此可使用EXISTS(NOT EXISTS)來提高查詢效率
6. 複雜的大型多表格查詢下使用EXISTS會比DISTINCT來的高效，但是在某些情況下使用DISTINCT可讀性比較高，並且效能也不會輸EXISTS

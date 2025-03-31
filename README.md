# Git&GitHub測試文件與筆記
本篇參考papaya電腦教室
參考網址: https://www.youtube.com/watch?v=FKXRiAiQFiY

=== Git追蹤的是檔案的『變化』，而非檔案本身 ===

# Git四大狀態
// Untracked (未追蹤)
Git不會記錄該檔案的內容變更與編輯歷史。

// Tracked (已追蹤)
將該檔案納入Git版本管理中。

// Staged (已暫存)
透過 git add [檔案名稱] 指令，將Untracked的檔案移到Staging Area(暫存區)中。

// Committed (已提交)
將儲存於暫存區中的檔案，透過 git commit -m "Message..." 指令，把狀態記錄起來。

## 相關指令
// Git記錄版本變更時，會儲存作者的資訊
git config --global user.name "作者名稱"
git config --global user.email "作者信箱"

// 轉成具有版本管理功能的Git儲存庫，.git用於儲存所有變更的歷史記錄
git init

// 檢查當前目錄中每個檔案的狀態
git status

// 將檔案的狀態由 Untracked => Tracked 
git add [檔案名稱1] [檔案名稱2]

// 將儲存於暫存區的檔案提交
git commit -m "輸入變更的訊息"

// 列出先前所有的提交歷史記錄(詳細資訊) 
git log

// 比較同一檔案新、舊版本內容的差異
git diff [比較的ID編號] -- [欲比較的檔案名稱]

// 將檔案還原到先前的版本 (!!注意還原過後，同樣需進行提交)
git checkout [欲還原的ID編號] -- [欲還原的檔案名稱]

// 將全部檔案還原到某個時間點，並捨棄掉該還原點之後所有的存檔記錄 
(!!注意該操作為不可逆，建議進行該操作前可先進行備份)
git reset --hard [目標還原點的ID]

// 避免與主線分支混在一起，另外建立一條新的分支，並切換至新分支
git checkout -b [新分支名稱]

# Tips
// HEAD:當前最新的存檔點，master:當前位於主線分支上

// 將所有附檔名為[.py .js .html...]的文件全部加入
git add *[.py .js .html...]

// 將當前目錄中所有需變更的檔案當放入暫存區
git add .

// 檢視log的簡化版
git log --oneline

// 退出log的檢視模式
輸入q

// 刪除的檔案依然需要儲存於暫存區並提交 

// 若某些檔案不需要被追蹤，也不需建立任何版本記錄
於目錄中建立.gitignore檔案，並把要忽略的檔名或副檔名撰寫於文件內


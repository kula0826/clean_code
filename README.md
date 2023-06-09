# Clean Code
   
   
   
### 命名規則
 - variable：使用名詞
 - function：使用動詞
 - boolean：is或has開頭或是類似概念
 - 不使用中文
 - 有意義的命名，不要用 x1, x2 之類的  
***
   
   
### 替每個概念(動作/行為)使用一種字詞，並持續使用
 舉例來說，在為不同類別設定取得方法時，fetch、retrieve 和 get 就用同一個字就好
***
   
   
### 一律用相對較新的寫法
 比如 callback, promise, async await 就用 async await
 
 避免 callback hell
 ```
 callback(10, function(num1){  //10
    var x = num1 + 10
        callback(x, function(num2){ //20
            var y = num2 + 10
            callback(y, function(num3){ //30 
                console.log(num3 + 10) //40 
                console.log('end of hell')
            })
        })
    })
  ```
*** 
   
   
### 不自幹沒用的邏輯
 utility一律使用現成工具庫，比如[Lodash](https://www.lodashjs.com/)
*** 
  
    
### [編排](https://github.com/javascript-tutorial/zh-hant.javascript.info/blob/master/1-js/03-code-quality/02-coding-style/article.md)
  用同一種縮排風格
***  
   
   
### [SOLID Principle](https://ithelp.ithome.com.tw/articles/10252738)
   S — Single responsibility principle(單一職責原則)      
   O — Open closed principle(開放封閉原則)   
   L — Liskov substitution principle(Liskov替換原則)   
   I — Interface segregation principle(介面隔離原則)   
   D — Dependency Inversion principle(依賴倒置原則)   
***   
   
   
### CSS Coding Style
  樣式層級撰寫排序：排版 > 區塊 > 內容 > 動畫  
  排版樣式: position > top > right > bottom > left > display > flex…  
  區塊樣式: margin > padding > width > height > border > background…  
  內容樣式: font > line-height > color…  
  動畫樣式: transition > animation…  
  命名規範(有意義的命名＋容器範疇)  
  有意義的命名: 基於功能、基於內容   Ex. avatarSection、headerContent、searchIcon、menuList  
  容器範疇: 由大而小、由外而內   Ex. container/wrapper、section、block/content/group、item  

  CSS EX：
  ```
    .searchWrapper {
      position: relative;
      width: 100%;
    }
    
    .searchText {
      position: absolute;
      right: 15px;
      bottom: 0;
      magin: 10px 0;
      border: 1px solid #ccc;
      font-size: 13px;
      font-family: Helvetica;
      color: #888888;
      text-align: left;
      transition: 0.3s; 
    }
  ```
***
   
   
### Git flow
  main - production (prd, stable, repo owner)   
  sit - system integration testing (開發環境)   
  uat - user acceptance testing (QA)   
  feat - feature (需求分支)  
  fix - hotfix (爸個分支)    
      
  * 打tag    
    git tag v.build_number   
    git tag v0.0.0-<build_number>   
    git tag prd-20230411-01     
***  
    
    
### commit message
  - feat: 新需求
  - fix: 修爸個
  - refactor: 重構
  - chore: 雜項變更
  
  範例：[JIRA單] feat: jira標題  
  refactor(scope): 會議功能 [#35]  
  fixup: feat: 會議   
  
  [具體參考Angular的commit規範](https://zj-git-guide.readthedocs.io/zh_CN/latest/message/Angular%E6%8F%90%E4%BA%A4%E4%BF%A1%E6%81%AF%E8%A7%84%E8%8C%83)
***  
  
   
### 不要合併提交
  不要在同一個commit提交多個需求
***  
   
   
### API命名規範
  方法 /模組/版本/資源/其他延伸    
  GET /module/v1/resource

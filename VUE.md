## 事前準備與資源

雙字幕 幫助之後看VUE https://chrome.google.com/webstore/detail/youtube-dual-subtitles/hkbdddpiemdeibjoknnofflfgbgnebcm

每一項一定都要全部跟著做一次 影片內的東西 能理解很好 不能也沒事 盡力去想
建議可以邊看邊做筆記 對之後也會很有幫助 尤其VUE
觀看順序
#### html：[https://youtu.be/CLUPkcLQm64](https://youtu.be/CLUPkcLQm64)
#### css：[https://youtu.be/Ml78vnNTBLw](https://youtu.be/Ml78vnNTBLw)
#### js：[https://youtu.be/yZwlW5INhgk](https://youtu.be/yZwlW5INhgk)
#### vue：[https://youtu.be/YrxBCBibVo0](https://youtu.be/YrxBCBibVo0)

都完成後請至屁眼蜜櫃台找mike大哥領取任務 邊寫邊問問題 不懂的可以問我 我算比較閒的

## VUE 第1集 

```html
添加index.html 	利用doc + tab 創建基礎樣式 在<body>部分更改顯示文字
```

## VUE 第2集

```html
在<head>進行vue cdn的設置<script src="https://unpkg.com/vue@3"></script>
```

在資料夾底下添加app.js

```html
在index.html <body>添加 <script src="app.js"></script>讓html可以偵測到app.js
```

```js
const app = Vue.creatApp()創建app
app.mount('#app')將app掛載到dom 讓他運作
```

```html
在<body>內div#app + tab 創建<div id="app"></div>讓元素可以訪問運作
可在內部creatApp({})內添加各種html <div><div> 	或是直接在<div id="app"><div><div><div>添加狀態
```

在Vue.createApp當中添加data(){return{ 變數:數字 || 字串 || 布林值}}

```html
html可對data當中的變數讀取<div id="app"><h2> {{變數}}</h2></div>
```

```html
<button @click="變數++">增加變數1</button>
```

```js
methods:{
  changeTitle(abc){
    console.log(“觸發”)
    this.title = “巴拉巴拉”

    如果要將()將內的abc帶入
    this.title = abc 那麼title會=changeTitle()內的東西也就是"顯示abc"

  }
}
```

```html
<button @click="changeTitle('顯示abc')>觸發changeTitle</button>
```

html 進行show的切換 運行toggleShowBooks()方法

```html
<button @click="toggleShowBooks">
  <span>切換showBooks的true或false</span>
</button>
```

toggleShowBooks()方法利用button觸發後會將showBooks變更 如果true 則 = false如果為false則 = true

```js
toggleShowBooks(){
  this.showBooks = !this.showBooks
},

return {
  title:'123321',
  age:2,
  showBooks:true,
}
```

如果showBooks = true 就會顯示

```html
<div v-show="showBooks">
  <h2> {{title}} -- {{age}}</h2>
</div>
<div v-if="showBooks">
  <h2> {{title}} -- {{age}}</h2>
</div>
		
```

if與show的差別是 if會將整個dom刪除 而show只是將style 改為不顯示


## VUE 第3集

```html
<div class="box"></div>
class="box" 抓取<style>名稱為.box
```

```css
	<style>
.box {
  padding: 100px 0; /*在box外面添加100px的寬度*/
  width: 400px; /*box本身寬度*/
  text-align: center; /*文字置中*/
  background: #ddd; /*box背景顏色*/
  margin: 20px; /*box邊框*/
  display: inline-block; /*內邊框*/
}
	</style>
```

```html
<div class="box" @mouseover="handleEvant($event,5)">鼠標進入</div>
<div class="box" @mouseleave="handleEvant">鼠標離開</div>
<div class="box" @dblclick="handleEvant">鼠標雙擊</div>
<div class="box"></div>
```

```js
  handleEvant(e,data){
    console.log(e,e.type) //e與e的類型
    if(data){ //如果data有東西
      console.log(data) 
    }
  },
```

```html
<div class="box" @mousemove="HandleMousemove">x.y位子{{x}}-{{y}}</div>
```

獲取e的x.y存到data

```js
data(){
  return {
    x:0,
    y:0,
  }
},
methods:{
  HandleMousemove(e){
    this.x = e.offsetX //data設定的x = e的offsetX
    this.y = e.offsetY //data設定的y = e的offsetX
  },
},
```

循環輸出數組

```js
books:[ /*{}內的東西為物件 可自由創建{變數:數字 || 字串 || 布林值}*/
  {title:'1',author:'哈',img:'assets/1.jpg'},
  {title:'2',author:'哈哈',img:'assets/2.jpg'},
  {title:'3',author:'哈哈哈',img:'assets/3.jpg'},
]
```

```html
<li v-for="book in books"> <!-- books將命名為book book 可隨意更改 -->
  <img :src="book.img" :alt="book.title"><!-- 循環例遍books名為img的[0] 第一個數組 到最後一個-->
  <h3>{{book.title}}</h3> <!-- 循環例遍books名為title的[0] 第一個數組 到最後一個 -->
  <p>{{book.author}}</p>	<!-- 循環例遍books名為author的[0] 第一個數組 到最後一個 -->
</li>
```

輸入網址

```html
<a :href="url"></a>
```

```js
url:'網址',
```
導入圖片

```js
img:'assets/1.jpg' /*資料夾位子 assets -> 1.jpg*/
```

css渲染判定

```html
<li v-for="book in books" class="{ fav: book.isFav}"> <!-- books將命名為book book 可隨意更改 -->
    <!-- 數列的isFav如果 = true  css .fav 會渲染 = false則不會-->
```

```js
books:[
  {title:'1',author:'哈',img:'assets/1.jpg',isFav:true},
  {title:'2',author:'哈哈',img:'assets/2.jpg',isFav:true},
  {title:'3',author:'哈哈哈',img:'assets/3.jpg',isFav:true},
]
```

計算屬性

```html
<li v-for="book in filteredBooks" class="{ fav: book.isFav}">
```

```js
computed:{
  filteredBooks(){
    return this.books.filter((book) => book.isFav) /*如果books.isFav = false則 不會渲染*/
  }
}
```

## VUE 第4集

下載note.js 
打開cmd 輸入 node -v 查看是否有正確安裝

輸入npm install -g @vue/cli 0 全域安裝vue cli

cd 資料夾名稱 ->進入資料夾

cd ..  -> 退出資料夾

vue create 新資料夾名稱 ->在當前位子 創建一個新資料夾

code . ->利用vscode 打開資料夾

```html
index.html
<div id="app"></div> 渲染app
```

main.js 很重要

```js
import { createApp } from 'vue' 導入createApp 從vue
import App from './App.vue' 導入App 從路徑./App.vue

createApp(App).mount('#app')  創建App
```

確保 npm run serve 與 npm run bulid 兩個都要正常運作 如果有error 那就是不行

```json
"scripts": {
    "serve": "vue-cli-service serve",
    "build": "vue-cli-service build"
  },
```

向div添加class 按下按鈕後 input 增加class 'active'

```html
<input type="text" ref="name">
<button @click="handleClick">點擊我</button>
```

```js
methods:{
  handleClick(){
    console.log(this.$refs.name)
    this.$refs.name.classList.add('active')
  }
},
```

新增 資料夾名稱.vue 到components

```html
<資料夾名稱 />
```

```js
import 資料夾名稱 from './components/資料夾名稱.vue' /*存放資料夾的位子*/

components: { 資料夾名稱 },
```

## VUE 第5集

讓css設定只在這個檔案渲染

```css
<style scoped>

</style>
```

判定 任意渲染名稱 是否要渲染

App.vue父 Modle.vue子

Modle.vue
```html
<div :class="{ css任意渲染名稱: theme === '變數' }">
<div> theme 如果完全= '變數' 則輸出css樣式 任意渲染名稱 如果不等於 就不會輸出樣式</div>
</div>
```

App.vue
```html
<Modal theme="變數" />
```
theme === 變數 所以會渲染 css任意渲染名稱

### 子級調用父級方法

Modal.vue
```html
<div class="modal" :class="{ css任意渲染名稱: theme === '變數' }">
</div>
```

觸發父級close

```js
closeModal(){
  this.$emit('close')
}
```

App.vue
```html
<div v-if="showModal">
  <Modal theme="sale" @close="toggleModal" />
</div>
```

```js
toggleModal(){
  this.showModal = !this.showModal
}
```

















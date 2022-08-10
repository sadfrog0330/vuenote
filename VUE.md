### 事前準備與資源

雙字幕 幫助之後看VUE https://chrome.google.com/webstore/detail/youtube-dual-subtitles/hkbdddpiemdeibjoknnofflfgbgnebcm

每一項一定都要全部跟著做一次 影片內的東西 能理解很好 不能也沒事 盡力去想
觀看順序 建議可以邊看邊做筆記 對之後也會很有幫助 尤其VUE
#### html：[https://youtu.be/CLUPkcLQm64](https://youtu.be/CLUPkcLQm64)
#### css：[https://youtu.be/Ml78vnNTBLw](https://youtu.be/Ml78vnNTBLw)
#### js：[https://youtu.be/yZwlW5INhgk](https://youtu.be/yZwlW5INhgk)
#### vue：[https://youtu.be/YrxBCBibVo0](https://youtu.be/YrxBCBibVo0)

都完成後請至屁眼蜜櫃台找mike大哥領取任務 邊寫邊問問題 不懂的可以問我 我算比較閒的

### VUE 第1集 

```html
添加index.html 	利用doc + tab 創建基礎樣式 在<body>部分更改顯示文字
```

### VUE 第2集

```html
在<head>進行vue cdn的設置<script src="https://unpkg.com/vue@3"></script>
```

	在資料夾底下添加app.js

```html
在index.html <body>添加 <script src="app.js"></script>讓html可以偵測到app.js
```

```
	const app = Vue.creatApp()創建app
	app.mount('#app')將app掛載到dom 讓他運作
```

```
	div#app + tab 創建<div id="app"></div>讓元素可以訪問運作
	可在內部creatApp({})內添加各種html <div><div> 	或是直接在<div id="app"><div><div><div>添加狀態
```

```
	在Vue.createApp當中添加data(){return{ 變數:數字 || 字串 || 布林值}}
	html可對data當中的變數讀取<div id="app"><h2> {{變數}}</h2></div>
```

```
	<button @click="變數++">增加變數1</button>
```

```
	methods:{
    changeTitle(abc){
	    console.log(“觸發”)
	    this.title = “巴拉巴拉”
	
    如果要將()將內的abc帶入
        this.title = abc 那麼title會=changeTitle()內的東西也就是"顯示abc"
        }
    }
<button @click="changeTitle("顯示abc")>觸發changeTitle</button>
```

```
	html 進行show的切換 運行toggleShowBooks()方法
				<button @click="toggleShowBooks">
            <span>切換showBooks的true或false</span>
        </button>
```

toggleShowBooks()方法利用button觸發後會將showBooks變更 如果true 則 = false如果為false則 = true
```
	
toggleShowBooks(){
	this.showBooks = !this.showBooks
},

return {
	title:'123321',
	age:2,
	showBooks:true,
	}
			
如果showBooks = true 就會顯示

<div v-show="showBooks">
	<h2> {{title}} -- {{age}}</h2>
</div>
<div v-if="showBooks">
	<h2> {{title}} -- {{age}}</h2>
</div>
		
```
if與show的差別是 if會將整個dom刪除 而show只是將style 改為不顯示

### VUE 第3集

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































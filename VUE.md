####
事先準備 雙字幕 幫助之後看VUE https://chrome.google.com/webstore/detail/youtube-dual-subtitles/hkbdddpiemdeibjoknnofflfgbgnebcm
每一項一定都要全部跟著做一次 影片內的東西 能理解很好 不能也沒事 盡力去想
html https://youtu.be/CLUPkcLQm64 ->
css https://youtu.be/Ml78vnNTBLw ->
js https://youtu.be/yZwlW5INhgk ->
vue https://youtu.be/YrxBCBibVo0 1~6 ->
都完成後請至櫃台找mike大哥領取任務 邊寫邊問問題 不懂的可以問我 我算比較閒的
可不可以給我換黑底 很傷眼睛 可不可以給我換黑底 很傷眼睛 可不可以給我換黑底 很傷眼睛 很傷眼睛  很傷眼睛很傷眼睛很傷眼睛很傷眼睛很傷眼睛很傷眼睛很傷眼睛
VUE 第1集 
   	 添加index.html 	利用doc + tab 創建基礎樣式 在<body>部分更改顯示文字
####
VUE 第2.3集(未完成)
     	在<head>進行vue cdn的設置<script src="https://unpkg.com/vue@3"></script>

在資料夾底下添加app.js 並在index.html <body>添加 
<script src="app.js"></script>讓html可以偵測到app.js

	const app = Vue.creatApp()創建app
	app.mount('#app')將app掛載到dom 讓他運作

	div#app + tab 創建<div id="app"></div>讓元素可以訪問運作
	可在內部creatApp({})內添加各種html <div><div>

或是直接在<div id="app"><div><div><div>添加狀態

	在Vue.createApp當中添加data(){return{ 變數:數字 || 字串 || 布林值}}html可對data當中的變數讀取<div id="app"><h2> {{變數}}</h2></div>

	<button @click="變數++">增加變數1</button>

	methods:{
changeTitle(abc){
console.log(“觸發”)
this.title = “巴拉巴拉”

如果要將()將內的abc帶入
this.title = abc 那麼title會=顯示abc
}
}
<button @click="changeTitle("顯示abc")>觸發changeTitle</button>

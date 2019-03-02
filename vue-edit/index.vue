<template>
	<div class="atuser">
		<atuser :members="members" @enterSend="send" v-model="inputcontent" @cursorRect="cursorRect"></atuser>
		<edit></edit>
	</div>
</template>

<script>
	import atuser from './atuser.vue'
	
	import edit from './edit.vue'
	
	export default {
		data() {
			return {
				members: [123, 12, 1234, 12345, "小花", "小花华", "小三"],
				inputcontent: "" //用户输入内容初始值

			};
		},
		components: {
			atuser,edit
		},
		methods: {
			send(e) { //回车发送
				console.log(e)
			},
			cursorRect(val){
				console.log("当前光标点击位置：")
				console.log(val)
			}
		}
	}
</script>

<style scoped="scoped" lang="less">
	.atuser {
		width: 700px;
		height: 160px;
		border: 1px solid red;
		.editor{
			width: 700px;
			height: 160px;
			overflow: hidden;
			border: 0px;
			outline: none;
			resize: none;
	       -webkit-appearance: none;
		}
	}
</style>
<template>
	<div class="atuser">
		<at :members="members" @enterSend="send" v-model="inputcontent">
			<textarea class="editor"></textarea>
		</at>
	</div>
</template>

<script>
	import at from './atuser.vue'
	export default {
		data() {
			return {
				members: [123, 12, 1234, 12345, "小花", "小花华", "小三"],
				inputcontent: "" //用户输入内容初始值

			};
		},
		components: {
			at,
		},
		methods: {
			send(e) { //回车发送
				console.log(e)
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
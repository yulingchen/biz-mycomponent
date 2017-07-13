<template>
	<div class="wrap">
		<h1>{{title}}</h1>
		<a href="javascript:;" @click="toInner">Click me >></a>
	</div>
</template>

<script>
	export default {
		props:{
			title: {
				type: String,
				default:'Hello world！'
			}
		},
		methods:{
			toInner(){
				this.$router.push('/biz-mycomponent-innerPage')
			}
		}
	}
</script>

<style lang="less">
	.wrap{
		text-align: center;
		padding-top: 30px;

		h1{
			margin-bottom:10px;
		}
	}
</style>

<template>
	<el-form :model="form" label-width="80px">
	  <el-form-item label="欢迎词">
	  	<el-input :value="form.props.title" @change="changeTitle"></el-input>
	  </el-form-item>
	</el-form>
</template>

<script>
	import Vue from 'vue'
	import Form from 'element-ui/lib/form'
	import FormItem from 'element-ui/lib/form-item'
	import Input from 'element-ui/lib/input'

	Vue.component(Form.name, Form)
	Vue.component(FormItem.name, FormItem)
	Vue.component(Input.name, Input)

	export default {
    props:{
      value: Object 
    },
		data() {
      return {
      	form:{
      		props:{
      			title: this.value.props && this.value.props.title
      		}
      	}
      }
    },
    watch:{
      value(){
        this.form.props.title = this.value.props && this.value.props.title
      }
    },
    methods:{
    	changeTitle(title){
    		this.form.props.title = title
        this.$emit('onupdate', this.form)
    	}
    }
	}
</script>
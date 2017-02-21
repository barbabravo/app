<template>
	<div class="page-header-main">
		<header class="mint-header">
			<div class="mint-header-button is-left">
				<a href="/">
					<i class="icon icon-back"></i>
				</a>
			</div> 
			<h1 class="mint-header-title" @click="showToast">我要开户</h1> 
			<div class="mint-header-button is-right">
				<a href="/">
					<i class="icon icon-close"></i>
				</a>
			</div>
		</header>
		<div>
			<ul>
				<li>信息填写</li>
				<li>风险阅读</li>
				<li>手机验证</li>
			</ul>
			<p>
				轻松开户，您只需要准备：
				1. 居民身份证（清晰的彩色照片或清晰的彩色扫描文档）
				2. 手机
			</p>
			<p>如有任何疑问，请向会员单位咨询。</p>
			<div class="mint-cell mint-field">
				<div class="mint-cell-wrapper">
					<div class="mint-cell-title"> 
						<span class="mint-cell-text">开户邀请码</span> 
					</div> 
					<div class="mint-cell-value">
						<input placeholder="请输入用户名" type="text" class="mint-field-core" maxlength="10">  
						<div class="mint-field-clear" style="display: none;">
							<i class="mintui mintui-field-error"></i>
						</div> 
						<span class="mint-field-state is-default"><i class="mintui mintui-field-default"></i></span> 
						<div class="mint-field-other"></div>
					</div>
				</div>  
			</div>
			<div class="identify-wrapper clearfix">
				<div class="identify-part front">
					<img src="../../public/images/identify-front.jpg" alt="">
				</div>
				<div class="identify-part front">
					<img src="../../public/images/identify-front.jpg" alt="">
				</div>				
			</div>
			<mt-actionsheet
			  :actions="actions"
			  v-model="sheetVisible">
			</mt-actionsheet>
		</div>
	</div>
</template>

<style lang="less">
	html{
		font-size:62.5%;
	}
	body{
		margin:0;
		font-size:1.6rem;
	}
	.identify-wrapper{
		display: table;
		width:100%;
		vertical-align:middle;
		text-align: center;
		padding:1rem;
		box-sizing:border-box;
	}
	.identify-part{
		display:table-cell;
		background-color:#efefef;
		border:1px solid #d4d4d4;
		padding:1rem;
		img{
			width:10rem;
			height:auto;
		}
		&.front{
		}
		&.back{
		}
	}
</style>

<script>
import "mint-ui/lib/style.css";
import "../../public/less/reset.less";
import "../../public/less/base.less";

import Vue from 'vue'
import {
	Button, 
	Cell, 
	Toast, 
	Indicator,
	MessageBox,
	Actionsheet
} from 'mint-ui'
import vuex from 'vuex'
import vueRouter from 'vue-router'

Vue.component(Button.name, Button)
Vue.component(Cell.name, Cell)
Vue.component(Actionsheet.name, Actionsheet);

export default {
	data(){
		return {
			sheetVisible:false,
			actions:[{
				name:'aaa',
				method:this.aaa
			},{
				name:'bbb',
				method:this.bbb
			}]
		}
	},
	mounted(){
		
	},
	methods:{
		aaa(){
			console.log('aaa')
		},
		bbb(){
			console.log('bbb')
		},
		showToast(){
			this.sheetVisible = true
			MessageBox('提示', '操作成功');
			let instance = Toast({
			  message: '操作成功',
			  iconClass: 'icon icon-roundcheck'
			});
			Indicator.open({
			  text: '加载中...',
			  spinnerType: 'fading-circle'
			});
		}
	}
};
</script>

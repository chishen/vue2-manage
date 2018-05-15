<template>
	<div class="manage_page fillcontain">
		<el-row style="height: 100%;padding-left: 240px;position: relative;">
	  		<el-col style="min-height: 100%;width: 240px;position: absolute;left: 0;top: 0;bottom: 0;">
				<el-menu
                    :default-active="defaultActive"
                     style="min-height: 100%;"
                     background-color="#333"
                     text-color="#fff"
                     router>
                    <el-submenu index="7">
                        <template slot="title"><i class="el-icon-menu"></i>内容管理</template>
                        <el-menu-item index="news">企业动态</el-menu-item>
                        <el-menu-item index="team">蜜蜂团队</el-menu-item>
                        <el-menu-item index="video">视频</el-menu-item>
                        <el-menu-item index="link">友情链接</el-menu-item>
                        <el-menu-item index="topics">蜜蜂专题</el-menu-item>
                    </el-submenu>
                    <el-submenu index="8">
                        <template slot="title"><i class="el-icon-document"></i>用户管理</template>
                        <el-menu-item index="applyList">申请列表</el-menu-item>
                    </el-submenu>
                    <!--<el-menu-item index="applyList"><i class="el-icon-document"></i>申请列表</el-menu-item>-->
                    <el-submenu index="9">
                        <template slot="title"><i class="el-icon-setting"></i>设置</template>
                        <el-menu-item index="setting">设置全站参数</el-menu-item>
                    </el-submenu>
                    <el-menu-item index="manage"><i class="el-icon-menu"></i>首页</el-menu-item>
					<el-submenu index="2">
						<template slot="title"><i class="el-icon-document"></i>数据管理</template>
						<el-menu-item index="userList">用户列表</el-menu-item>
						<el-menu-item index="shopList">商家列表</el-menu-item>
						<el-menu-item index="foodList">食品列表</el-menu-item>
						<el-menu-item index="orderList">订单列表</el-menu-item>
						<el-menu-item index="adminList">管理员列表</el-menu-item>
					</el-submenu>
					<el-submenu index="3">
						<template slot="title"><i class="el-icon-plus"></i>添加数据</template>
						<el-menu-item index="addShop">添加商铺</el-menu-item>
						<el-menu-item index="addGoods">添加商品</el-menu-item>
					</el-submenu>
					<el-submenu index="4">
						<template slot="title"><i class="el-icon-star-on"></i>图表</template>
						<el-menu-item index="visitor">用户分布</el-menu-item>
						<!-- <el-menu-item index="newMember">用户数据</el-menu-item> -->
					</el-submenu>
					<el-submenu index="5">
						<template slot="title"><i class="el-icon-edit"></i>编辑</template>
						<!-- <el-menu-item index="uploadImg">上传图片</el-menu-item> -->
						<el-menu-item index="vueEdit">文本编辑</el-menu-item>
					</el-submenu>
					<el-submenu index="6">
						<template slot="title"><i class="el-icon-setting"></i>设置</template>
						<el-menu-item index="adminSet">管理员设置</el-menu-item>
						<!-- <el-menu-item index="sendMessage">发送通知</el-menu-item> -->
					</el-submenu>
					<el-submenu index="7">
						<template slot="title"><i class="el-icon-warning"></i>说明</template>
						<el-menu-item index="explain">说明</el-menu-item>
					</el-submenu>
				</el-menu>
			</el-col>
			<el-col style="height: 100%;overflow: auto;width: 100%;">
				<keep-alive>
				    <router-view></router-view>
				</keep-alive>
			</el-col>
		</el-row>
  	</div>
</template>

<script>
    export default {
		computed: {
			defaultActive: function(){
				return this.$route.path.replace('/', '');
			}
		},
    }
</script>


<style lang="less" scoped>
	@import '../style/mixin';
	.manage_page{

	}
</style>

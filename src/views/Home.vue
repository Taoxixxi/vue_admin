<template>
  <div class="home">
    <el-container>
      <!-- 头部 -->
      <el-header>
        <div class="header">
          <div>
            <img alt="Vue logo" src="../assets/logo.png" />
            <i class="el-icon-s-fold" v-if="!isCollapse" @click="isShowAll"></i>
            <i class="el-icon-s-unfold" v-else @click="isShowAll"></i>
          </div>
          <span>管理员</span>
        </div>
      </el-header>
      <!-- 主体 -->
      <el-container>
        <!-- 侧边栏 -->
        <el-aside>
          <el-menu
            default-active="1-4-1"
            class="el-menu-vertical-demo"
            @open="handleOpen"
            @close="handleClose"
            :collapse="isCollapse"
            background-color="#545c64"
            text-color="#fff"
            active-text-color="#ffd04b"
          >
            <el-submenu index="1">
              <template slot="title">
                <i class="el-icon-location"></i>
                <span>导航一</span>
              </template>
              <el-menu-item-group>
                <el-menu-item index="1-1">
					<router-link to="/test">选项1</router-link>
					</el-menu-item>
                <el-menu-item index="1-2">
					<router-link to="/page2">选项2</router-link>
					</el-menu-item>
                <el-menu-item index="1-3">选项3</el-menu-item>
              </el-menu-item-group>
              <el-submenu index="1-4">
                <template slot="title">选项4</template>
                <el-menu-item index="1-4-1">选项1</el-menu-item>
              </el-submenu>
            </el-submenu>
            <el-menu-item index="2">
              <i class="el-icon-menu"></i>
              <span slot="title">导航二</span>
            </el-menu-item>
            <el-menu-item index="3">
              <i class="el-icon-document"></i>
              <span slot="title">导航三</span>
            </el-menu-item>
            <el-menu-item index="4">
              <i class="el-icon-setting"></i>
              <span slot="title">导航四</span>
            </el-menu-item>
          </el-menu>
        </el-aside>
        <el-container>
          <el-main>
			  Main
			  <router-view/>
			  </el-main>

          <!-- <el-footer>Footer</el-footer> -->
        </el-container>
      </el-container>
    </el-container>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "home",
  components: {},
  data() {
    return {
      isCollapse: false
    };
  },
  methods: {
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    },
    isShowAll() {
      this.isCollapse = !this.isCollapse;
    }
  }
};
</script>
<style lang="less">
a{
	color: #fff;
	text-decoration: none;
}
.el-header {
  background-color: #b3c0d1;
  // color: #fff;
  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: inherit;
    img {
      width: 3rem;
    }
  }
}
.el-aside {
  width: fit-content !important;
}
.el-menu-vertical-demo:not(.el-menu--collapse) {
  width: 200px;
  min-height: 400px;
}
</style>

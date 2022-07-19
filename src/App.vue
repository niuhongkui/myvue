<template>
  <div id="app">
    <el-container>
      <el-header class="header"></el-header>
      <el-container>
        <el-aside class="aside">
          <el-menu :default-openeds="['1', '2']">
            <el-submenu index="1">
              <template slot="title"><i class="el-icon-message"></i>导航一</template>
              <el-menu-item-group>
                <template slot="title">分组一</template>
                <el-menu-item @click="navTo('/home')" index="1-1">Home</el-menu-item>
                <el-menu-item @click="navTo('/')" index="1-2">HelloWorld</el-menu-item>
              </el-menu-item-group>
              <el-menu-item-group title="分组2">
                <el-menu-item index="1-3">选项3</el-menu-item>
              </el-menu-item-group>
              <el-submenu index="1-4">
                <template slot="title">选项4</template>
                <el-menu-item index="1-4-1">选项4-1</el-menu-item>
              </el-submenu>
            </el-submenu>
            <el-submenu index="2">
              <template slot="title"><i class="el-icon-menu"></i>导航二</template>
              <el-menu-item-group>
                <template slot="title">分组一</template>
                <el-menu-item index="2-1">选项1</el-menu-item>
                <el-menu-item index="2-2">选项2</el-menu-item>
              </el-menu-item-group>
              <el-menu-item-group title="分组2">
                <el-menu-item index="2-3">选项3</el-menu-item>
              </el-menu-item-group>
              <el-submenu index="2-4">
                <template slot="title">选项4</template>
                <el-menu-item index="2-4-1">选项4-1</el-menu-item>
              </el-submenu>
            </el-submenu>
          </el-menu>
        </el-aside>
        <el-container>
          <el-main class="main">
            <router-view />
          </el-main>
          <el-footer class="footer"></el-footer>
        </el-container>
      </el-container>
    </el-container>
  </div>
</template>

<script>
export default {
  name: 'App',
  methods: {
    navTo (path) {
      this.$router.push({ path })
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 97vh;
}

.header {
  background-color: #ddd;
}

.aside {
  background-color: #e3e3e3;
  height: calc(100vh - 70px);
  width: 200px;
  overflow: auto;
}

.aside::-webkit-scrollbar {
  display: none;
}

.footer {
  background-color: #e3e3e3;
}

.main {
  background-color: #f3f3f3;
}
</style>

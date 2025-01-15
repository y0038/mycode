<template>
  <div id="app">
    <el-container style="height: 1000px; ">
      <el-aside style="background-color:#39465C ;overflow: hidden;min-height: 100vh;width: 270px;">
        <div style="height: 70px; display: flex; align-items: center; justify-content: center;">
          <img src="@/assets/logo.png" alt="" style="height: 40px; width: 40px;">
          <span style="color: white; margin-left: 10px;">慢慢做好毕设</span>
        </div>
        <el-menu>

          <el-submenu index="1">
            <template slot="title"><i class="el-icon-user"></i>用户管理</template>
            <el-menu-item index="1-1">选项1</el-menu-item>
            <el-menu-item index="1-2">选项2</el-menu-item>
          </el-submenu>
          <el-submenu index="2">
            <template slot="title"><i class="el-icon-menu"></i>信息管理</template>
            <el-menu-item index="2-1">选项1</el-menu-item>
            <el-menu-item index="2-2">选项2</el-menu-item>
          </el-submenu>
          <el-submenu index="3">
            <template slot="title"><i class="el-icon-setting"></i>系统设置</template>
            <el-menu-item-group>
              <template slot="title">分组一</template>
              <el-menu-item index="3-1">选项1</el-menu-item>
              <el-menu-item index="3-2">选项2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="分组2">
              <el-menu-item index="3-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="3-4">
              <template slot="title">选项4</template>
              <el-menu-item index="3-4-1">选项4-1</el-menu-item>
            </el-submenu>
          </el-submenu>
        </el-menu>
      </el-aside>

      <el-container>
        <el-header style="text-align: right; font-size: 12px;">
          <img src="@/assets/avtar.jpg" alt=""
               style="height: 40px; width: 40px;border-radius: 50%;margin-right: 10px; vertical-align: middle;">
          <span
              style="color: #4c5a73;font-weight: bold;font-size: 14px;margin-right: 20px; vertical-align: middle;">王小虎</span>
          <el-dropdown>
            <i class="el-icon-setting" style="margin-left: 10px"></i>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>个人空间</el-dropdown-item>
              <el-dropdown-item>退出登录</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
        </el-header>

        <el-main>
          <el-table :data="tableData">
            <el-table-column prop="date" label="日期" width="140">
            </el-table-column>
            <el-table-column prop="name" label="姓名" width="120">
            </el-table-column>
            <el-table-column prop="address" label="地址">
            </el-table-column>
          </el-table>
        </el-main>
      </el-container>
    </el-container>

    <router-view/>
  </div>
</template>
<style>
.el-header {
  background-color: #B3C0D1;
  color: #333;
  line-height: 60px;
}

.el-aside {
  color: #333;
}
</style>

<script>
export default {
  data() {
    const item = {
      date: '2016-05-02',
      name: '王小虎',
      address: '上海市普陀区金沙江路 1518 弄'
    };
    return {
      tableData: Array(20).fill(item)
    }
  }
};
</script>
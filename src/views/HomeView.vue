<template>
  <div>
    <el-container style="height: 500px; border: 1px solid #eee">
      <el-aside width="200px" style="background-color: rgb(238, 241, 246);height: 100vh">
        <el-menu :default-openeds="['1', '3']" style="min-height: 100%;overflow-x: hidden" background-color="rgb(48,65,86)" text-color="#fff" active-text-color="#ffd04b" :collapse-transition="false" :collapse="isCollapse">
          <div style="height: 60px;line-height: 60px;text-align: center;">
            <img src="../assets/logo.png" style="width:20px ;position: relative;top:5px">
            <b style="color: white;">
              后台管理
            </b>

          </div>
          <el-submenu index="1">
            <template slot="title"><i class="el-icon-message"></i>导航一</template>
            <el-menu-item-group>
              <template slot="title">分组一</template>
              <el-menu-item index="1-1">选项1</el-menu-item>
              <el-menu-item index="1-2">选项2</el-menu-item>
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
          <el-submenu index="3">
            <template slot="title"><i class="el-icon-setting"></i>导航三</template>
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
        <el-header style="text-align: right; font-size: 12px; border-bottem:1px solid #ccc;line-height: 60px;display: flex ">
          <div style="flex: 1;font-size: 18px;">
          <span :class="collapseBtnClass" style="cursor: pointer" @click="collapse"></span>
          </div>
          <el-dropdown style="width: 200px">
            <span>王小虎</span>
            <i class="el-icon-arrow-down"></i>
            <i class="el-icon-setting" style="margin-right: 15px"></i>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>查看</el-dropdown-item>
              <el-dropdown-item>新增</el-dropdown-item>
              <el-dropdown-item>删除</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
          
        </el-header>

        <el-main>
          <div style="padding: 10px 0">
            <el-input style="width:200px" placeholder="请输入名称" suffix-icon="el-icon-search"></el-input>
            <el-input style="width:200px" placeholder="请输入邮箱" suffix-icon="el-icon-search"></el-input>
            <el-input style="width:200px" placeholder="请输入地址" suffix-icon="el-icon-search"></el-input>
            <el-button class="ml-5" type="primary">搜索</el-button>

          </div>
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
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import { Collapse } from 'element-ui';

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  },
  data(){
    const item = {
      date: '2016-05-02',
      name: '王小虎',
      address: '上海市普陀区金沙江路 1518 弄'
    };

    return{
      msg:"hello banana",
      tableData: Array(20).fill(item),
      collapseBtnClass:'el-icon-s-fold',
      isCollapse:false
    }
    },
    methods:{
      collapse(){
        this.isCollapse = !this.isCollapse
        if(this.isCollapse){
          this.sideWidth =64
          this.collapseBtnClass = 'el-icon-s-unfold'
          this.logloading

        }

      }
    }
    }
</script>

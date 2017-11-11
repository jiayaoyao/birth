<template>
    <div class="main-left">
        <el-radio-group v-model="isCollapse" style="margin-bottom: 20px;">
        <el-radio-button :label="false">展开</el-radio-button>
        <el-radio-button :label="true">收起</el-radio-button>
        </el-radio-group>
        
        <el-menu default-active="1-4-1" class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose" :collapse="isCollapse">
            
            <el-submenu index="1">
                <template slot="title">
                    <i class="el-icon-location"></i>
                    <span slot="title">导航一</span>
                </template>
                <el-menu-item-group>
                  <el-menu-item index="1-1"><row cols="24"/></el-menu-item>
                  <el-menu-item index="1-2"><row cols="12,12"/></el-menu-item>
                  <el-menu-item index="1-3"><row cols="8,8,8"/></el-menu-item>
                  <el-menu-item index="1-4"><row cols="6,6,6,6"/></el-menu-item>
                  <el-menu-item index="1-5"><row cols="4,4,4,4,4,4"/></el-menu-item>
                  <el-menu-item index="1-6"><row cols="6,18"/></el-menu-item>
                  <el-menu-item index="1-7"><row cols="18,6"/></el-menu-item>
                  <el-menu-item index="1-8"><listtable /></el-menu-item>
                </el-menu-item-group>
            </el-submenu>
            
        </el-menu>
        
    </div>
</template>

<script>
import row from "./Row";
import listtable from "./Table"
export default {
  name: "controls",
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
    }
  },
  computed: {
  },
  components: {
    row,
    listtable
  }
};
</script>

<style>
.main-left {
  text-align: center;
  max-width: 500px;
  float: left;
  border: 1px solid red;
}
.el-menu {
  background-color: transparent !important;
}
.el-menu-vertical-demo:not(.el-menu--collapse) {
  width: 200px;
  min-height: 400px;
}
.my-handle {
  cursor: move;
  cursor: -webkit-grabbing;
}
</style>
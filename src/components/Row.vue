<template>
  <drag>
  <el-row :gutter="10">
    <el-col v-for="col in cols.split(',')" v-bind:span=+col>
      <drag class="grid-content bg-purple"></drag>
    </el-col>
  </el-row>
  </drag>
</template>

<script>
import draggable from "vuedraggable";
import preview from "./system/Preview";
import drag from "./system/Drag";
export default {
  name: "row",
  data: function() {
    return {

    }
  },
  props: ['cols'],
  components: {
    preview,
    drag
  }
};
</script>
<style>
  .el-row {
    margin-bottom: 20px;
    /* &:last-child {
      margin-bottom: 0;
    }  */
  }
  .el-col {
    border-radius: 4px;
  }
  .bg-purple-dark {
    background: #99a9bf;
  }
  .bg-purple {
    background: #d3dce6;
    border: 1px solid blue;
  }
  .bg-purple-light {
    background: #e5e9f2;
  }
  .grid-content {
    border-radius: 4px;
    min-height: 30px;
  }
  .row-bg {
    padding: 10px 0;
    background-color: #f9fafc;
  }
</style>
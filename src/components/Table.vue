<template>
<draggable :options="dragOptions" element="div" class="drag-handle">
  <div class="box drag-handle" >
    <div class="preview">
      <input value="Table" readonly />
    </div>
    <div class="view">
      <el-table :data="tableData" style="width: 100%">
        <el-table-column prop="date" label="日期" width="180"></el-table-column>
        <el-table-column prop="name" label="姓名" width="180"></el-table-column>
        <el-table-column prop="address" label="地址"></el-table-column>
      </el-table>
    </div>
  </div>
</draggable>
</template>

<script>
import draggable from "vuedraggable";

export default {
  name: "listtable",
  data() {
    return {
      tableData: [
        {
          date: "2016-05-02",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1518 弄"
        },
        {
          date: "2016-05-04",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1517 弄"
        },
        {
          date: "2016-05-01",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1519 弄"
        },
        {
          date: "2016-05-03",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1516 弄"
        }
      ]
    };
  },
  computed: {
    dragOptions() {
      return {
        group: { name: "ctrl", pull: "clone", put: false },
        handle: ".drag-handle",
        forceFallback: true,
        fallbackClass: "sortable-fallback"
      };
    }
  },
  components: {
    draggable
  }
};
</script>
<style>
.el-row {
  margin-bottom: 20px;
}
.el-col {
  border-radius: 4px;
}
.bg-purple {
  background: #d3dce6;
  border: 1px solid blue;
}
.grid-content {
  border-radius: 4px;
  min-height: 30px;
}
.drag-handle {
  cursor: move;
  cursor: -webkit-grabbing;
}
</style>
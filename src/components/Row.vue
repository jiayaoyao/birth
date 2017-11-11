<template>
<draggable :options="dragOptions1" element="div" class="drag-handle">
  <div class="box drag-handle" >
    <div class="preview">
      <input v-bind:value="cols" readonly />
    </div>
    <div class="view">
      <el-row :gutter="10">
        <el-col v-for="col in cols.split(',')" v-bind:span=+col>
          <draggable :options="dragOptions2" element="div" class="grid-content bg-purple">
          </draggable>
        </el-col>
      </el-row>
    </div>
  </div>
</draggable>
</template>

<script>
import draggable from "vuedraggable";

export default {
  name: "row",
  props: ['cols'],
  computed: {
    dragOptions1() {
      return {
        group: { name: "ctrl", pull: "clone", put: false },
        handle: ".drag-handle",
        forceFallback: true,
        fallbackClass: "sortable-fallback"
      };
    },
    dragOptions2() {
      return {
        group: { name: "ctrl", pull: true, put: true },
        handle: ".drag-handle"
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
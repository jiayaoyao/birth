<template>
    <div class="main-right" >
        <draggable :options="dragOptions" element="div" class="draggable-demo" >
        </draggable>
    </div>
</template>

<script>
import draggable from "vuedraggable";
export default {
  name: "demo",
  methods: {
  },
  computed: {
    dragOptions() {
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
.main-right {
  -webkit-box-flex: 1;
  -ms-flex: 1;
  flex: 1;
  background-color: #fff;
  padding: 20px 30px;
  border: 1px solid red;
}
.draggable-demo {
  -webkit-box-flex: 1;
  -ms-flex: 1;
  flex: 1;
  background-color: #fff;
  padding: 20px 30px;
  border: 1px solid blue;
}
.drag-handle {
  cursor: move;
  cursor: -webkit-grabbing;
}
</style>
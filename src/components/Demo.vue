<template>
    <div class="main-right" >
        <drag class="draggable-demo"></drag>
    </div>
</template>

<script>
import drag from "./system/Drag";
export default {
  name: "demo",
  methods: {
  },
  computed: {
    dragOptions() {
      return {
        group: { name: "ctrl", pull: true, put: true },
        disabled: false,
        animation: 0
      };
    }
  },
  components: {
    drag
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
</style>
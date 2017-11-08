<template>
<draggable v-model="myArray" :move="getdata" @update="datadragEnd">
        <transition-group>
            <div v-for="element in myArray" :key="element.id">
                {{element.name}}
            </div>
        </transition-group>
</draggable>
</template>

<script>
export default {
  name: "drag",
  data() {
    return {
      //测试用
      myArray: [
        {
          id: "1",
          name: "aaaaaaaaaaaaa"
        },
        {
          id: "2",
          name: "bbbbbbbbbbbbb"
        },
        {
          id: "3",
          name: "ccccccccccccccc"
        }
      ]
    };
  },
  methods: {
    getdata(evt) {
      console.log(evt.draggedContext.element.id);
    },
    datadragEnd(evt) {
      console.log("拖动前的索引 :" + evt.oldIndex);
      console.log("拖动后的索引 :" + evt.newIndex);
      console.log(this.tags);
    }
  }
};
</script>

<style>

</style>
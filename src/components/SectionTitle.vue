<template>
  <div class="section1">
    <div class="section-title">
      <div class="section-title-text">
        <input type="text" :value="sectionName" />
      </div>
      <div class="section-right">
        <PlusCircle class="plus-circle" @click="addTask()" /><Trush />
      </div>
    </div>
        <draggable
        :list="newTask"
        :disabled="!enabled"
        :move="checkMove"
        @start="dragging = true"
        @end="dragging = false"
      >
    <div class="task" v-for="s in newTask" :key="s">
      <div class="task-left">
        <div class="task-state">
          <div class="task-state-text">CONFIRMED</div>
        </div>
        <div class="task-title">
          <input type="text" :value="xxx" />
        </div>
        <div class="task-date">{{ s.date }}</div>
      </div>
      <div class="task-right"><Dot /><BookMark /></div>
    </div>
    </draggable>
  </div>
</template>

<script>
import draggable from "vuedraggable";
import PlusCircle from "@/icons/PlusCircle.svg";
import Trush from "@/icons/Trush.svg";
import Dot from "@/icons/Dot.svg";
import BookMark from "@/icons/BookMark.svg";
export default {
  data() {
    return {
      newTask: [],
       enabled: true,
      dragging: false,
      xxx: null,
    };
  },
  computed: {
    draggingInfo() {
      return this.dragging ? "under drag" : "";
    }},
  methods: {
    addTask() {
      var xxx = { name: null, date: new Date().toISOString().split("T")[0]};
      this.newTask.push(xxx);
    },
    add: function() {
      this.newTask.push({ name: "Juan "});
    },
    replace: function() {
      this.newTask = [{ name: "Edgard"}];
    },
    checkMove: function(e) {
      window.console.log("Future index: " + e.draggedContext.futureIndex);
    }
  },
  components: {
    PlusCircle,
    Trush,
    Dot,
    BookMark,
    draggable
  },
  props: {
    sectionName: String,
  },
};
</script>

<style lang="scss">
input {
  background: transparent;
  border: none;
}
.plus-circle {
  cursor: pointer;
}
</style>
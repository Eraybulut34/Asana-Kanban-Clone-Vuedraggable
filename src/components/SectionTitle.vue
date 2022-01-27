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
    <div class="task" v-for="s in newTask" :key="s">
      <div class="task-left">
        <div class="task-state">
          <div class="task-state-text">CONFIRMED</div>
        </div>
        <div class="task-title">
          <input type="text" :value="s.name" />
        </div>
        <div class="task-date">{{ s.date }}</div>
      </div>
      <div class="task-right"><Dot /><BookMark /></div>
    </div>
  </div>
</template>

<script>
import PlusCircle from "@/icons/PlusCircle.svg";
import Trush from "@/icons/Trush.svg";
import Dot from "@/icons/Dot.svg";
import BookMark from "@/icons/BookMark.svg";
export default {
  data() {
    return {
      newTask: [],
    };
  },
  methods: {
    addTask() {
      var xxx = { name: null, date: new Date().toISOString().split("T")[0] };
      this.newTask.push(xxx);
    },
  },
  components: {
    PlusCircle,
    Trush,
    Dot,
    BookMark,
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
.plus-circle{
    cursor: pointer;
}
</style>
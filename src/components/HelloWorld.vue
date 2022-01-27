<template>
  <div class="hello">
    {{ newSection }}
    <div class="sections">
      <draggable
        :list="newSection"
        :disabled="!enabled"
        class="list-group"
        ghost-class="ghost"
        :move="checkMove"
        @start="dragging = true"
        @end="dragging = false"
      >
      <SectionTitle v-for="(n,index) in newSection" :key="n" :sectionName="n.name+(index+1)" />
      </draggable>
       <button class="add" @click="addSection"><Plus/>Add Section</button>
    </div>
  </div>
</template>

<script>
//import draggable from "vuedraggable";
//import Dot from "@/icons/Dot.svg";
//import BookMark from "@/icons/BookMark.svg";
import Plus from "@/icons/Plus.svg";
import SectionTitle from "@/components/SectionTitle.vue";

export default {
  name: "HelloWorld",
  components: {
    //draggable,
    //Dot,
    //BookMark,
    Plus,
    SectionTitle,
  },
  data() {
    return {
      newSection: [],
      newTask: [],
    };
  },
  methods: {
    
    addTask() {
      var xxx = { name: null, date: new Date().toISOString().split("T")[0] };
      this.newTask.push(xxx);
    },
    addSection() {
      var xxy = { name: null };
      this.newSection.push(xxy);
    },
  },
};
</script>
<style lang="scss">
.sections {
  display: flex;
  flex-direction: row;
}
.hello {
  background-color: #e5e5e5;
  height: 2000px;
  justify-content: center;
}
.section {
  display: flex;
  flex-direction: column;
  position: relative;
  left: 60px;
  top: 42px;
}
.section-title {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  padding: 10px 20px;
  position: static;
  width: 320px;
  height: 51px;
  left: 0px;
  top: 0px;
  background: #ffffff;
  box-shadow: 0px 0px 2px rgba(118, 96, 126, 0.45);
  border-radius: 2px;
  flex: none;
  order: 0;
  flex-grow: 0;
  margin: 0px 20px;
}

.section-text {
  position: static;
  width: 83px;
  height: 31px;
  left: 20px;
  top: 10px;
  font-family: IBM Plex Sans Devanagari;
  font-style: normal;
  font-weight: 500;
  font-size: 20px;
  line-height: 31px;
  letter-spacing: -0.02em;
  color: #333333;
  flex: none;
  order: 0;
  flex-grow: 0;
  margin: 0px 120px;
}
.plus {
  width: 20px;
  height: 20px;
  left: 0px;
  top: 0px;
  cursor: pointer;
}
.task {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 20px;
  max-width: 100%;
  position: static;
  width: 320px;
  height: 136px;
  top: 0px;
  background: #ffffff;
  box-shadow: 0px 0px 2px rgba(118, 96, 126, 0.45);
  border-radius: 2px;
  flex: none;
  order: 0;
  flex-grow: 0;
  margin: 10px 0px 0px 20px;
}
.task-left {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding: 0px;
  justify-content: space-between;
  position: static;
  width: 108px;
  height: 96px;
  left: 20px;
  top: 20px;

  /* Inside auto layout */

  flex: none;
  order: 0;
  flex-grow: 0;
}
.task-right {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: flex-end;
  padding: 0px;

  position: static;
  width: 25px;
  height: 96px;
  top: 20px;
  flex: none;
  order: 1;
  flex-grow: 0;
}
.task-state {
  display: flex;
  flex-direction: row;
  padding: 7px;
  position: static;
  width: 95px;
  background-color: #9b73aa;
  border-radius: 6px;
}
.task-state-text {
    position: static;
    width: 64px;
    font-family: IBM Plex Sans;
    font-style: normal;
    font-weight: 500;
    align-items: center;
    text-align: center;
    color: #fffdff;
    margin-left: -5px;
    margin-top: -5px;
}
.task-title {
  position: static;
  width: 108px;
  height: 24px;
  left: 0px;
  top: 34px;

  font-family: IBM Plex Sans Devanagari;
  font-style: normal;
  font-weight: normal;
  font-size: 16px;
  line-height: 24px;

  color: #000000;

  /* Inside auto layout */

  flex: none;
  flex-grow: 0;
  margin: 20px 0px;
}
input {
  background: transparent;
  border: none;
}
.add {
  color: white;
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  align-items: center;
  padding: 10px;

  width: 148px;
  height: 51px;

  /* Blue 1 */

  background: #2f80ed;
  border-radius: 6px;
  cursor: pointer;
}
</style>

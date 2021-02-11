<template>
  <div id="app">
    <board id="board"> </board>
    <div style="position:relative; margin:50px">
      <movable
        id="idea_1"
        draggable="true"
        class="testmove"
        posTop="444"
        :grid="20"
        ><span>Idea 1</span></movable
      >
      <movable
        id="idea_2"
        draggable="true"
        class="testmove"
        posTop="222"
        posLeft="222"
        :grid="20"
        ><span>Idea 2</span></movable
      >
    </div>
  </div>
</template>

<script>
import movable from "./components/movable";
import Board from "./components/Board.vue";
export default {
  name: "app",
  components: { movable, Board },
};
</script>

<style>
body {
  padding: 0;
  margin: 0;
  font-family: Helvetica, Arial;
}
.movable {
  cursor: pointer;
}
.testmove {
  display: block;
  position: absolute;
  top: 0;
  height: 150px;
  width: 150px;

  background: rgb(119, 78, 187);
  color: white;
}
.board {
  width: 100%;
  max-width: 300px;
  background-color: #080008;
  padding: 15px;
  height: 40vh;
}
</style>

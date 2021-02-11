<template>
  <div :id="id" class="board" @dragover.prevent @drop.prevent="drop">
    <header>New Ideas</header>
    <slot />
  </div>
</template>

<script>
export default {
  props: ["id"],
  methods: {
    drop(e) {
      const idea_id = e.dataTransfer.getData("idea_id");
      console.log(idea_id);
      const idea = document.getElementById(idea_id);
      idea.style.display = "block";
      e.target.appendChild(idea);
    },
  },
};
</script>

<style>
header {
  background-color: white;
  display: flex;
  justify-content: center;
  padding: 0.5rem;
}
</style>

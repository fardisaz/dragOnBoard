<template>
  <div :id="id" class="board" @dragover.prevent @drop.prevent="drop">
    <header>My Elements</header>
    <slot />
  </div>
</template>

<script>
export default {
  props: ["id"],
  methods: {
    drop(e) {
      const el_id = e.dataTransfer.getData("el_id");
      console.log(el_id);
      const element = document.getElementById(el_id);
      element.style.display = "block";
      e.target.appendChild(element);
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

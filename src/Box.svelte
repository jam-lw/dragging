<script>
  export let showbox = false;
  export let hidebox;

  let held = false;

  function dragstart() {
    held = true;
    setTimeout(() => hidebox(), 0);
  }

  function dragend() {
    held = false;
  }
</script>

<style>
  .box {
    height: 100px;
    width: 100px;
    background-color: black;
    position: relative;
    top: 5px;
    left: 5px;
    cursor: pointer;
  }

  .held {
    border: solid 10px black;
    background-color: black;
  }

  .invisible {
    display: none;
  }
</style>

<div class="box" class:invisible={!showbox} draggable="true" on:dragstart={dragstart} on:dragend={dragend} />

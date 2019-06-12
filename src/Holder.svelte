<script>
  import { Box } from "./components.js";

  export let showbox = false;

  let hovered = false;

  const dragenter = () => hovered = true;
  const dragleave = () => hovered = false;
  const drop = () => {
    showbox = true;
    hovered = false;
  }
  const hidebox = () => showbox = false;
</script>

<style>
  .holder {
    height: 110px;
    width: 110px;
    margin: 10px;
    border: solid 5px black;
    background-color: white;
    display: inline-block;
  }

  .hovered {
    border: dotted 5px black;
  }
</style>

<div class="holder" class:hovered on:dragover|preventDefault on:dragenter|preventDefault={dragenter}
  on:dragleave={dragleave} on:drop={drop}>
  {#if showbox}
    <Box showbox={showbox} hidebox={hidebox} />
  {/if}
</div>

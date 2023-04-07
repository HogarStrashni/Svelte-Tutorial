<script lang="ts">
  //event dispatcher
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  let mousePosititon = {
    posX: 0,
    posY: 0,
  };

  let { posX, posY } = mousePosititon;

  const mouseMoveHandler = (event) => {
    posX = event.clientX;
    posY = event.clientY;
  };

  const alertHandler = () => {
    // event modifiers - once; self; stopPropagation; preventDefault; capture; trusted
    alert("Alert just once");

    // dispatch event
    dispatch("helloAlert", {
      text: "Hello World!",
    });
  };
</script>

<div
  class="m-4 flex items-center justify-center border py-8"
  on:mousemove={mouseMoveHandler}
>
  Mouse position is {posX} x {posY}
</div>

<div class="flex justify-center">
  <!-- after one click, handler has been removed  -->
  <button on:click|once={alertHandler} class="rounded-lg border px-4 py-2">
    Click me several times, I'll do it just once
  </button>

  <!-- forwards to parent -->
  <button on:click class="rounded-lg border px-4 py-2">
    Forward to parent
  </button>
</div>

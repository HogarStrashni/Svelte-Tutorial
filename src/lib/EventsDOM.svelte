<script lang="ts">
  let mousePosititon = {
    posX: 0,
    posY: 0,
  };

  let { posX, posY } = mousePosititon;

  const mouseMoveHandler = (event) => {
    posX = event.clientX;
    posY = event.clientY;
  };

  console.log(mousePosititon);
</script>

<div
  class="flex w-full items-center justify-center border"
  on:mousemove={mouseMoveHandler}
>
  Mouse position is {posX} x {posY}
</div>

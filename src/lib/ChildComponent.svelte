<script lang="ts">
  export let numberOne = 1;
  export let numberTwo = 2;

  const sumOfNums = (a: number, b: number) => a + b;
</script>

<div class="flex w-full flex-col items-center pt-4">
  <p>Number One is {numberOne}</p>
  <p>Number Two is {numberTwo}</p>
  <p>Sum: {sumOfNums(numberOne, numberTwo)}</p>
</div>

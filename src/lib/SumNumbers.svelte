<script lang="ts">
  let numbers = [1, 2, 3];

  const addNumber = () => (numbers = [...numbers, numbers.length + 1]);

  $: sumAllNumbers = numbers.reduce((acc, num) => acc + num, 0);
</script>

<div class="mt-4 flex flex-col items-center text-2xl font-light text-gray-200">
  <p>
    {numbers.join(" + ")} = {sumAllNumbers}
  </p>

  <button
    class="mt-1 rounded-lg border px-4 py-2 text-base"
    on:click={addNumber}
  >
    Add a number</button
  >
</div>

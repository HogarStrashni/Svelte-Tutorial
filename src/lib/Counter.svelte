<script lang="ts">
  let count: number = 0;

  $: doubled = count * 2;

  $: {
    if (count >= 5) {
      console.log("Not allowed!");
      alert("Not allowed!");
      count = 4;
    }
  }

  const incrementCount = () => {
    count += 1;
  };
</script>

<button
  on:click={incrementCount}
  class="my-2 rounded-lg border border-gray-200 px-4 py-2 text-gray-200"
>
  Button clicked {count}
  {count === 1 ? "time" : "times"}! Doubled is {doubled}
</button>

<script lang="ts">
  import Counter from "./lib/Counter.svelte";
  import SumNumbers from "./lib/SumNumbers.svelte";
  import "./app.css";

  const someData = [
    { id: 1, name: "Button 1" },
    { id: 2, name: "Button 2" },
    { id: 3, name: "Button 3" },
  ];
</script>

<main
  class="flex h-full flex-col items-center justify-center overflow-auto bg-black"
>
  <Counter />
  <SumNumbers />
</main>

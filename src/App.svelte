<script lang="ts">
  import Counter from "./lib/Counter.svelte";
  import SumNumbers from "./lib/SumNumbers.svelte";
  import ChildComponent from "./lib/ChildComponent.svelte";
  import "./app.css";

  const numbers = {
    numberOne: 25,
    numberTwo: 15,
  };
</script>

<main
  lang="ts"
  class="flex h-full flex-col items-center justify-center overflow-auto bg-black text-gray-200"
>
  <Counter />
  <SumNumbers />
  <ChildComponent numberOne={15} numberTwo={10} />

  <!-- without values - defaults -->
  <ChildComponent />

  <!-- values - with spread operator -->
  <ChildComponent {...numbers} />
</main>

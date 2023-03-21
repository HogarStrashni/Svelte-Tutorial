<script lang="ts">
  import Counter from "./lib/Counter.svelte";
  import SumNumbers from "./lib/SumNumbers.svelte";
  import ChildComponent from "./lib/ChildComponent.svelte";
  import LogicBlocks from "./lib/LogicBlocks/LogicBlocks.svelte";
  import LogicBlocksFetchOnClick from "./lib/LogicBlocks/LogicBlocksFetchOnClick.svelte";
  import EventsDOM from "./lib/EventsDOM.svelte";
  import "./app.css";

  const numbers = {
    numberOne: 25,
    numberTwo: 15,
  };
</script>

<main
  lang="ts"
  class="flex min-h-full flex-col items-center justify-center overflow-auto bg-black py-8 text-gray-200"
>
  <Counter />
  <SumNumbers />
  <ChildComponent numberOne={15} numberTwo={10} />

  <!-- without values - defaults -->
  <ChildComponent />

  <!-- values - with spread operator -->
  <ChildComponent {...numbers} />

  <!-- getting data on initial load -->
  <LogicBlocks />

  <!-- getting data on click event -->
  <LogicBlocksFetchOnClick />

  <EventsDOM />
</main>

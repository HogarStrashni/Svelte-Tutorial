<script lang="ts">
  import "./app.css";
  import Counter from "./lib/Counter.svelte";
  import SumNumbers from "./lib/SumNumbers.svelte";
  import ChildComponent from "./lib/ChildComponent.svelte";
  import LogicBlocks from "./lib/LogicBlocks/LogicBlocks.svelte";
  import LogicBlocksFetchOnClick from "./lib/LogicBlocks/LogicBlocksFetchOnClick.svelte";
  import EventsDOM from "./lib/EventsDOM.svelte";
  import Binding from "./lib/Binding.svelte";

  const numbers = {
    numberOne: 25,
    numberTwo: 15,
  };

  const { numberOne: num1, numberTwo: num2 } = numbers;
</script>

<main lang="ts" class="overflow-auto bg-black py-8 text-gray-200">
  <section class="flex flex-col items-center justify-center overflow-auto">
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
  </section>
  <EventsDOM
    on:helloAlert={() => alert(`Via Dispatcher: Sum = ${num1 + num2}`)}
    on:click={() => alert("Button forward")}
  />
  <section class="mt-4 py-2">
    <Binding />
  </section>
</main>

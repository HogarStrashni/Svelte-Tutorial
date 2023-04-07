<script lang="ts">
  let name = "World";
  let number = 2;

  let isChecked = false;
</script>

<div class="mx-auto flex w-96 flex-col">
  <!-- text -->
  <label for="name" class="mr-2">Name</label>
  <input
    type="text"
    id="name"
    placeholder="Enter name..."
    class="rounded py-1 px-2 text-gray-900"
    bind:value={name}
  />
  <!-- number -->
  <label for="number" class="mr-2">Number</label>
  <input
    type="number"
    id="number"
    placeholder="Enter number..."
    class="rounded py-1 px-2 text-gray-900"
    bind:value={number}
  />
</div>

<h2 class="mx-auto my-1 w-96">Hello, {name}!</h2>
<h2 class="mx-auto mb-1 w-96">This is number: {number}!</h2>

<!-- checkbox -->
<label for="checkbox" class="m-4 flex items-center">
  <input
    type="checkbox"
    id="checkbox"
    bind:checked={isChecked}
    class="mr-2 h-4 w-4"
  />
  I agree to the terms and conditions
</label>

<button
  disabled={!isChecked}
  class="mx-4 rounded-lg border border-green-500 py-2 px-4 text-green-500 disabled:cursor-not-allowed disabled:border-gray-600 disabled:text-gray-600"
  >CONTINUE</button
>

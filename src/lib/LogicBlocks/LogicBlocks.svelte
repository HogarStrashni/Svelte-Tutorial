<script lang="ts">
  import Person from "./Person.svelte";

  interface IUserData {
    id: number;
    name: string;
    username: string;
    email: string;
    address: {
      street: string;
      suite: string;
      city: string;
      zipcode: string;
      geo: {
        lat: string;
        lng: string;
      };
    };
    phone: string;
    website: string;
    company: {
      name: string;
      catchPhrase: string;
      bs: string;
    };
  }

  interface IAllUsers {
    allUsersData: Array<IUserData> | undefined;
    loading: boolean;
  }

  let numberOne = 20;
  let numberTwo = 12;

  const changeValue = () => (numberOne -= 4);

  let people = [
    { id: 101, firstName: "Bob", lastName: "Melone" },
    { id: 202, firstName: "John", lastName: "Williamson" },
    { id: 303, firstName: "Janis", lastName: "Tosh" },
  ];

  let allUsers: IAllUsers = {
    allUsersData: undefined,
    loading: false,
  };

  const getAllUsers = async () => {
    allUsers.loading = true;
    const response = await fetch("https://jsonplaceholder.typicode.com/users");
    const data: Array<IUserData> = await response.json();

    if (response.ok) {
      return data;
    } else {
      throw new Error("Something went wrong! Try again!");
    }
  };
</script>

<button class="mt-4 rounded-lg border px-4 py-2" on:click={changeValue}>
  {#if numberOne > numberTwo}
    {numberOne} is greater then {numberTwo}
  {:else if numberOne === numberTwo}
    {numberOne} is equal {numberTwo}
  {:else}
    {numberOne} is lower than {numberTwo}
  {/if}
</button>

<div class="mt-4 flex w-full flex-col items-center">
  {#each people as { id, firstName, lastName } (id)}
    <Person {id} {firstName} {lastName} />
  {/each}
</div>

<div class="mt-4 flex w-full flex-col items-center">
  {#await getAllUsers()}
    <p>Loading Spinner Component...</p>
  {:then allUsers}
    {#each allUsers as { id, name, email } (id)}
      <div>
        <p>{name} / {email}</p>
      </div>
    {/each}
  {:catch error}
    <p>{error.message}</p>
  {/await}
</div>

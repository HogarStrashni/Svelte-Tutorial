<script lang="ts">
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

  let allUsers: IAllUsers = {
    allUsersData: undefined,
    loading: false,
  };

  const getAllUsers = async () => {
    allUsers.loading = true;
    const response = await fetch("https://jsonplaceholder.typicode.com/users");
    const data: Array<IUserData> = await response.json();

    if (response.ok) {
      return (allUsers = {
        allUsersData: data,
        loading: false,
      });
    } else {
      throw new Error("Something went wrong! Try again!");
    }
  };
</script>

<button
  class="mt-4 rounded-lg border border-gray-200 py-2 px-4"
  on:click={() => {
    getAllUsers();
  }}
>
  GetUsers
</button>

{#if allUsers.loading === true}
  <p>Loading Spinner Component...</p>
{:else}
  {#each allUsers.allUsersData || [] as { id, name, email } (id)}
    <div>
      <p>{name} / {email}</p>
    </div>
  {/each}
{/if}

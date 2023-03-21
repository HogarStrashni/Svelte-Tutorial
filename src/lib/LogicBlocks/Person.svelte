<script lang="ts">
  export let id: number;
  export let firstName: string;
  export let lastName: string;
</script>

<section class="flex justify-center">
  <span class="mr-2">{Math.floor(id / 100)}.</span>
  <p>{firstName} {lastName}</p>
</section>

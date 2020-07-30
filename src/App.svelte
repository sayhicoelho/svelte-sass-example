<script>
  import HelloWorld from '@/components/HelloWorld.svelte'
  import TableExample from '@/components/TableExample.svelte'

  export let name
</script>

<main class="container">
  <HelloWorld {name} />
  <p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
  <TableExample />
</main>

<style global lang="scss">
  @import './scss/custom.scss';
</style>

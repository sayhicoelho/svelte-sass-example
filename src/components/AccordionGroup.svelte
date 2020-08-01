<script>
  import { setContext } from 'svelte';

  export let multiple = false
  export let header = true

  const items = new Set()

  setContext('accordion', {
    getMultiple: () => multiple,
    getHeader: () => header,
    getItems: () => items,
    addItem: item => items.add(item),
    deleteItem: item => items.delete(item),
  })
</script>

<div class="accordion-group">
  <slot />
</div>

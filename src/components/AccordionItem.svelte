<script>
  import { onMount, getContext, createEventDispatcher, tick } from 'svelte';

  export let className = ''
  export {className as class}

  const {
    getMultiple,
    getHeader,
    getItems,
    addItem,
    deleteItem
  } = getContext('accordion')

  const multiple = getMultiple()
  const header = getHeader()
  const items = getItems()

  const dispatch = createEventDispatcher();

  let show = false
  let collapsing = false
  let height = null
  let content = null

  $: heightStyle = height !== null ? `height: ${height}px;` : ''

  function collapse() {
    height = content.scrollHeight
    collapsing = true
    show = false

    setTimeout(() => {
      height = null
    }, 5)

    setTimeout(() => {
      show = false
      collapsing = false
    }, 200)
  }

  async function toggle() {
    if (collapsing) return

    if (!show) {
      if (!multiple) {
        items.forEach(item => {
          if (item !== collapse) {
            item()
          }
        })
      }

      collapsing = true

      await tick()

      height = content.scrollHeight

      setTimeout(() => {
        show = true
        height = null
        collapsing = false
      }, 200)
    } else {
      collapse()
    }

    dispatch('toggle', show)
  }

  onMount(() => {
    addItem(collapse)

    return () => {
      deleteItem(collapse)
    }
  })
</script>

<div class={'accordion-item ' + className}>
  {#if header}
    <div class="accordion-header" on:click={toggle}>
      <slot name="header" />
    </div>
  {/if}
  <div class="accordion-content" class:show class:collapsing style={heightStyle} bind:this={content}>
    <div class="accordion-content-inner">
      <slot name="content" />
    </div>
  </div>
</div>

<style lang="css">
  .accordion-header {
    cursor: pointer;
  }

  .accordion-item.show > .accordion-header,
  .accordion-header:hover {
    background-color: #f2f2f2;
  }

  .accordion-content {
    transition: height 200ms ease;
  }

  .accordion-content:not(.show):not(.collapsing) {
    display: none;
  }

  .accordion-content.collapsing {
    height: 0;
    overflow: hidden;
  }
</style>

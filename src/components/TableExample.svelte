<script>
  import Example from '@/components/Example.svelte'
</script>

<table class="table table-striped">
  <thead>
    <tr>
      <th>#</th>
      <th>Name</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Example</td>
      <td>
        <button class="btn btn-primary">
          click me
        </button>
      </td>
    </tr>
  </tbody>
</table>

<Example />

<style lang="scss">
  td {
    color: $customColor;
  }
</style>

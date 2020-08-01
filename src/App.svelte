<script>
  import HelloWorld from '@/components/HelloWorld.svelte'
  import TableExample from '@/components/TableExample.svelte'
  import AccordionGroup from '@/components/AccordionGroup.svelte'
  import AccordionItem from '@/components/AccordionItem.svelte'

  export let name
</script>

<main class="container">
  <HelloWorld {name} />
  <p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
  <TableExample />

  <h2>Accordion 1</h2>
  <AccordionGroup multiple={false}>
    <AccordionItem class="card">
      <div slot="header" class="p-4">
        <h5>ADRIANE APARECIDA BARBOSA DALL’AGLIO</h5>

        <span class="d-block small text-muted mb-1">
          <i class="fa fa-at"></i>
          marcelo.nerys@bdsa.com.br / adriane.barbosa@bdsa.com.br
        </span>
        <span class="d-block small text-muted">
          <i class="fa fa-phone"></i>
          (14) 3161-3161 / (14) 9.9735-5198
        </span>
      </div>
      <div slot="content" class="card-body p-4">
        The accordion 1
      </div>
    </AccordionItem>
    <AccordionItem class="card mt-3">
      <div slot="header" class="p-4">
        <h5>FRANCISCO VERAS TEOTONIO</h5>

        <span class="d-block small text-muted mb-1">
          <i class="fa fa-at"></i>
          marcelo.nerys@bdsa.com.br / adriane.barbosa@bdsa.com.br
        </span>
        <span class="d-block small text-muted">
          <i class="fa fa-phone"></i>
          (14) 3161-3161 / (14) 9.9735-5198
        </span>
      </div>
      <div slot="content" class="card-body p-4">
        The accordion 1
      </div>
    </AccordionItem>
  </AccordionGroup>

  <div style="height: 1px; border-top: 1px solid #f2f2f2; margin: 22px 0px;"></div>
  <h2>Accordion 2</h2>
  <AccordionGroup multiple={false}>
    <AccordionItem class="card">
      <div slot="header" class="p-4">
        <h5>ADRIANE APARECIDA BARBOSA DALL’AGLIO</h5>

        <span class="d-block small text-muted mb-1">
          <i class="fa fa-at"></i>
          marcelo.nerys@bdsa.com.br / adriane.barbosa@bdsa.com.br
        </span>
        <span class="d-block small text-muted">
          <i class="fa fa-phone"></i>
          (14) 3161-3161 / (14) 9.9735-5198
        </span>
      </div>
      <div slot="content" class="card-body p-4">
        The accordion 1
      </div>
    </AccordionItem>
    <AccordionItem class="card mt-3">
      <div slot="header" class="p-4">
        <h5>FRANCISCO VERAS TEOTONIO</h5>

        <span class="d-block small text-muted mb-1">
          <i class="fa fa-at"></i>
          marcelo.nerys@bdsa.com.br / adriane.barbosa@bdsa.com.br
        </span>
        <span class="d-block small text-muted">
          <i class="fa fa-phone"></i>
          (14) 3161-3161 / (14) 9.9735-5198
        </span>
      </div>
      <div slot="content" class="card-body p-4">
        The accordion 1
      </div>
    </AccordionItem>
  </AccordionGroup>
  <p class="mt-3 text-center">&copy; 2020 Example.</p>
</main>

<style global lang="scss">
  @import './scss/custom.scss';
</style>

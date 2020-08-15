<Page name="catalog">
  <Navbar title="Hakkımda" />
  <List>
    {#each products as product, index (product.id)}
      <ListItem
        title={product.title}
        link={`/product/${product.id}/`}
      />
    {/each}
  </List>
</Page>
<script>
  import { f7ready, f7, Page, Navbar, List, ListItem } from 'framework7-svelte';

  let products = [];

  f7ready(() => {
    products = f7.data.products;
  });
</script>

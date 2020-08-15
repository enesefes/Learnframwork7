<Page name="sonuclar">
  <Navbar title="Sonuçlar" />

  <BlockTitle>Form burası sonuç</BlockTitle>
  <div>
    <input type="email" placeholder="Email..." bind:value={email} />
    <input type="password" placeholder="Password..." bind:value={password} />
    <button on:click={login}>Login to Account</button>
  </div>

</Page>
<script>
  import {
    Page,
    Navbar,
    List,
    ListInput,
    ListItem,
    Toggle,
    BlockTitle,
    Row,
    Button,
    Range,
    Block
  } from 'framework7-svelte';

  let email=""
  let password;
  function login (){
    alert("adam ol");
  }
</script>

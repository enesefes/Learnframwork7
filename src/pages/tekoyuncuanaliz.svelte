<Page>
  <Navbar title="adam ol" backLink="Geri" />
    <Toolbar bottom class="fab-morph-target" >
            <Link>jjj</Link>
            <Link>Link 2</Link>
            <Link>Link 3</Link>
    </Toolbar>

  <Fab position="left-top" color="yellow">
    <Icon ios="f7:plus" aurora="f7:plus" md="material:add"></Icon>
    <Icon ios="f7:xmark" aurora="f7:xmark" md="material:close"></Icon>
    <FabButtons position="bottom">
      <FabButton>{users.names}</FabButton>
      <FabButton>2</FabButton>
      <FabButton>3</FabButton>
    </FabButtons>
  </Fab>

  <Fab position="right-top" color="pink">
    <Icon ios="f7:plus" aurora="f7:plus" md="material:add"></Icon>
    <Icon ios="f7:xmark" aurora="f7:xmark" md="material:close"></Icon>
    <FabButtons position="left">
      <FabButton>1</FabButton>
      <FabButton>2</FabButton>
      <FabButton>3</FabButton>
    </FabButtons>
  </Fab>

  <Fab position="center-center" color="green">
    <Icon ios="f7:plus" aurora="f7:plus" md="material:add"></Icon>
    <Icon ios="f7:xmark" aurora="f7:xmark" md="material:close"></Icon>
    <FabButtons position="center">
      <FabButton>1</FabButton>
      <FabButton>2</FabButton>
      <FabButton>3</FabButton>
      <FabButton>4</FabButton>
    </FabButtons>
  </Fab>

  <Fab position="right-bottom" color="orange">
    <Icon ios="f7:plus" aurora="f7:plus" md="material:add"></Icon>
    <Icon ios="f7:xmark" aurora="f7:xmark" md="material:close"></Icon>
    <FabButtons position="top">
      <FabButton label="Action 1">1</FabButton>
      <FabButton label="Action 2">2</FabButton>
      <FabButton label="Action 2">2</FabButton>
      <FabButton label="Action 2">2</FabButton>
    </FabButtons>
  </Fab>

   

    

</Page>
<script>
  import Listim from './list.svelte'
  let users=[];
  import { 
    List,ListInput,Row,Col,Button,Link, Fab,FabButton, Icon,FabButtons,Toolbar,
    Page, Navbar, Block, BlockTitle } from 'framework7-svelte';
</script>

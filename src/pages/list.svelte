<script>
  import {
    f7,
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
    Block,Sheet,PageContent,Popup,NavRight,Link,SwipeoutActions,SwipeoutButton
  } from 'framework7-svelte';
  import { onMount, onDestroy } from 'svelte';

  export let users=[];


  let actions;

  function more() {
    actions.open();
  }
  function mark() {
    f7.dialog.alert('Mark');
  }
  function reply() {
    f7.dialog.alert('Reply');
  }
  function forward() {
    f7.dialog.alert('Forward');
  }
  function onDeleted() {
    f7.dialog.alert('Thanks, item removed!');
  }

  onMount(() => {
    actions = f7.actions.create({
      buttons: [
        [
          {
            text: 'Here comes some optional description or warning for actions below',
            label: true,
          },
          {
            text: 'merhaba',
            onClick:merhaba
          },
          {
            text: 'Action 2',
          },
        ],
        [
          {
            text: 'Cancel',
            bold: true,
          },
        ],
      ],
    });
  });

  onDestroy(() => {
    actions.destroy();
  });
  function merhaba (){
    console.log()
  }
</script>


<BlockTitle>Oyuncular</BlockTitle>
  <List>
  {#each users as user}
    <ListItem swipeout title="{user.names} - {user.number}" >
      <SwipeoutActions left>
        <SwipeoutButton overswipe color="green" onClick={reply}>Reply</SwipeoutButton>
        <SwipeoutButton color="blue" onClick={forward}>Forward</SwipeoutButton>
      </SwipeoutActions>
      <SwipeoutActions right>
        <SwipeoutButton onClick={more}>More</SwipeoutButton>
        <SwipeoutButton color="orange" onClick={mark}>Mark</SwipeoutButton>
        <SwipeoutButton delete overswipe confirmText="Are you sure you want to delete this item?">Delete</SwipeoutButton>
      </SwipeoutActions>
       <input type="text" bind:value={user.names}>
      
    </ListItem>
    
    
  
   {/each} 
  </List>

  
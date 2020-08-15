<Page name="analiz" >
  <Navbar title="Analiz Yap" />

  <Listim users={users}></Listim>
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
  
  

  import PouchDB from 'pouchdb-browser';
  const replicate = PouchDB.sync('db', 'http://127.0.0.1:5984/deniyoruz', {
    live:true,
    retry:true
  }).on('change', async function(i){
    await uptadeContact();
  }).on('error', function(err){
    console.log('hATA VAR canım hata ' + err);
  })
  import {onMount} from 'svelte';
  import Listim from './list.svelte'

  let db = new PouchDB('db');

  let users=[];
  let name="";
  let oNumber="";

  async function addContact(event){

    const newContact ={
      names:name,
      number:oNumber
    }
    //console.log(newContact);
    const sendtoDb = await db.post(newContact);

      if(sendtoDb.ok){
        await uptadeContact();
      }

    name=""
    oNumber=""
  }

  async function uptadeContact (){
    const allContact = await db.allDocs({
      include_docs:true
    });

    users= allContact.rows.map(row => row.doc);
    console.log(users)
  }

  onMount (async() =>{
    await uptadeContact();
  })

    
</script>

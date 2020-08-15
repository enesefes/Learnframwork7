<Page name="home">
  <!-- Top Navbar -->
  <Navbar sliding={false}>
    
    <NavTitle sliding>Handball Analyse</NavTitle>
    
    
  </Navbar>

  <!-- Page content --> 
  <Row>
      <Col width="100" medium="33">
        <BlockTitle>Takım Bilgileri</BlockTitle>
  <Block strong inset>
    <Row>
      <Col>
        <p>
            Burada takım bilgileriniz girebilir ve görebilirsinizç
        </p>
      </Col>      
    </Row>
    <Row>
      <Col>
        <List noHairlinesMd>
          <ListInput
            label="Name"
            floatingLabel
            type="text"
            placeholder="Your name"
            clearButton
            
          >
            <i class="icon demo-list-icon" slot="media"/>
          </ListInput>
        </List>
      </Col>
    </Row>
    <Row>
      <Col>
        <Button on:click={bas} raised fill>Oluştur</Button>
      </Col>
    </Row>
    
    
  </Block>
      </Col>
      <Col width="100" medium="66" >
      <blockquote>Oyuncu Bilgileri</blockquote>
      <Block strong inset>
        <List noHairlinesMd>
    <form on:submit|preventDefault={addContact}>
    <Row>
    <Col>
  <input type="text" placeholder="oyuncu adı soyadı" bind:value={name}>
  <p>{name}</p>
  </Col>
  </Row>
    <Row>
    <Col>
  <input type="number" placeholder="oyuncu numarası" bind:value={oNumber}>
  <p>{oNumber}</p>
  </Col>
  </Row>

    <Row tag="p">
      
      <Col tag="span">
        <Button on:click={addContact} raised fill>Gönder</Button>
      </Col>
      
    </Row>

  </form>
</List>
      </Block>
      </Col>
    </Row> 


    

    
<Listim users={users}></Listim>

  
</Page>
<script>
let neyazdin=""
let basma=0
function bas (){
  basma +=1
}

  import {
    TextEditor,ListInput,Badge,Sheet,PageContent,
    SwipeoutActions, SwipeoutButton,
    Fab, Icon, FabButtons, FabButton,
    CardFooter,
    CardContent,
    CardHeader,
    Card,
    Page,
    Navbar,
    NavLeft,
    NavTitle,
    NavTitleLarge,
    NavRight,
    Link,
    Toolbar,
    Block,
    BlockTitle,
    List,
    ListItem,
    Row,
    Col,
    Button
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
  let user="";

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


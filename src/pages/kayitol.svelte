<Page>
  <Navbar title="Kayıt Ol" backLink="Geri" />
  <BlockTitle>Kayıt Ol</BlockTitle>
 <List noHairlinesMd>
    <ListInput
      label="Name"
      type="text"
      placeholder="Your name"
    ></ListInput>

    <ListInput
      label="E-mail"
      type="email"
      placeholder="E-mail"
    ></ListInput>

    <ListInput
      label="Password"
      type="password"
      placeholder="Password"
    ></ListInput>
  </List>

  <Row tag="p">
        <Col>
          <Button outline color="green">
            Gönder
          </Button>
        </Col>
    </Row>
 
</Page>
<script>
  import { 
    List,ListInput,Row,Col,Button,Link,
    Page, Navbar, Block, BlockTitle } from 'framework7-svelte';
</script>

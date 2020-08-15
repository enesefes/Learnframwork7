<Page>
  <Navbar title="Giriş Yap" backLink="Geri" />
  <BlockTitle>Giriş Yap</BlockTitle>
  <List noHairlinesMd>
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
  import { List,ListInput,Row,Col,Button,Link,
    Page, Navbar, Block, BlockTitle} from 'framework7-svelte';
</script>

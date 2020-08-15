<Page name="settings">
  <Navbar title="Ayarlar" />

  
  
  <BlockTitle>Outline Buttons</BlockTitle>
  <Block strong>
    <Row tag="p">
        <Col>
          <Button outline color="green">
            <Link href="/kayitol/">Kayıt Ol</Link>
          </Button>
        </Col>
    </Row>
    <Row tag="p">
        <Col>
          <Button outline>
            <Link href="/girisyap/">Giriş Yap</Link>
          </Button>
        </Col>
    </Row>
    <Row tag="p">
      <Col>
        <Button outline color="yellow">
          <Link href="/about/">Hakkımızda</Link>
        </Button>
      </Col>
    </Row>
  </Block>

  
</Page>
<script>
  import {
    Col,
    Link,
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
</script>

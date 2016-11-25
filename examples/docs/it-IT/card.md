<script>
  import dateUtil from 'main/utils/date'
  export default {
    data() {
      return {
        currentDate: dateUtil.format(new Date(), 'yyyy-MM-dd HH:mm')
      };
    }
  }
</script>

<style scoped>
  .text {
    font-size: 14px;
  }

  .time {
    font-size: 13px;
    color: #999;
  }

  .bottom {
    margin-top: 13px;
    line-height: 12px;
  }

  .item {
    padding: 18px 0;
  }

  .button {
    padding: 0;
    float: right;
  }

  .image {
    width: 100%;
    display: block;
  }

  .clearfix {
    @utils-clearfix;
  }

  .box-card {
    width: 480px;
  }
</style>
## Card

Visualizza informazioni in un box di tipo Card

### Utilizzo di base

Il componente Card include un titolo, contenuto e operazioni.

:::demo Il componente card è compost da `header` e `body`. `header` è opzionale, la distribuzione del contenuto dipende dallo slot.

```html
<el-card class="box-card">
  <div slot="header" class="clearfix">
    <span style="line-height: 36px;">Nome della Card</span>
    <el-button style="float: right;" type="primary">Bottone</el-button>
  </div>
  <div v-for="o in 4" class="text item">
    {{'Elemento ' + o }}
  </div>
</el-card>

<style>
  .text {
    font-size: 14px;
  }

  .item {
    padding: 18px 0;
  }

  .clearfix:before,
  .clearfix:after {
      display: table;
      content: "";
  }
  .clearfix:after {
      clear: both
  }

  .box-card {
    width: 480px;
  }
</style>
```
:::

### Card semplice

L'header può essere omesso

:::demo
```html
<el-card class="box-card">
  <div v-for="o in 4" class="text item">
    {{'Elemento ' + o }}
  </div>
</el-card>

<style>
  .text {
    font-size: 14px;
  }

  .item {
    padding: 18px 0;
  }

  .box-card {
    width: 480px;
  }
</style>
```
:::

### Con immagini

Visualizza un contenuto pi ricco aggiungendo qualche configurazione.

:::demo L'attributo `body-style` può essere utilizzato per definire un CSS personalizzato per il `body`. Questo esempio utilizza anche il componente `el-col` per la gestione del layout.

```html
<el-row>
  <el-col :span="8" v-for="(o, index) in 2" :offset="index > 0 ? 2 : 0">
    <el-card :body-style="{ padding: '0px' }">
      <img src="~examples/assets/images/hamburger.png" class="image">
      <div style="padding: 14px;">
        <span>Yummy hamburger</span>
        <div class="bottom clearfix">
          <time class="time">{{ currentDate }}</time>
          <el-button type="text" class="button">Bottone</el-button>
        </div>
      </div>
    </el-card>
  </el-col>
</el-row>

<style>
  .time {
    font-size: 13px;
    color: #999;
  }

  .bottom {
    margin-top: 13px;
    line-height: 12px;
  }

  .button {
    padding: 0;
    float: right;
  }

  .image {
    width: 100%;
    display: block;
  }

  .clearfix:before,
  .clearfix:after {
      display: table;
      content: "";
  }

  .clearfix:after {
      clear: both
  }
</style>

<script>
export default {
  data() {
    return {
      currentDate: new Date()
    };
  }
}
</script>
```
:::

### Attributes
| Attributo      | Descrizione          | Tipo      | Valori accettati      | Default  |
|---------- |-------- |---------- |-------------  |-------- |
| header | Titolo della card. Accetta anche elementi DOM passando per lo `slot#header`. | stringa| — | — |
| body-style | Stile CSS del body | oggetto| — | { padding: '20px' } |

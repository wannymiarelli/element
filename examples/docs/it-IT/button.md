<script>
  import { addClass } from 'wind-dom/src/class';
  export default {
    data() {
      return {
        isLoading: false,
        isLoading2: false
      };
    },
    methods: {
      handleClick(event) {
        console.log(event);
        alert('bottone cliccato!');
      }
    },
    mounted() {
      this.$nextTick(() => {
        let demos = document.querySelectorAll('.source');
        let thirdDemo = demos[2];
        addClass(thirdDemo, 'intro-block');
      });
    }
  }
</script>

## Button

Bottone

### Utilizzo di base

::: demo Il componente Button mette a disposizione 7 temi definiti dall'attributo `type`.

```html
<el-button>Bottone di Default</el-button>
<el-button type="primary">Bottone Primario</el-button>
<el-button type="text">Bottone Testuale</el-button>
```
:::

### Disabled Button

L'attributo `disabled` determina se il bottone è disabilitato.

:::demo Usa l'attributo `disabled` per scegliere quando il bottone dev'essere disabilitato. Accetta un valore `Booleano`

```html
<el-button :plain="true" :disabled="true">Bottone di Default</el-button>
<el-button type="primary" disabled>Bottone Primario</el-button>
<el-button type="text" disabled>Bottone testuale</el-button>
```
:::

### Significato colori

Ogni colore esprime un concetto differente.

:::demo Usa l'attributo `plain` per creare un bottone piatto, accetta un valore `Booleano`. Puoi assegnare differenti `type` ad un bottone piatto come specificato qui sopra. **Attenzione**: Quando usi un bottone piatto, puoi assegnare un valore a `type`, questo però non farà alcuna differenza. Un bottone piatto viene sempre visualizzato come un `Bottone testuale`.

```html
<div class="block">
  <span class="demonstration">Default</span>
  <span class="wrapper">
    <el-button type="success">Conferma</el-button>
    <el-button type="warning">Attenzione</el-button>
    <el-button type="danger">Pericolo</el-button>
    <el-button type="info">Info</el-button>
  </span>
</div>
<div class="block">
  <span class="demonstration">Sposta il cursore per visualizzare il colore</span>
  <span class="wrapper">
    <el-button :plain="true" type="success">Conferma</el-button>
    <el-button :plain="true" type="warning">Attenzione</el-button>
    <el-button :plain="true" type="danger">Pericolo</el-button>
    <el-button :plain="true" type="info">Info</el-button>
  </span>
</div>
```
:::

### Icona Bottone

Utilizza le icone dare più significato al Bottone. Puoi utilizzare solamente le icone per ridurre lo spazio o accompagnarle con del testo.

:::demo Usa l'attributo `icon` per aggiungere un'icona. Puoi trovare le icone disponibili nel componente Icon di Element. Per allineare un icona alla destra del testo utilizza il tag `<i>`. Puoi utilizzare anche icone personalizzate.

```html
<el-button type="primary" icon="edit"></el-button>
<el-button type="primary" icon="share"></el-button>
<el-button type="primary" icon="delete"></el-button>
<el-button type="primary" icon="search">Cerca</el-button>
<el-button type="primary">Carica <i class="el-icon-upload el-icon-right"></i></el-button>
```
:::

### Gruppo di Bottoni

Visualizza un gruppo di bottone, può essere utilizzato per raggruppare una serie di operazioni simili.

:::demo Usa il tag `<el-button-group>` per raggruppare i bottoni.

```html
<el-button-group>
  <el-button type="primary" icon="arrow-left">Pagina Precedente</el-button>
  <el-button type="primary">Pagina Successiva<i class="el-icon-arrow-right el-icon-right"></i></el-button>
</el-button-group>
<el-button-group>
  <el-button type="primary" icon="edit"></el-button>
  <el-button type="primary" icon="share"></el-button>
  <el-button type="primary" icon="delete"></el-button>
</el-button-group>
```
:::

### Bottone di caricamento

Clicca il bottone per caricare i dati, nel mentre il bottone mostra un messaggio di caricamento.

:::demo Imposta l'attributo `loading` su `true` per visualizzare il messaggio di caricamento

```html
<el-button type="primary" :loading="true">Caricamento</el-button>
```
:::

### Dimensioni

Oltre alla dimensione di base, il componente Button prevede altre tre dimensioni aggiuntive da utilizzare in base alle proprie esigenze.


::: Usa l'attributo `size` per impostare la dimensione con `large`, `small` or `mini`.

```html
<el-button type="primary" size="large">Bottone Large</el-button>
<el-button type="primary">Bottone di Default</el-button>
<el-button type="primary" size="small">Bottone Small</el-button>
<el-button type="primary" size="mini">Bottone Mini</el-button>
```
:::

### Attributi
| Attributi      | Descrizione    | Tipo      | Valori accettati       | Default   |
|---------- |-------- |---------- |-------------  |-------- |
| size     | dimensione bottone   | stringa  |   large/small/mini            |    —     |
| type     | tipo bottone   | stringa    |   primary/success/warning/danger/info/text |     —    |
| plain     | determina se è un bottone piatto   | Booleano    | true,false | false   |
| disabled  | disabilita il bottone    | booleano   | true, false   | false   |
| icon  | icona del bottone, accetta le icone presenti nel componente Icon di Element | stringa   |  —  |  —  |
| autofocus  | equivalente all'`autofocus` dei bottoni nativi  | booleano   |  —  |  false  |
| native-type | equivalente al `type` nei bottoni nativi | stringa | button/submit/reset | button |

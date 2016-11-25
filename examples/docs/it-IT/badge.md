## Badge

Un numero o un segno colorato su bottoni e icone.

### Utilizzo di base

Mostra il numero di nuovi messaggi.

:::demo L'ammontare è definito dall'attributo `value` che accetta un `Numero` o una `Stringa`.

```html
<el-badge :value="12" class="item">
  <el-button size="small">commenti</el-button>
</el-badge>
<el-badge :value="3" class="item">
  <el-button size="small">risposte</el-button>
</el-badge>

<el-dropdown trigger="click">
  <span class="el-dropdown-link">
    Cliccami<i class="el-icon-caret-bottom el-icon--right"></i>
  </span>
  <el-dropdown-menu slot="dropdown">
    <el-dropdown-item class="clearfix">
      commenti
      <el-badge class="mark" :value="12" />
    </el-dropdown-item>
    <el-dropdown-item class="clearfix">
      risposte
      <el-badge class="mark" :value="3" />
    </el-dropdown-item>
  </el-dropdown-menu>
</el-dropdown>

<style>
.item {
  margin-top: 10px;
  margin-right: 40px;
}
</style>
```
:::

### Valore massimo

Puoi impostare il valore massimo.

::: demo Il valore massimo è definito dalla proprietà `max` che è un `Numero`. Nota bene che funziona solo quando anche `value` è un `Numero`.

```html
<el-badge :value="200" :max="99" class="item">
  <el-button size="small">commenti</el-button>
</el-badge>
<el-badge :value="100" :max="10" class="item">
  <el-button size="small">risposte</el-button>
</el-badge>

<style>
.item {
  margin-top: 10px;
  margin-right: 40px;
}
</style>
```
:::

### Personalizzazione

Mostra contenuto testuale piuttosto che numerico.

:::demo Quando `value` è una `Stringa`, il badge può contenere testo personalizzato.

```html
<el-badge value="new" class="item">
  <el-button size="small">commenti</el-button>
</el-badge>
<el-badge value="hot" class="item">
  <el-button size="small">risposte</el-button>
</el-badge>

<style>
.item {
  margin-top: 10px;
  margin-right: 40px;
}
</style>
```
:::

### Pallino rosso

Usa il pallino rosso per evidenziare contenti che richiedono visibilità

:::demo Usa l'attributo `is-dot`. Accetta un valore `Booleano`.

```html
<el-badge is-dot class="item">domanda</el-badge>
<el-badge is-dot class="item">
  <el-button class="share-button" icon="share" type="primary"></el-button>
</el-badge>

<style>
.item {
  margin-top: 10px;
  margin-right: 40px;
}
</style>
```
:::

<style scoped>
  .share-button {
    width: 36px;
    padding: 10px;
  }

  .mark {
    margin-top: 8px;
    line-height: 1;
    float: right;
  }

  .clearfix {
    @utils-clearfix;
  }

  .item {
    margin-right: 40px;
  }
</style>

### Attributi
| Attributo          | Descrizione            | Tipo            | Valori accettati                 | Default   |
|-------------  |---------------- |---------------- |---------------------- |-------- |
| value          | valore visualizzato      | stringa, numero          |          —             |    —     |
| max          |  valore massimo, mostra '{max}+' quando il valore eccede il valore massimo. Funziona solo se `value` è un `Numero`   | number  |         —              |     —    |
| is-dot       | definisce se visualizzare semplicemente un pallino rosso   | boolean  |  —  |  false |

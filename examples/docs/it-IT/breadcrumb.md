## Breadcrumb

Mostra la posizione della pagina corrente, rendendo più facile la navigazione inversa.

### Utilizzo di base

:::demo All'interno di `el-breadcrumb`, ogni `el-breadcrumb-item` è un tag che rappresenta ciascun livello a partire dall'homepage. Questo componente ha un attributo `separator` di tipo `Stringa` che permette di definire il separatore. Il valore di default è '/'.

```html
<el-breadcrumb separator="/">
  <el-breadcrumb-item :to="{ path: '/' }">homepage</el-breadcrumb-item>
  <el-breadcrumb-item>gestione promozioni</el-breadcrumb-item>
  <el-breadcrumb-item>gestione liste</el-breadcrumb-item>
  <el-breadcrumb-item>dettagli promozioni</el-breadcrumb-item>
</el-breadcrumb>
```
:::

### Attributi Breadcrumb
| Attributo      | Descrizione          | Tipo      | Valori accettati            | Default|
|---------- |-------------- |---------- |--------------------------------  |-------- |
| separator | carattere di separazione | stringa | — | / |

### Attributi Breadcrumb Item
| Attributo      | Descrizione          | Tipo      | Valori accettati            | Default|
|---------- |-------------- |---------- |--------------------------------  |-------- |
| to | rotta di destinazione del link, espressa come in `to` di `vue-router` | stringa/oggetto | — | — |
| replace | se `true`, la navigazione non lascerà alcun record nella cronologia. | boolean | — | false |

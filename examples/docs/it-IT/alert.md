<script>
  export default {
    methods: {
      hello() {
        alert('Hello World!');
      }
    }
  }
</script>

## Alert

Mostra un messaggio importante.

### Utilizzo base

I componenti Alert sono elementi senza overlay che non spariscono automaticamente.

::: demo Gli Alert hanno 4 tipi di temi definiti dalla propietà `type` per la quale il valore di default è `info`.

```html
<template>
  <el-alert
    title="success alert"
    type="success">
  </el-alert>
  <el-alert
    title="info alert"
    type="info">
  </el-alert>
  <el-alert
    title="warning alert"
    type="warning">
  </el-alert>
  <el-alert
    title="error alert"
    type="error">
  </el-alert>
</template>
```
:::

### Personalizzazione del bottone di chiusura

Puoi personalizzare il bottone di chiusura con testo o altri simboli.

::: demo Il componente Alert ti permette di scegliere se è possibile chiuderlo oppure no. Il testo del bottone di chiusura e la callback sono altrettanto personalizzabili. L'attributo `closable` definisce se il componente può essere chiuso oppure no. Accetta un valore `boolean`, il valore di default è `true`. Puoi utilizzare l'attributo `close-text` per modificare il simbolo predefinito del bottone di chiusura. Nota bene che `close-text` dev'essere una stringa. L'evento `close` viene generato quando il componente si è chiuso.

```html
<template>
  <el-alert
    title="unclosable alert"
    type="success"
    :closable="false">
  </el-alert>
  <el-alert
    title="customized close-text"
    type="info"
    close-text="Gotcha">
  </el-alert>
  <el-alert
    title="alert with callback"
    type="warning"
    @close="hello">
  </el-alert>
</template>

<script>
  export default {
    methods: {
      hello() {
        alert('Hello World!');
      }
    }
  }
</script>
```
:::

### Con Icona

Visualizzare un'icona migliora la leggibilità.

::: demo Impostare l'attributo `show-icon` mostra un'icona che corrisponde al tipo di alert corrente.

```html
<template>
  <el-alert
    title="success alert"
    type="success"
    show-icon>
  </el-alert>
  <el-alert
    title="info alert"
    type="info"
    show-icon>
  </el-alert>
  <el-alert
    title="warning alert"
    type="warning"
    show-icon>
  </el-alert>
  <el-alert
    title="error alert"
    type="error"
    show-icon>
  </el-alert>
</template>
```
:::

### Con Descrizione

La descrizione include un messaggio con informazioni più dettagliate.

::: demo Oltre all'attributo obbligatorio `title`, puoi aggiungere l'attributo `description` per aiutarti a descrivere l'alert in modo più dettagliato. La descrizione può contentere solo una stringa, il ritorno a capo è automatico.

```html
<template>
  <el-alert
    title="with description"
    type="success"
    description="This is a description.">
  </el-alert>
</template>
```
:::

### Con icona e descrizione

::: demo Infine, questo è un esempio con icona e descrizione.

```html
<template>
  <el-alert
    title="success alert"
    type="success"
    description="more text description"
    show-icon>
  </el-alert>
  <el-alert
    title="info alert"
    type="info"
    description="more text description"
    show-icon>
  </el-alert>
  <el-alert
    title="warning alert"
    type="warning"
    description="more text description"
    show-icon>
  </el-alert>
  <el-alert
    title="error alert"
    type="error"
    description="more text description"
    show-icon>
  </el-alert>
</template>
```
:::

### Attributes
| Atributo      | Descrizione          | Tipo      | Valori accettati       | Default  |
|---------- |-------------- |---------- |--------------------------------  |-------- |
| **title** | titolo **REQUIRED** | string | — | — |
| type | tipo del componente | string | success/warning/info/error | info |
| description | testo di supporto | string | — | — |
| closable | definisce se può essere chiuso o no | boolean | — | true |
| close-text | testo personalizzato del bottone di chiusura | string | — | — |
| show-icon | definisce se visualizzare o no l'icona del tipo di alert | boolean | — | false |


### Events
| Nome evento | Descrizione | Parametri |
|---------- |-------- |---------- |
| close | viene generato quando l'Alert è stato chiuso. | — |

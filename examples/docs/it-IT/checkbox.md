<script>
  module.exports = {
    data() {
      return {
        checkList: ['selected and disabled','Option A'],
        // checkList2: ['Option A'],
        checked: true,
        checked1: false,
        checked2: true,
        isValid: 'valid'
      };
    }
  };
</script>

## Checkbox

Un gruppo di opzioni per scelte multiple.

### Utilizzo di base

Il componente Checkbox può essere utilizzato per passare tra due stati.

:::demo Definire `v-model`(bind variable) nel componente `el-checkbox`. Il valore di default è `Boolean` per la singola checkbox, e diventa `true` quando selezionata.

```html
<template>
  <!-- `checked` should be true or false -->
  <el-checkbox v-model="checked">Opzione</el-checkbox>
</template>
<script>
  export default {
    data() {
      return {
        checked: true
      };
    }
  };
</script>
```
:::

## Disabled

Disabilita una checkbox.

::: demo Imposta l'attributo `disabled`.

```html
<template>
  <el-checkbox v-model="checked1" disabled>Opzione</el-checkbox>
  <el-checkbox v-model="checked2" disabled>Opzione</el-checkbox>
</template>
<script>
  export default {
    data() {
      return {
        checked1: false,
        checked2: true
      };
    }
  };
</script>
```
:::

### Gruppo di Checkbox
Utilizzato per raggruppare checkbox multiple.

:::demo L'elemento `checkbox-group` può gestire più checkbox in un solo gruppo utilizzando `v-model` che viene collegato ad un `Array`. `label` modifica la descrizione della checkbox e rappresenta anche il valore della checkbox. `label` corrisponde al valore dell'elemento nell'Array. La checkbox è selezionata se il valore  specificato è presente nell'array e vice versa.

```html
<template>
  <el-checkbox-group v-model="checkList">
    <el-checkbox label="Opzione A"></el-checkbox>
    <el-checkbox label="Opzione B"></el-checkbox>
    <el-checkbox label="Opzione C"></el-checkbox>
    <el-checkbox label="disabilitata" disabled></el-checkbox>
    <el-checkbox label="selezionata e disabilitata" disabled></el-checkbox>
  </el-checkbox-group>
</template>

<script>
  export default {
    data () {
      return {
        checkList: ['selezionata e disabilitata','Opzione A']
      };
    }
  };
</script>
```
:::

### Attributi Checkbox
| Attributo      | Descrizione         | Tipo    | Opzioni                         | Default|
|---------- |-------- |---------- |-------------  |-------- |
| label     | valore della checkbox quando usato all'interno di `checkbox-group` | stringa    |       —        |     —    |
| true-label | valore della checkbox se selezionata   | stringa, numero    |       —        |     —    |
| false-label | valore della checkbox se non selezionata   | stringa, numero    |      —         |     —    |
| name | attributo 'name' nativo | stringa    |      —         |     —    |
| disabled  | disabilita la checkbox   | booleano   |  — | false   |
| checked  | if the checkbox is checked   | booleano   |  — | false   |
| indeterminate  | equivale a `indeterminate` nelle checkbox native | booleano   |  — | false   |

### Eventi Checkbox-group
| Nome evento | Descrizione | Parametri |
|---------- |-------- |---------- |
| change  | viene rilasciato quando il valore di binding cambia | Event object |

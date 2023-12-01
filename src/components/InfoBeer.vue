<script >

export default {
  name: "InfoBeer",
  props: {
    info: Object
  }
}




</script>

<template>
    <div >
      <hr class="spazio">
      <p>Nome bar = {{info.name}}</p>
      <p>Tipologia = {{ info.brewery_type }}</p>
      <p>address = {{ info.address_1 }}</p>
      <p>Citta = {{ info.city }}</p>
      <p>Paese = {{ info.country }}</p>
      <p>Codice Postale = {{ info.postal_code }}</p>
    </div>
</template>

<style scoped>
  .spazio{
    margin: 50px 0px 50px 0px;
  }
</style>

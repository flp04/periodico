<template>
  <section>
    <div style="margin: 20px;">
      <p>Inicio > {{ secao }}</p>
      <h3>{{ secao.toUpperCase() }}</h3>
    </div>
    <div style="display: flex; justify-content: space-around;">
      <article>
        <div></div>
        <p>Lorem Ipsulum Lorem Ipsulum Lorem Ipsulum Lorem Ipsulum</p>
      </article>
      <article>
        <div></div>
        <p>Lorem Ipsulum Lorem Ipsulum Lorem Ipsulum Lorem Ipsulum</p>
      </article>
      <article>
        <div></div>
        <p>Lorem Ipsulum Lorem Ipsulum Lorem Ipsulum Lorem Ipsulum</p>
      </article>
    </div>
  </section>
</template>
<script>
export default {
  props: ['secao'],
  data() {
    return {
      // secao: ''
    }
  },
}
</script>
<style>
  article {
    margin: 10px;
    display: inline-block;
    position: relative;
  }
  article div {
    border: 1px black solid;
    width: 400px;
    height: 250px;
  }
  article p {
    position: absolute;
    bottom: 0;
  }
</style>
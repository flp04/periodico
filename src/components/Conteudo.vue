<template>
  <section>
    <div v-if="secao" style="margin: 20px;">
      <p>Inicio > {{ secao }}</p>
      <h3>{{ secao.toUpperCase() }}</h3>
    </div>
    <div class="card-group">
      <div class="col-sm-4" style="padding: 5px;">
        <div class="card">
          <!-- <img class="card-img-top" src="..." alt="Card image cap"> -->
          <div class="text-center" style="width: 100%; height: 150px; border: solid 1px black;"></div>
          <div class="card-body">
            <h5 class="card-title">Card title</h5>
            <p class="card-text">Lorem Ipsulum Lorem Ipsulum Lorem Ipsulum.</p>
            <p class="card-text"><small class="text-muted">Data da publicação</small></p>
          </div>
        </div>
      </div>
      <div class="col-sm-4" style="padding: 5px;">
        <div class="card">
          <div class="text-center" style="width: 100%; height: 150px; border: solid 1px black;"></div>
          <div class="card-body">
            <h5 class="card-title">Card title</h5>
            <p class="card-text">Lorem Ipsulum Lorem Ipsulum Lorem Ipsulum.</p>
            <p class="card-text"><small class="text-muted">Data da publicação</small></p>
          </div>
        </div>
      </div>
      <div class="col-sm-4" style="padding: 5px;">
        <div class="card">
          <div class="text-center" style="width: 100%; height: 150px; border: solid 1px black;"></div>
          <div class="card-body">
            <h5 class="card-title">Card title</h5>
            <p class="card-text">Lorem Ipsulum Lorem Ipsulum Lorem Ipsulum.</p>
            <p class="card-text"><small class="text-muted">Data da publicação</small></p>
          </div>
        </div>
      </div>
    </div>
    <!-- <div style="display: flex; justify-content: space-around;">
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
    </div> -->
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
<style scoped>
  /* article {
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
  } */
</style>
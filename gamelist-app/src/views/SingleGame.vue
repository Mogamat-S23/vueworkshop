<template>
  <div class="single">
    <h1>This is an single game page</h1>
    <!-- <div class="products-container">
      <div v-for="property of properties" :key="property.id" class="card">
        <router-link :to="{ name: 'SingleGame', params: { id: property.id } }">
          <img :src="property.image" alt="property.address.street" />
        </router-link>
        {{ property.address.street }}
      </div>
    </div> -->
    <div class="container">
      <div class="row">
        <div
          class="card m-3 p-3"
          v-for="property of properties"
          :key="property.id"
          style="width: 18rem"
        >
          <img :src="property.image" class="card-img-top" alt="..." />
          <div class="card-body">
            <h5 class="card-title">Card title</h5>
            <p class="card-text">{{ property.address.street }}</p>
            <router-link
              :to="{ name: 'SingleGame', params: { id: property.id } }"
            >
              <a href="#" class="btn btn-primary">Go somewhere</a>
            </router-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      properties: [],
    };
  },
  mounted() {
    fetch("http://localhost:3000/properties")
      .then((res) => res.json())
      .then((data) => (this.properties = data));
  },
};
</script>

<style>
</style>


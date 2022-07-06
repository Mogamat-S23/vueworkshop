<template>
  <div class="Game">
    <h1>This is an Game page</h1>
    <p>The game id is {{ id }}</p>
    <img :src="property.image" alt="" width="200" height="200">
  </div>
</template>
<script>
export default {
  props: ['id'],
  data() {
    return {
      property: [],
    };
  },
  mounted() {
    fetch("http://localhost:3000/properties/" + this.id)
      .then((res) => res.json())
      .then((data) => (this.property = data));
  },
};
</script>
<template>
  <div class="home">
    <section class="hero is-medium is-dark mb-6">
      <div class="hero-body has-text-centered">
        <p class="title mb-6">Welcome</p>
        <p class="subtitle">the best</p>
      </div>
    </section>

    <div class="columns is-multiline">
      <div class="column is-12">
        <h2 class="is-size-2 has-text-centered">Latest product</h2>
      </div>
      <div
        class="colums is-3"
        v-for="product in latestProducts"
        v-bind:key="product.id"
      >
        <div>
          <figure class="image mb-4">
            <img :src="product.get_thumbnail" />
          </figure>
          <h3>{{ product.name }}</h3>
          <p class="is-size-6 has-text-grey">{{ product.price }}</p>

          View details
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import axios from "axios";

export default {
  name: "HomeView",
  data() {
    return {
      latestProducts: [],
    };
  },
  components: {},
  mounted() {
    this.getLatestProducts();
  },
  methods: {
    getLatestProducts() {
      axios
        .get("/api/v1/latest-products/")
        .then((response) => {
          this.latestProducts = response.data;
        })
        .then((data) => {
          console.log(data); // In ra để xem dữ liệu nhận được
          // Xử lý dữ liệu nhận được từ API
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>
<style scoped>
.image {
  margin-top: -1.25rem;
  margin-left: -1.25rem;
  margin-right: -1.25rem;
}
</style>

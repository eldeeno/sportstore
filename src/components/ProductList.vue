<template>
  <div>
    <div v-for="p in products" v-bind:key="p.id" class="card m-1 p-1 bg-light">
      <h4>
        {{p.name}}
        <span class="badge rounded-pill bg-primary float-end">
          {{ p.price | currency}}
        </span>
      </h4>
      <div class="card-text bg-white p-1">{{ p.description }}</div>
    </div>
    <page-controls/>
  </div>
</template>
<script>
import {mapGetters} from "vuex";
import PageControls from "./PageControls";

export default {
  components: {PageControls},
  computed: {
    ...mapGetters({ products: 'processedProducts' })
  },
  filters: {
    currency(value) {
      return new Intl.NumberFormat("en-NG",
          { style: "currency", currency: "NGN" }).format(value);
    }
  }
}
</script>
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
  </div>
</template>
<script>
import { mapState } from "vuex";
export default {
  computed: {
    ...mapState(["products"])
  },
  filters: {
    currency(value) {
      return new Intl.NumberFormat("en-NG",
          { style: "currency", currency: "NGN" }).format(value);
    }
  }
}
</script>
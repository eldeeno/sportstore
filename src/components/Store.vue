<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col bg-dark">
        <a class="navbar-brand text-white">SPORTS STORE</a>
      </div>
    </div>
    <div class="row">
      <div class="col-3 bg-info p-2">
        <h4 class="text-white m-2">Categories</h4>
      </div>
      <div class="col-9 bg-success p-2">
        <product-list/>
      </div>
    </div>
  </div>
</template>

import
<script>
import ProductList from "./ProductList";
export default {
  components: {ProductList}
}
</script>
<template>
  <div id="addForm">
    <form @submit.prevent="handleAdd">
      <div class="form-group">
        <label for="id">Id</label>
        <input type="text" v-model="product.id" class="form-control" id="id"/>
      </div>
      <div class="form-group">
        <label for="categoryId">Category Id</label>
        <input type="text" v-model="product.categoryId" class="form-control" id="categoryId"/>
      </div>
      <div class="form-group">
        <label for="productName">Product Name</label>
        <input type="text" v-model="product.productName" class="form-control" id="productName"/>
      </div>
      <div class="form-group">
        <label for="quantityPerUnit">Quantity Per Unit</label>
        <input type="text" v-model="product.quantityPerUnit" class="form-control" id="quantityPerUnit"/>
      </div>
      <div class="form-group">
        <label for="unitPrice">Unit Price</label>
        <input type="text" v-model="product.unitPrice" class="form-control" id="unitPrice"/>
      </div>
      <div class="form-group">
        <label for="unitsInStocks">Units In Stocks</label>
        <input type="text" v-model="product.unitsInStocks" class="form-control" id="unitsInStocks"/>
      </div>
      <button class="btn btn-sm btn-success" type="submit">Ekle</button>
    </form>
  </div>
</template>
<script>
export default {
  name: "product-add",
  data() {
    return {
      product: {
        id: '',
        categoryId: '',
        productName: '',
        quantityPerUnit: '',
        unitPrice: '',
        unitsInStocks: '',
      },
    };
  },
  methods:{
      handleAdd(){
          this.$emit("add:product", this.product)
      }
  }
};
</script>
<style scoped>
#addForm {
    margin: 100px;
}
</style>

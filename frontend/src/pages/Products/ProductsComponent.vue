<template>
  <DashboardComponent>
    <div slot="slot-pages" class="content-pages">

      <header class="title-pages">
        <p>Products</p>
      </header>
      
    </div>
  </DashboardComponent>
</template>

<script>
import DashboardComponent from "../Dashboard/DashboardComponent";

export default {
  name: "ProductsComponent",
  components: {
    DashboardComponent,
  },
};
</script>

<style lang="scss" src="./style.scss" />
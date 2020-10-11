<template>
  <DashboardComponent>
    <div slot="slot-pages" class="content-pages">

      <header class="title-pages">
        <p>Clients</p>
      </header>
      
    </div>
  </DashboardComponent>
</template>

<script>
import DashboardComponent from "../Dashboard/DashboardComponent";

export default {
  name: "Clients",
  components: {
    DashboardComponent,
  },
};
</script>

<style lang="scss" src="./style.scss" />
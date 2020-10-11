<template>
  <DashboardComponent>
    <div slot="slot-pages" class="content-pages">
      <header class="title-pages">
        <p>Home</p>
      </header>
      <div>
        <div class="row">
          <div class="col-12 col-md-3">
            <CardsComponent
              :type="'Clientes'"
              :percentage="'7%'"
              :icon="'fa-users'"
              :qtd="'9750'"
            />
          </div>
          <div class="col-12 col-md-3">
            <CardsComponent
              :type="'Produtos'"
              :percentage="'12%'"
              :icon="'fa-box'"
              :qtd="'350'"
            />
          </div>
          <div class="col-12 col-md-3">
            <CardsComponent
              :type="'Serviços'"
              :percentage="'3%'"
              :icon="'fa-store'"
              :qtd="'270'"
            />
          </div>
          <div class="col-12 col-md-3">
            <CardsComponent
              :type="'Relatórios'"
              :percentage="'25%'"
              :icon="'fa-chart-bar'"
              :qtd="'30'"
            />
          </div>
        </div>
      </div>
      <div class="mt-5">
        <div class="row">
          <div class="col-12 col-md-6">
            <ListsComponent
              :data="clients"
              description="Clientes"
              :columns="['Nome', 'Email']"
            />
          </div>

          <div class="col-12 col-md-6">
            <ListsComponent
              :data="products"
              description="Produtos"
              :columns="['Nome', 'Valor']"
            />
          </div>
        </div>
      </div>
    </div>
  </DashboardComponent>
</template>

<script>
import DashboardComponent from "../Dashboard/DashboardComponent";
import CardsComponent from "../../components/CardsComponent";
import ListsComponent from "../../components/ListsComponent";
const axios = require("axios");

export default {
  name: "HomeComponent",
  data() {
    return {
      clients: [],
      products: [],
    };
  },
  mounted() {
    this.getUsers();
  },
  methods: {
    async getUsers() {
      // const response = await axios.get('https://jsonplaceholder.typicode.com/users')
      // if(response.status == 200) {
      //   this.users = response.data
      // }else {
      //   console.error('Falha na requisição!')
      // }
      const response = await axios.get("/");
      if (response.status == 200) {
        this.clients = response.data.clients;
        this.products = response.data.products;
      } else {
        console.error("Falha na requisição!");
      }
    },
  },
  components: {
    DashboardComponent,
    CardsComponent,
    ListsComponent,
  },
};
</script>

<style lang="scss" src="./style.scss" />
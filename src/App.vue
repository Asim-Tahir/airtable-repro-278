<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Hello Vue 3 + TypeScript + Vite" />
  <pre>{{ appointments }}</pre>
</template>

<script lang="ts">
  import { defineComponent } from "vue";
  import HelloWorld from "./components/HelloWorld.vue";
  import { default as Airtable } from "airtable";

  console.log(import.meta.env);

  const airtable = new Airtable({
    apiKey: import.meta.env.VITE_AIRTABLE_API_KEY!.toString(),
    endpointUrl: "https://api.airtable.com",
  });

  const base = airtable.base(import.meta.env.VITE_AIRTABLE_BASE_ID!.toString());

  const appointments = await base("Appointment").select().all();

  export default defineComponent({
    name: "App",
    components: {
      HelloWorld,
    },
    setup() {
      return {
        appointments,
      };
    },
  });
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>

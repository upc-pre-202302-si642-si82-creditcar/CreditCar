<script>
import Toolbar from "@/public/components/toolbar.component.vue";
export default {
  name: "App",
  components: {Toolbar},
};
</script>

<template>
  <div class="select-none">
    <toolbar></toolbar>
    <router-view></router-view>
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css?family=Open+Sans');
@tailwind base;
@tailwind components;
@tailwind utilities;

:root {
  --primary-blue: #16537E;
  --primary-white:#E1E8EC;
  --gray-1: #D9D9D9;
  --gray-2:#8E8E8E;
  --gray-3:#4D4D4D;
  --black: #282828;
  --white: #FFFFFF;
  --red: #eb0a1e;
  --font-primary: 'Open Sans';
  --heading-1-size: 52px;
  --heading-2-size: 36px;
  --heading-3-size: 24px;
  --heading-4-size: 18px;
  --large-text-bold-size: 24px;
  --large-text-regular-size: 24px;
  --medium-text-bold-size: 18px;
  --medium-text-regular-size: 18px;
  --normal-text-bold-size: 16px;
  --normal-text-regular-size: 16px;
  --small-text-bold-size: 14px;
  --small-text-regular-size: 14px;
}

* :not(i) {
  font-family: var(--font-primary) !important;
}

body {
  background-color: #FCFBFB;
}

.card {
  background-color: var(--white);
  box-shadow: 0 1px 5px 0 rgba(0, 0, 0, 0.12), 0 2px 2px 0 rgba(0, 0, 0, 0.14), 0 1px 1px 0 rgba(0, 0, 0, 0.20);
  border-radius: 20px !important;
  margin: 2.7rem 2rem;
}
</style>

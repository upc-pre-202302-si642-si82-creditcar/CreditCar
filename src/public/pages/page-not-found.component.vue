<script>
export default {
  name: "page-not-found-component",
  data() {
    return {
      invalidUrl: this.$route.fullPath,
    };
  },
}
</script>


<template>
  <div class="center">
    <h1>Page Not Found</h1>
    <p>The path <b>{{ invalidUrl }}</b> is not valid.</p>
    <router-link to="/">
      <pv-button class="p-button-text">
        Return
      </pv-button>
    </router-link>
  </div>
</template>


<style scoped>
.center {
  text-align: center;
  margin: 20%;
}
.center h1 {
  font-size: 2rem;
  color: var(--black);
}
p {
  color: var(--black);
}
</style>
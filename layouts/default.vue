<template>
  <div>
    <AppHeader />
    <Nuxt  class="mt-4"/>
  </div>
</template>
<script>
import AppHeader from "../components/AppHeader.vue";
export default {
  name: "default",
  components: { AppHeader },
};
</script>

<template>
  <div>
    <h2>This is the main index page</h2>
  </div>
</template>

<script>
export default {
  name: "IndexPage",
  head() {
    return {
      title: "Main index page",
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: "description",
          name: "description",
          content: "My ABout description of dad jokes",
        },
      ],
    };
  },
};
</script>

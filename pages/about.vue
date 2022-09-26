<template>
  <div>
    <h1>This the about page of dadjokes</h1>
    <p>
      It is a long established fact that a reader will be distracted by the
      readable content of a page when looking at its layout. The point of using
      Lorem Ipsum is that it has a more-or-less normal distribution of letters
    </p>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: "About page",
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

<style></style>

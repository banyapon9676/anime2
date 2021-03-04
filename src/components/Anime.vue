<template>
  <div class="card">
    <b-card

      :img-src="image"
      img-alt="Card image"
      img-top
      tag="article"
      class="overflow-hidden"
      align="center"
      bg-variant="dark"
      style="height: 38rem"
    >
   
      <b-card-text style="color: white">
        <h4>{{ title }}</h4>
      </b-card-text>
    </b-card>
  </div>
</template>
<script>
export default {
  props: {
    title: String,
    image: String,
  },
};
</script>

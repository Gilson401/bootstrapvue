<template>
  <div class="content">
    <div class="right align-self-center">
      <p class="text-white">/News</p>
      <p class="text-gray-300 font-size-030">/Cases Games</p>

      <slot/>
    </div>
  </div>
</template>

<script>
export default {
  name: "CaseGames",
  props: {
    route: String,
    index: Number,
    text1: String,
  },
};
</script>

<style scoped>
.content {
  grid-area: content;
  display: grid;
  grid-template-areas: "right right";
  grid-template-columns: 50% 50%;
  grid-gap: 10px;
  height: 100vh;
  padding: 30px;
}

p {
  text-align: left;
} 
.left {
  grid-area: left;
  padding: 12%;
}

.right {
  grid-area: right;
}

.card {
  width: auto;
  height: auto;
  
  background-color: rgb(41,41,41);
}

.card-img {
  aspect-ratio: 1.5;
  width: 100%;
}

.card-button {
  background-color: rgb(147,149,152);
color:black;
text-transform: uppercase;
display: inline-block;
width: fit-content;
padding: 1px 2px 1px 2px;
}

.card-text{
    margin: 10px 20px 0 20px;
    padding-bottom: 20px;
}

</style>

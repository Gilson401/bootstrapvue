<template>
  <a class="text-decoration-none text-left ml-auto text-uppercase" :href="text.route">
    <span class="text-gray-300"> {{ text.label }} </span>
    <span class="text-white"> &#129134; </span>
  </a>
</template>

<script>
export default {
  name: "ArrowLink",
  props:{
      text:Object,
  }
};
</script>

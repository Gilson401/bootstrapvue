<template>
  <div class="pb-3">
    <slot name="top" />

    <p :v-if="topText" class="font-size-075 text-gray-300">
      {{ topText }}
    </p>

    <p :v-if="mediumText" class="text-white font-size-012">
      {{ mediumText }}
    </p>
    <slot name="medium" />

    <arrow-link v-if="bottomLink" :text="bottomLink" />
    <slot name="bottom" />
  </div>
</template>

<script>
import ArrowLink from "./ArrowLink.vue";
export default {
  components: { ArrowLink },
  name: "ContactCard",
  props: {
    topText: String,
    mediumText: String,
    bottomLink: Object,
  },
};
</script>

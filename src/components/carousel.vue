<template>
  <div class="relative w-full flex items-center invisible md:visible md:pb-12">
    <button
        class="absolute bg-blue-800 hover:bg-blue-700 text-white text-2xl font-bold hover:shadow rounded-full w-16 h-16 ml-12"
        @click="decrement"
    >
      &#8592;
    </button>
    <template v-for="image in visibleImages" :key="image">
      <img class="w-1/6 hover:opacity-75" :src="image">
    </template>
    <button
        class="absolute right-0 bg-blue-800 hover:bg-blue-700 text-white text-2xl font-bold hover:shadow rounded-full w-16 h-16 mr-12"
        @click="increment"
    >
      &#8594;
    </button>
  </div>
</template>

<script>
export default {
  props: {
    currentIndex: Number,
    images: Array,
  },
  data() {
    return {
      itemsPerPage: 6,
    };
  },
  computed: {
    visibleImages() {
      return this.images.slice(this.currentIndex, this.currentIndex + this.itemsPerPage);
    },
  },
  methods: {
    increment() {
      this.$emit('increment');
    },
    decrement() {
      this.$emit('decrement');
    },
  },
};
</script>

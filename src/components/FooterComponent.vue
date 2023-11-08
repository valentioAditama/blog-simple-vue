<template>
  <main>
    <footer class="w-full border-t bg-white pb-12">
      <carousel :currentIndex="currentIndex" :images="images" @increment="increment" @decrement="decrement"></carousel>
      <div class="w-full container mx-auto flex flex-col items-center">
        <div class="flex flex-col md:flex-row text-center md:text-left md:justify-between py-6">
          <a href="#" class="uppercase px-3">About Us</a>
          <a href="#" class="uppercase px-3">Privacy Policy</a>
          <a href="#" class="uppercase px-3">Terms & Conditions</a>
          <a href="#" class="uppercase px-3">Contact Us</a>
        </div>
        <div class="uppercase pb-6">&copy; myblog.com</div>
      </div>
    </footer>
  </main>
</template>

<script>
import Carousel from "./carousel.vue";

export default {
  data() {
    return {
      currentIndex: 0,
      images: [
        'https://source.unsplash.com/collection/1346951/800x800?sig=1',
        'https://source.unsplash.com/collection/1346951/800x800?sig=2',
        'https://source.unsplash.com/collection/1346951/800x800?sig=3',
        'https://source.unsplash.com/collection/1346951/800x800?sig=4',
        'https://source.unsplash.com/collection/1346951/800x800?sig=5',
        'https://source.unsplash.com/collection/1346951/800x800?sig=6',
        'https://source.unsplash.com/collection/1346951/800x800?sig=7',
        'https://source.unsplash.com/collection/1346951/800x800?sig=8',
        'https://source.unsplash.com/collection/1346951/800x800?sig=9',
      ],
    };
  },
  components: {
    Carousel,
  },
  methods: {
    increment() {
      this.currentIndex = this.currentIndex === this.images.length - 6 ? 0 : this.currentIndex + 1;
    },
    decrement() {
      this.currentIndex = this.currentIndex === this.images.length - 6 ? 0 : this.currentIndex - 1;
    },
  },
};
</script>

<template>
  <div>
    this is index page
  </div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      scrollObserver: null,
    };
  },
  async created() {
    // bind target to observer
    // const target = document.querySelector('.loading-area__footer');
    //
    // this.scrollObserver = this.createObserverWithHandleEvent(this.loadItems);
    // this.observeTarget(this.scrollObserver, target);
  },
  beforeDestroy() {
    this.scrollObserver.disconnect();
  },
  methods: {
    createObserverWithHandleEvent(handleEvent) {
      return new IntersectionObserver(
        entries => {
          if (entries[0].intersectionRatio !== 1) return;

          handleEvent();
        },
        {
          threshold: [1],
        }
      );
    },
    observeTarget(observer, target) {
      observer.observe(target);
    },
  },
}
</script>

<style lang="scss" scoped>
</style>

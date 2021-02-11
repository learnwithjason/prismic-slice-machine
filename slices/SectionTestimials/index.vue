<template>
  <section class="section-testimonials">
    <div v-for="(item, i) in slice.items" :key="`slice-item-${i}`">
      <div class="image-wrap">
        <prismic-image :field="item.image" />
      </div>
      <h2>{{ item.heading }}</h2>
      <prismic-rich-text :field="item.testimonial" />
    </div>
  </section>
</template>

<script>
export default {
  props: {
    slice: {
      type: Object,
      required: true,
      default() {
        return {}
      },
    },
  },
}
</script>

<style scoped>
.section-testimonials {
  display: grid;
  grid-template-columns: repeat(3, 30%);
  gap: 2rem;
  position: relative;
  background: #fff;
  color: #111;
  padding: 4em;
  text-align: center;
}

.image-wrap {
  margin: 0 auto 1rem;
  width: 100px;
  height: 100px;
  border-radius: 50%;
  overflow: hidden;
}

.image-wrap img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
a {
  color: #111;
}
.title {
  margin-bottom: 2em;
}
</style>

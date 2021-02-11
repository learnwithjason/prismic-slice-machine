<template>
  <section class="section-hero">
    <div class="text">
      <h1><prismic-rich-text :field="slice.primary.title" class="title" /></h1>
      <div>
        <prismic-rich-text :field="slice.primary.description" />
      </div>
      <prismic-link :field="slice.primary.buttonLink" class="button">{{ slice.primary.button }}</prismic-link>
    </div>
    <div class="image">
      <prismic-image :field="slice.primary.image" />
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
.section-hero {
  display: flex;
  gap: 2rem;
  position: relative;
  background: #f7f7f7;
  color: #111;
  padding: 4em;
  text-align: center;
}

.text {
  text-align: left;
  width: 60%;
}

.button {
  background: #111;
  color: #f7f7f7;
  font-weight: bold;
  padding: 0.5rem 1rem;
  border: none;
  border-radius: 0.25rem;
  display: inline-block;
  text-decoration: none;
  margin-top: 1rem;
}

.image {
  width: calc(40% - 2rem);
}

.image img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}
</style>

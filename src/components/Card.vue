<template>
  <section class="card" :class="this.clickable ? 'clickable' : ''" @click="emitClick">
    <div v-if="img" class="card-header" :style="computedHeaderStyle">
      <div class="card-header-overlay"></div>
      <div class="card-header-hover"></div>
      <span v-if="badge" class="card-header-badge">{{ badge }}</span>
    </div>
    <div class="card-body">
      <h4 v-if="title" class="card-title">{{ computedTitle }}</h4>
      <slot></slot>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: null,
    },
    badge: {
      type: String,
      default: null,
    },
    img: {
      type: String,
      default: null,
    },
    height: {
      type: String,
      default: "200px",
    },
    clickable: {
      type: Boolean,
      default: false,
    },
  },
  computed: {
    computedHeaderStyle() {
      return "background-image: url('" + require(`@/assets/${this.img}`) + "'); height: " + this.height + ";";
    },
    computedTitle() {
      const lastSpace = this.title.substring(0, 61).lastIndexOf(" ");
      return this.title.length > 64 ? this.title.substring(0, lastSpace) + "…" : this.title;
    },
  },
  methods: {
    emitClick() {
      if (this.clickable) this.$emit('click');
    },
  },
};
</script>

<style>
.card {
  overflow: hidden;
  border-radius: 1rem;
  box-shadow: 0px 13px 35px rgba(0, 30, 47, 0.1);
  text-align: left;
  background-color: #fff;
  line-height: 1.3;
  font-size: 12px;
  color: #393C40;
}

.card.clickable {
  cursor: pointer;
}

.card-header {
  height: 200px;
  background-image: url(../assets/pizza.jpg);
  background-size: cover;
  position: relative;
}

.card-header-overlay {
  height: 100%;
  background: linear-gradient(180deg, rgba(0, 0, 0, 0.0001) 0%, rgba(22, 27, 35, 0.2) 70.94%, rgba(26, 29, 34, 0.79) 106.25%);
}

.card-header-hover {
  position: absolute;
  width: 100%;
  height: 100%;
  left: 0;
  top: 0;
  background-color: #fff;
  opacity: 0;
  transition: opacity 0.3s;
}

.card.clickable:hover .card-header-hover {
  opacity: 0.3;
  background-color: #fff;
}

.card-header-badge {
  background-color: rgb(255, 255, 255, 0.5);
  color: #fff;
  font-weight: bold;
  padding: .2rem .75rem;
  border-radius: .75rem;
  position: absolute;
  bottom: .5rem;
  left: .5rem;
}

.card-title {
  font-size: 14px;
  font-weight: 700;
  margin: 0 0 .6rem 0;
  line-height: 1.25;
  color: #0C0C0A;
}

.card-body {
  padding: 1rem 1.25rem .35rem 1.25rem;
}

.card-body p {
  margin: 0 0 1rem 0;
  padding: 0;
}
</style>

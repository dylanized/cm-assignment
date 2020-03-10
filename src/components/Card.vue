<template>
  <section class="card">
    <div v-if="img" class="card-header" :style="computedHeaderStyle">
      <div class="card-header-overlay"></div>
      <span v-if="badge" class="card-header-badge">{{ badge }}</span>
    </div>
    <div class="card-body">
      <h4 class="card-title">{{ title }}</h4>
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
    }
  },
  computed: {
    computedHeaderStyle() {
      return "background-image: url('" + require(`@/assets/${this.img}`) + "'); height: " + this.height + ";";
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

.card.has-action {
  cursor: pointer;
}

.card .card-header-overlay {
  transition: opacity .3s;
}

.card.has-action:hover .card-header-overlay {
  opacity: 0;
}

.card-header {
  height: 200px;
  background-image: url(../assets/pizza.jpg);
  background-size: cover;
  position: relative;
}

.card-header-overlay {
  background: linear-gradient(180deg, rgba(0, 0, 0, 0.0001) 0%, rgba(22, 27, 35, 0.2) 70.94%, rgba(26, 29, 34, 0.79) 106.25%);
  height: 100%;
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

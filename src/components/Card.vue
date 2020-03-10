<template>
  <section class="card">
    <div class="card-header">
      <img class="card-header-img" src="" alt="" />
      <slot name="card-header"></slot>
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
  },
};
</script>

<style>
.card {
  width: 340px;
  overflow: hidden;
  border-radius: 1rem;
  box-shadow: 1px 1px #888888;
}

.card-header {
  height: 200px;
  background: linear-gradient(180deg, rgba(0, 0, 0, 0.0001) 0%, rgba(22, 27, 35, 0.2) 70.94%, rgba(26, 29, 34, 0.79) 106.25%);
}

.card-header-img {
  width: 100%;
  display: block;
}

.card-header-badge {

}

.card-header-heart {

}

.card-body {
  font-size: 1rem;
  padding: .5rem 1rem;
  line-height: 1.3;
}

.card-body .card-title {
  font-weight: bold;
}
</style>

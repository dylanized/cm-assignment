<template>
  <div id="app">
    <div class="cm-container">
      <div class="cm-logo-wrapper">
        <img alt="Carb Manager" src="./assets/cm-logo.svg" class="cm-logo" />
      </div>
      <h2>Carb Manager Dev Assignment</h2>
      <p>See the README file for assignment requirements.</p>

      <div class="premium-recipe-wrapper">
        <Card class="card-demo" title="Here is a clickable card" img="dinner.jpg" badge="Card Badge" @click="displayClicked" clickable="true">
          <p>Card body lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi semper ante tortor, nec congue turpis vulputate eu.</p>
        </Card>

        <Card class="card-demo" title="Here is a basic card" img="pizza.jpg" badge="Card Badge">
          <p>Card body lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi semper ante tortor, nec congue turpis vulputate eu.</p>
        </Card>

        <Card class="card-demo" title="Here is a basic card with a longer title that stretches to two lines" height="150px" img="pancakes.jpg">
          <p>Card body lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi semper ante tortor, nec congue turpis vulputate eu.</p>
        </Card>

        <Card class="card-demo" title="Here is a basic card with no header">
          <p>Card body lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi semper ante tortor, nec congue turpis vulputate eu.</p>
        </Card>

        <Card class="card-demo" height="230px" img="burgers.jpg">
          <p>Basic card with no title and taller image. Card body lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi semper ante tortor, nec congue turpis vulputate eu.</p>
        </Card>
      </div>
    </div>
  </div>
</template>

<script>
import Card from "./components/Card.vue";

export default {
  name: "App",
  components: {
    Card,
  },
  methods: {
    displayClicked() {
      alert('clicked');
    },
  },
};
</script>

<style>
#app {
  font-family: "proxima-nova", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

<style scoped>
.cm-logo-wrapper {
  margin-bottom: 30px;
}

.cm-logo {
  max-width: 150px;
  height: auto;
}

.cm-container {
  max-width: 960px;
  margin: auto;
}

/** Remove these styles when done */
.premium-recipe-wrapper {
  margin: 100px 0;
  border: 2px dashed red;
  padding: 16px;
  background-color: #e5e5e5;
}

.card-demo {
  width: 250px;
  margin: 50px auto;
}
</style>

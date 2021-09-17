<template>
  <div class="card">
    <div class="title-container">
        <Button title="Edit" type="card" />
        <Button title="Delete" type="card" />
    </div>
    <h3 class="title">
        {{ title }}
      </h3>
    <p class="description">
      {{ description }}
    </p>
  </div>
</template>

<script>
import Button from "./Button";
export default {
  name: "Card",
  components: {
    Button,
  },
  props: {
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      default: "No description.",
    },
  },
};
</script>

<style scoped>
.card {
  min-height: 300px;
  margin: 50px;
  border-radius: 10px;
  background-color: #1e3d59;
  max-width: 300px;
}

.title {
  padding: 15px;
  padding-top: 25px;
  color: #ff6e40;
}

.description {
  padding: 15px;
  word-wrap: break-word;
  color: #f5f0e1;
}

.hr {
  width: 50%;
}

.title-container { 
    display: flex;
    flex-direction: row-reverse;
}
</style>
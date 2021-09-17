<template>
  <div>
    <button :class="c_buttonClass">{{ title }}</button>
  </div>
</template>

<script>
export default {
  name: "Button",
  props: {
    title: {
      type: String,
      required: true,
    },
    type: {
        type: String,
        default: "header",
        validate: value => ["header", "card"].includes(value) 
    }
  },
  computed: {
      c_buttonClass() {
          return this.type === "header" ? "button-header" : "button-card"
      }
  }
};
</script>

<style scoped>
.button-header {
  background-color: #ffc13b;
  border: none;
  border-radius: 10px;
  color: #1e3d59;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;

}

.button-card {
  background-color: #ffc13b;
  border: none;
  border-radius: 10px;
  color: #1e3d59;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
}
</style>
<template>
  <div class="hello">
    <div class="app-title">
      <h1>{{ msg }}</h1>
      <h2>Members:</h2>
      <p>Florian Schächter, Peter Currie, and Wayne Cabanto</p>
    </div>
    <div class="button-headers">
      <Button title="Add a note" type="header" />
    </div>
    <div class="notes-container">
      <div v-for="(note, index) in notes" :key="index">
        <Card :title="note.title" :description="note.description" />
      </div>
    </div>
  </div>
</template>

<script>
import Card from "../components/Card";
import Button from "../components/Button";
import axios from "axios";

export default {
  name: "Home",
  components: {
    Card,
    Button,
  },
  props: {
    msg: String,
  },
  data() {
    return {
      notes: [],
    };
  },
  created() {
    this.getNotes();
  },
  methods: {
    getNotes() {
      axios
        .get(
          `https://express-sample-app-squad-4-app.ibmcloud-roks-wgiztgdm-6ccd7f378ae819553d37d5f2ee142bd6-0000.us-east.containers.appdomain.cloud/notes`
        )
        .then((response) => {
          console.log("result", response);
          this.notes = response.data;
        })
        .catch((e) => {
          this.errors.push(e);
        });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.app-title {
  text-align: center;
}

.notes-container {
  margin: auto;
  width: 85%;
  background-color: #f5f0e1;
  min-height: 400px;
  border-radius: 10px;

  /**Flexbox settings */
  display: flex;
  flex-wrap: wrap;
}

.button-headers {
  margin: auto;
  display: flex;
  flex-direction: row-reverse;
  width: 85%;
}
</style>

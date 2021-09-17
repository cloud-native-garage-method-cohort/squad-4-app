<template>
  <div class="hello">
    <div class="app-title">
      <h1>{{ msg }}</h1>
      <h2>Members:</h2>
      <p>Florian Schächter, Peter Currie, and Wayne Cabanto</p>
    </div>
    <div class="button-headers">
      <Button title="Add a note" type="header"/>
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
export default {
  name: "Home",
  components: {
    Card,
    Button
  },
  props: {
    msg: String,
  },
  data() {
    return {
      notes: [
        {
          title: "Football",
          description:
            "Football, also called association football or soccer, is a game involving two teams of 11 players who try to maneuver the ball into the other team's goal without using their hands or arms. The team that scores more goals wins. Football is the world's most popular ball game in numbers of participants and spectators.",
        },
        {
          title: "Mammal",
          description: "A warm-blooded vertebrate animal of a class that is distinguished by the possession of hair or fur, females that secrete milk for the nourishment of the young, and (typically) the birth of live young.",
        },
        {
          title: "Multiverse",
          description: "The multiverse is a hypothetical group of multiple universes. Together, these universes comprise everything that exists: the entirety of space, time, matter, energy, information, and the physical laws and constants that describe them.",
        },
        {
          title: "Football",
          description:
            "Football, also called association football or soccer, is a game involving two teams of 11 players who try to maneuver the ball into the other team's goal without using their hands or arms. The team that scores more goals wins. Football is the world's most popular ball game in numbers of participants and spectators.",
        },
        {
          title: "Mammal",
          description: "A warm-blooded vertebrate animal of a class that is distinguished by the possession of hair or fur, females that secrete milk for the nourishment of the young, and (typically) the birth of live young.",
        },
        {
          title: "Multiverse",
          description: "The multiverse is a hypothetical group of multiple universes. Together, these universes comprise everything that exists: the entirety of space, time, matter, energy, information, and the physical laws and constants that describe them.",
        },
        {
          title: "Multiverse",
          description: "The multiverse is a hypothetical group of multiple universes. Together, these universes comprise everything that exists: the entirety of space, time, matter, energy, information, and the physical laws and constants that describe them.",
        }
      ],
    };
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

<template>
  <div id="app" class="container">
    <div class="card-wrapper">
      <div class="row">
        <div v-for="card in cardList" :key="card.id">
          <card
            class="col s3"
            :id="card.id"
            :name="card.name"
            :state="card.state"
            @removeCard="removeHandler"
          />
        </div>
      </div>
    </div>

    <div class="row card green lighten-5">
    <form class="col s12">
      <div class="row">
        <div class="input-field col s12">
          <input id="first_name" type="text" class="validate" v-model="cardName">
          <label for="first_name">Название карточки</label>
          <a
          class="waves-effect waves-light btn col s12"
          @click="addCard"
          >Добавить</a>
        </div>
      </div>
    </form>
  </div>
  </div>
</template>

<script>
import Card from "./components/Card.vue";

export default {
  name: "app",
  components: {
    Card
  },
  created() {
    this.cardList.map(card => {
      card.state = Math.random() > 0.5;
      return card;
    });
    this.idCounter = this.cardList.length;
  },
  data: () => ({
    idCounter: null,
    cardName: '',
    cardList: [
      {
        id: 0,
        name: "Lorem ipsum dolor.",
        state: true
      },
      {
        id: 1,
        name: "Lorem ipsum dolor 1",
        state: null
      },
      {
        id: 2,
        name: "Lorem ipsum dolor ",
        state: null
      },
      {
        id: 3,
        name: "Lorem ipsum dolor 3",
        state: null
      },
      {
        id: 4,
        name: "Lorem ipsum dolor 4",
        state: null
      },
      {
        id: 5,
        name: "Lorem ipsum dolor 5",
        state: null
      },
      {
        id: 6,
        name: "Lorem ipsum dolor 6",
        state: null
      },
      {
        id: 7,
        name: "Lorem ipsum dolor 7",
        state: null
      },
      {
        id: 8,
        name: "Lorem ipsum dolor 8",
        state: null
      },
      {
        id: 9,
        name: "Lorem ipsum dolor 9",
        state: null
      },
      {
        id: 10,
        name: "Lorem ipsum dolor 10",
        state: null
      }
    ]
  }),
  methods: {
    removeHandler(removedID) {
      this.cardList = this.cardList.filter((card) => card.id != removedID);
    },
    addCard() {
      this.cardList.push({
        id: this.idCounter,
        name: this.cardName,
        state: Math.random > 0.5,
      })
      this.idCounter++;
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

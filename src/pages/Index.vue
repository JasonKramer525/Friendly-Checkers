<template>
  <q-page class="flex flex-center">
    <q-page-container>
      <div class="row text-center">
        <div class="col-12" style="transform:translateY(-80px)">
          <h5
            class="title-font"
          >Welcome to Friendly Checkers! Select two agents from the dropdowns to compete against each other.</h5>
        </div>
      </div>
      <div class="row justify-center" style="transform:translateY(-100px)">
        <q-btn-dropdown color="red" :label="red" class="q-ma-sm">
          <q-list>
            <q-item clickable v-close-popup @click="setRed('Tonto')">
              <q-item-section>
                <q-item-label>Tonto</q-item-label>
              </q-item-section>
            </q-item>
            <q-item clickable v-close-popup @click="setRed('KramerAI')">
              <q-item-section>
                <q-item-label>KramerAI</q-item-label>
              </q-item-section>
            </q-item>
          </q-list>
        </q-btn-dropdown>

        <q-btn-dropdown color="black" :label="black" class="q-ma-sm">
          <q-list>
            <q-item clickable v-close-popup @click="setBlack('Tonto')">
              <q-item-section>
                <q-item-label>Tonto</q-item-label>
              </q-item-section>
            </q-item>
            <q-item clickable v-close-popup @click="setBlack('KramerAI')">
              <q-item-section>
                <q-item-label>KramerAI</q-item-label>
              </q-item-section>
            </q-item>
          </q-list>
        </q-btn-dropdown>
      </div>
      <div
        class="row justify-center vertical-middle text-center"
        style="transform:translateY(-80px)"
      >
        <main>
          <table>
            <tr v-for="(child, index, index2) in row1">
              <td v-if="index%2 == 1" :id="index*8">
                <p :class="pieces[index*8]"></p>
              </td>
              <td class="noPieceHere" v-if="index%2 == 0" :id="index*8">
                <p :class="pieces[index*8]"></p>
              </td>
              <td class="noPieceHere" v-if="index%2 == 1" :id="index*8+1">
                <p :class="pieces[index*8+1]"></p>
              </td>
              <td v-if="index%2 == 0" :id="index*8+1">
                <p :class="pieces[index*8+1]"></p>
              </td>
              <td v-if="index%2 == 1" :id="index*8+2">
                <p :class="pieces[index*8+2]"></p>
              </td>
              <td class="noPieceHere" v-if="index%2 == 0" :id="index*8+2">
                <p :class="pieces[index*8+2]"></p>
              </td>
              <td class="noPieceHere" v-if="index%2 == 1" :id="index*8+3">
                <p :class="pieces[index*8+3]"></p>
              </td>
              <td v-if="index%2 == 0" :id="index*8+3">
                <p :class="pieces[index*8+3]"></p>
              </td>
              <td v-if="index%2 == 1" :id="index*8+4">
                <p :class="pieces[index*8+4]"></p>
              </td>
              <td class="noPieceHere" v-if="index%2 == 0" :id="index*8+4">
                <p :class="pieces[index*8+4]"></p>
              </td>
              <td class="noPieceHere" v-if="index%2 == 1" :id="index*8+5">
                <p :class="pieces[index*8+5]"></p>
              </td>
              <td v-if="index%2 == 0" :id="index*8+5">
                <p :class="pieces[index*8+5]"></p>
              </td>
              <td v-if="index%2 == 1" :id="index*8+6">
                <p :class="pieces[index*8+6]"></p>
              </td>
              <td class="noPieceHere" v-if="index%2 == 0" :id="index*8+6">
                <p :class="pieces[index*8+6]"></p>
              </td>
              <td class="noPieceHere" v-if="index%2 == 1" :id="index*8+7">
                <p :class="pieces[index*8+7]"></p>
              </td>
              <td v-if="index%2 == 0" :id="index*8+7">
                <p :class="pieces[index*8+7]"></p>
              </td>
            </tr>
          </table>
        </main>
      </div>
      <div class="row justify-center" style="transform:translateY(-60px)">
        <q-btn color="secondary" label="Go!" @click="go" />
      </div>
    </q-page-container>
  </q-page>
</template>

<script>
export default {
  methods: {
    setRed(agent) {
      console.log(agent);
      this.red = agent;
    },
    setBlack(agent) {
      console.log(agent);
      this.black = agent;
    },
    go() {
      console.log("go!");
    }
  },
  data() {
    return {
      red: "Red Agent",
      black: "Black Agent",
      row1: [0, 0, 0, 0, 0, 0, 0, 0],
      pieces: [
        "blank",
        "black-piece",
        "blank",
        "black-piece",
        "blank",
        "black-piece",
        "blank",
        "black-piece",
        "black-piece",
        "blank",
        "black-piece",
        "blank",
        "black-piece",
        "blank",
        "black-piece",
        "blank",
        "blank",
        "black-piece",
        "blank",
        "black-piece",
        "blank",
        "black-piece",
        "blank",
        "black-piece",
        "blank",
        "blank",
        "blank",
        "blank",
        "blank",
        "blank",
        "blank",
        "blank",
        "blank",
        "blank",
        "blank",
        "blank",
        "blank",
        "blank",
        "blank",
        "blank",
        "red-piece",
        "blank",
        "red-piece",
        "blank",
        "red-piece",
        "blank",
        "red-piece",
        "blank",
        "blank",
        "red-piece",
        "blank",
        "red-piece",
        "blank",
        "red-piece",
        "blank",
        "red-piece",
        "red-piece",
        "blank",
        "red-piece",
        "blank",
        "red-piece",
        "blank",
        "red-piece"
      ]
    };
  }
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Anton&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Fira+Sans:wght@900&display=swap");

.mobile {
  display: none;
}

.desktop {
  margin: 0;
  width: 100%;
}

.noPieceHere {
  background-color: #f0d2b4;
}

td {
  text-align: center;
  background-color: #ba7a3a;
  width: 65px;
  height: 65px;
}

.red-turn-text {
  text-align: center;
  color: black;
  font-family: "open sans";
  font-size: 55px;
}

.black-turn-text {
  text-align: center;
  font-family: "open sans";
  font-size: 55px;
  color: lightgray;
}

.black-piece {
  width: 40px;
  height: 40px;
  padding: 12px;
  background-color: black;
  border: 1px solid white;
  border-radius: 50px;
  transform: translateY(8px);
}

.red-piece {
  width: 40px;
  height: 40px;
  padding: 12px;
  background-color: red;
  border: 1px solid white;
  border-radius: 50px;
  transform: translateY(8px);
}

.king.red-piece {
  background-color: orange;
}

.king.black-piece {
  background-color: purple;
}

p {
  display: inline-block;
}

#divider {
  font-size: 90px;
  margin-left: 15px;
  margin-right: 15px;
}

span {
  display: inline-block;
}

@media screen and (max-width: 560px) {
  .red-piece {
    height: 4.5vw;
    width: 4.5vw;
  }

  .black-piece {
    height: 4.5vw;
    width: 4.5vw;
  }

  td {
    width: 12vw;
    height: 12vw;
  }

  .red-turn-text {
    font-size: 40px;
  }

  .black-turn-text {
    font-size: 40px;
  }

  table {
    margin: 0;
  }

  .mobile {
    display: block;
  }

  .desktop {
    display: none;
  }

  .red-turn-text {
    -webkit-transform: rotate(-180deg);
    -moz-transform: rotate(-180deg);
    -o-transform: rotate(-180deg);
    transform: rotate(-180deg);
    filter: progid:DXImageTransform.Microsoft.BasicImage(rotation=2);
  }
}

@media screen and (max-width: 380px) {
  .red-piece {
    height: 3vw;
    width: 3vw;
  }

  .black-piece {
    height: 3vw;
    width: 3vw;
  }
}

@media screen and (max-width: 345px) {
  .red-piece {
    height: 2.5vw;
    width: 2.5vw;
  }

  .black-piece {
    height: 2.5vw;
    width: 2.5vw;
  }
}

.title-font {
  font-family: "Fira Sans", sans-serif;
  color: black;
  font-weight: 900;
}

@media screen and (max-width: 300px) {
  .red-piece {
    height: 1.5vw;
    width: 1.5vw;
  }

  .black-piece {
    height: 1.5vw;
    width: 1.5vw;
  }

  .red-turn-text {
    font-size: 35px;
  }

  .black-turn-text {
    font-size: 35px;
  }
}
</style>

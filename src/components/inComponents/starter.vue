<template>
  <div>
    <b-jumbotron
      style="
        background-color: #151a23;
        box-shadow: 5px 10px;
        border-radius: 12px;
      "
    >
      <b-row>
        <b-col class="options">
          <h3>Select Category</h3>
          <b-form-select
            style="
              background-color: #151a23;
              color: whitesmoke;
              border: 0.3px solid #333739;
            "
            v-model="selectedCategory"
            :options="categories"
          ></b-form-select>
        </b-col>
        <b-col align-self="center" class="options">
          <h3>Select Difficulty</h3>
          <b-button-group>
            <b-button
              class="diffBtn"
              id="any_diff"
              size="sm"
              variant="outline-primary"
              @click="setDifficult(null)"
              >Any Difficulty
            </b-button>
            <b-button
              class="diffBtn"
              id="easy_diff"
              size="sm"
              variant="outline-success"
              @click="setDifficult('easy')"
              >Easy
            </b-button>
            <b-button
              class="diffBtn"
              id="medium_diff"
              size="sm"
              variant="outline-warning"
              @click="setDifficult('medium')"
              >Medium
            </b-button>
            <b-button
              class="diffBtn"
              id="hard_diff"
              size="sm"
              variant="outline-danger"
              @click="setDifficult('hard')"
              >Difficult
            </b-button>
          </b-button-group>
        </b-col>
      </b-row>
      <b-row class="options" id="setAmount">
        <b-col>
          <h3 class="text-center">Number of Question</h3>
          <b-form-spinbutton
            d="amount-selecter"
            style="background-color: whitesmoke"
            v-model="currentAmount"
            min="10"
            max="50"
          ></b-form-spinbutton>
        </b-col>
      </b-row>
      <b-row class="startButton" align-h="center">
        <b-button
          @click="
            $store.dispatch('starter', {
              selectedCategory,
              difficulty,
              currentAmount
            })
          "
          variant="outline-info"
          href="#"
          ><h2>Start</h2></b-button
        >
      </b-row>
    </b-jumbotron>
  </div>
</template>
0
<script>
import { mapState } from 'vuex'
export default {
  data() {
    return {
      selectedCategory: null,
      difficulty: null,
      currentAmount: 10
    }
  },
  computed: {
    ...mapState(['categories'])
  },
  methods: {
    setDifficult(difficulty) {
      this.difficulty = difficulty
    }
  }
}
</script>

<style>
.startButton {
  padding-top: 50px;
}

.diffBtn {
  margin: 0 5px;
}
#any_diff:focus {
  background-color: #007bff;
  color: whitesmoke;
  box-shadow: 1px 1px #528bd6;
}
#easy_diff:focus {
  background-color: #28a745;
  color: whitesmoke;
  box-shadow: 1px 1px #47bc5d;
}
#medium_diff:focus {
  background-color: #ffc107;
  color: whitesmoke;
  box-shadow: 1px 1px #d6b85e;
}
#hard_diff:focus {
  background-color: #dc3545;
  color: whitesmoke;
  box-shadow: 1px 1px #d65d69;
}
.options {
  padding: 30px;
}

.options h3 {
  color: whitesmoke;
}

#setAmount {
  width: 300px;
  margin: auto;
}
</style>

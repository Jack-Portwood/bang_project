<template>

  <div id="whole-game">
    <p id="arrow-supply">Arrow Supply: {{mainArrowSupply}}</p>

    <div v-if="diceRoleComplete" :key="diceRoleComplete" id="player-div">
      <div>
        <drop class="drop" :players="players" @drop="handleDrop0">
          <p v-if="players[0].role != 'sheriff'">{{ players[0].character }}</p>
          <p v-if="players[0].role === 'sheriff'">⭐️ {{ players[0].character }} ⭐️</p>
          <p v-if="activePlayer === 0" :style="'border: 10px solid orange;'" :class="`char-image ${players[0].className}`"> </p>
          <p v-if="activePlayer != 0" :class="`char-image ${players[0].className}`"> </p>
          <p>Arrows: {{ players[0].arrowCount}}</p>
          <p>Health: {{ players[0].currentHealth}}</p>
        </drop>
      </div>
      <div>
        <drop class="drop" :players="players" @drop="handleDrop1">
          <p v-if="players[1].role != 'sheriff'">{{ players[1].character }}</p>
          <p v-if="players[1].role === 'sheriff'">⭐️ {{ players[1].character }} ⭐️</p>
          <p v-if="activePlayer === 1" :style="'border: 10px solid orange;'" :class="`char-image ${players[1].className}`"> </p>
          <p v-if="activePlayer != 1" :class="`char-image ${players[1].className}`"> </p>
          <p>Arrows: {{ players[1].arrowCount}}</p>
          <p>Health: {{ players[1].currentHealth}}</p>
        </drop>
      </div>
      <div>
        <drop class="drop" :players="players" @drop="handleDrop2">
          <p v-if="players[2].role != 'sheriff'">{{ players[2].character }}</p>
          <p v-if="players[2].role === 'sheriff'">⭐️ {{ players[2].character }} ⭐️</p>
          <p v-if="activePlayer === 2" :style="'border: 10px solid orange;'" :class="`char-image ${players[2].className}`"> </p>
          <p v-if="activePlayer != 2" :class="`char-image ${players[2].className}`"> </p>
          <p>Arrows: {{ players[2].arrowCount}}</p>
          <p>Health: {{ players[2].currentHealth}}</p>
        </drop>
      </div>
      <div>
        <drop class="drop" :players="players" @drop="handleDrop3">
          <p v-if="players[3].role != 'sheriff'">{{ players[3].character }}</p>
          <p v-if="players[3].role === 'sheriff'">⭐️ {{ players[3].character }} ⭐️</p>
          <p v-if="activePlayer === 3" :style="'border: 10px solid orange;'" :class="`char-image ${players[3].className}`"> </p>
          <p v-if="activePlayer != 3" :class="`char-image ${players[3].className}`"> </p>
          <p>Arrows: {{ players[3].arrowCount}}</p>
          <p>Health: {{ players[3].currentHealth}}</p>
        </drop>
      </div>
      <div>
        <drop class="drop" :players="players" @drop="handleDrop4">
          <p v-if="players[4].role != 'sheriff'">{{ players[4].character }}</p>
          <p v-if="players[4].role === 'sheriff'">⭐️ {{ players[4].character }} ⭐️</p>
          <p v-if="activePlayer === 4" :style="'border: 10px solid orange;'" :class="`char-image ${players[4].className}`"> </p>
          <p v-if="activePlayer != 4" :class="`char-image ${players[4].className}`"> </p>
          <p>Arrows: {{ players[4].arrowCount}}</p>
          <p>Health: {{ players[4].currentHealth}}</p>
        </drop>
      </div>
    </div>



    <div v-if="!diceRoleComplete" :key="diceRoleComplete" id="player-div2">
      <div class="drop">
        <p v-if="players[0].role != 'sheriff'">{{ players[0].character }}</p>
        <p v-if="players[0].role === 'sheriff'">⭐️ {{ players[0].character }} ⭐️</p>
        <p v-if="activePlayer === 0" :style="'border: 10px solid orange;'" :class="`char-image ${players[0].className}`"> </p>
        <p v-if="activePlayer != 0" :class="`char-image ${players[0].className}`"> </p>
        <p>Arrows: {{ players[0].arrowCount}}</p>
        <p>Health: {{ players[0].currentHealth}}</p>
      </div>
      <div class="drop">
        <p v-if="players[1].role != 'sheriff'">{{ players[1].character }}</p>
        <p v-if="players[1].role === 'sheriff'">⭐️ {{ players[1].character }} ⭐️</p>
        <p v-if="activePlayer === 1" :style="'border: 10px solid orange;'" :class="`char-image ${players[1].className}`"> </p>
        <p v-if="activePlayer != 1" :class="`char-image ${players[1].className}`"> </p>
        <p>Arrows: {{ players[1].arrowCount}}</p>
        <p>Health: {{ players[1].currentHealth}}</p>
      </div>
      <div class="drop">
        <p v-if="players[2].role != 'sheriff'">{{ players[2].character }}</p>
        <p v-if="players[2].role === 'sheriff'">⭐️ {{ players[2].character }} ⭐️</p>
        <p v-if="activePlayer === 2" :style="'border: 10px solid orange;'" :class="`char-image ${players[2].className}`"> </p>
        <p v-if="activePlayer != 2" :class="`char-image ${players[2].className}`"> </p>
        <p>Arrows: {{ players[2].arrowCount}}</p>
        <p>Health: {{ players[2].currentHealth}}</p>
      </div>
      <div class="drop">
        <p v-if="players[3].role != 'sheriff'">{{ players[3].character }}</p>
        <p v-if="players[3].role === 'sheriff'">⭐️ {{ players[3].character }} ⭐️</p>
        <p v-if="activePlayer === 3" :style="'border: 10px solid orange;'" :class="`char-image ${players[3].className}`"> </p>
        <p v-if="activePlayer != 3" :class="`char-image ${players[3].className}`"> </p>
        <p>Arrows: {{ players[3].arrowCount}}</p>
        <p>Health: {{ players[3].currentHealth}}</p>
      </div>
      <div class="drop">
        <p v-if="players[4].role != 'sheriff'">{{ players[4].character }}</p>
        <p v-if="players[4].role === 'sheriff'">⭐️ {{ players[4].character }} ⭐️</p>
        <p v-if="activePlayer === 4" :style="'border: 10px solid orange;'" :class="`char-image ${players[4].className}`"> </p>
        <p v-if="activePlayer != 4" :class="`char-image ${players[4].className}`"> </p>
        <p>Arrows: {{ players[4].arrowCount}}</p>
        <p>Health: {{ players[4].currentHealth}}</p>
      </div>
    </div>

    <div id="dice-div">
      <div v-if="!diceRoleComplete" :key="diceRoleComplete">
        <dice-roller :activePlayer="activePlayer"></dice-roller>
      </div>

      <div v-if="diceRoleComplete" :key="diceRoleComplete">
        <div id="dragDice">
          <drag v-for="(die, index) in choosenDice" class="drag" :key="index" :class="{ [die]: true }"
          :transfer-data="{ die, index } "
          @dragstart="dragging = die"
          @dragend="dragging = null">
          </drag>
      </div>
      <p id="standardText">Assign your dice pardner!</p>
    </div>
  </div>
</div>

</template>

<script>
import GameServices from "../Service/GameServices.js"
import {eventBus} from '../main.js';
import { Drag, Drop } from 'vue-drag-drop';
import DiceRoller from './DiceRoller.vue';
export default {
  name: 'player-display',
  props: ['players'],
  components: { Drag, Drop, 'dice-roller': DiceRoller },
  mounted(){
    eventBus.$on("finshedRolling",(payload) => {
      this.choosenDice = payload;
      this.diceRoleComplete = true;
      this.checkForThreeGatlins();
    });
    eventBus.$on("tooManyDynamite", () => {
      if(this.players[this.activePlayer].currentHealth > 0) {
        this.players[this.activePlayer].currentHealth -= 1;
        this.winConditions();
      };
      this.choosenDice = [];
      this.moveToNextPlayer();
    });
    eventBus.$on("arrowRolled", () => {
      this.players[this.activePlayer].arrowCount += 1;
      if(this.mainArrowSupply > 0) {
        this.mainArrowSupply -= 1;
      };
      this.checkMainArrowSupply();
    });
  },
  data () {
    return {
      choosenDice: null,
      diceRoleComplete: false,
      activePlayer:0,
      mainArrowSupply: 5
    }
  },
  methods: {
    checkForThreeGatlins(){
      let gatlinCount = 0;
      for(const die of this.choosenDice) {
        if(die === 'gatlin') {
          gatlinCount += 1;
        };
      };
      if (gatlinCount >= 3) {
        alert(`You have at least 3 Gatlins. All players take 1 damage!`);
        this.gatlinDamage();
        // TODO: move to next player if no good dice Left
        this.dropableDiceLeft();
      };
    },
    gatlinDamage(){
      for(const player of this.players) {
        if(player !== this.players[this.activePlayer]) {
          if(player.currentHealth > 0) {
            player.currentHealth -= 1;
          };
        };
      };
      this.winConditions();
    },
    winConditions(){
      let sheriff = null;

      for(let player of this.players) {
        if(player.role === "sheriff"){
          sheriff = player;
        };
      };
      let outlaw = null;
      for(let player of this.players){
        if(player.role === "outlaw"){
          outlaw = player;
        }
      }
      let renegade = null;
      for(let player of this.players){
        if(player.role === "renegade"){
          renegade = player;
        }
      }
      let deputy = null;
      for(let player of this.players){
        if(player.role === "deputy"){
          deputy = player;
        }
      }
      let result = "";
      if (renegade.currentHealth >= 1) {
        if (outlaw.currentHealth <= 0 && deputy.currentHealth <= 0 && sheriff.currentHealth <= 0){
          result = "Renegade Wins";
          alert('Renegade Wins');
        }
      }
      if (sheriff.currentHealth >= 1) {
        if (outlaw.currentHealth <= 0 && renegade.currentHealth <= 0){
          result = "Law Wins";
          alert('Law Win');
        }
      }
      if (sheriff.currentHealth <= 0 && result !== "Outlaw Wins"){
        if (outlaw.currentHealth >= 1 && renegade.currentHealth >= 1 && deputy.currentHealth >= 1){
          result = "Outlaw Wins";
          alert('Outlaws Win');
        }
      }
       if (sheriff.currentHealth <= 0 && result !== "Outlaw Wins"){
        if (renegade.currentHealth >= 1 && deputy.currentHealth >= 1 && outlaw.currentHealth <=0){
          result ="Outlaw Wins";
          alert('Outlaws Win');
        }
      }
      if(sheriff.currentHealth<= 0){
        if(renegade.currentHealth <= 0 && deputy.currentHealth <= 0 && outlaw.currentHealth <=0){
          result = "Draw";
          alert('Violence is not the answer ! ')
        }
      }
      return result;
    },
    checkMainArrowSupply(){
      if(this.players[this.activePlayer].currentHealth >0){
        alert(`You got shot with an arrow`);
      };
      if(this.mainArrowSupply === 0) {
        alert(`The main arrow supply is empty. Prepare to take arrow damage!`);
        for(const player of this.players) {
          if(player.currentHealth > 0) {
            player.currentHealth -= player.arrowCount;
          };
          if(player.currentHealth <= 0) {
            player.currentHealth = 0;
          };
          if(this.players[this.activePlayer].currentHealth === 0) {
            alert(`You succummbed to arrows. You are dead! Next!!!! `)
            eventBus.$emit(`activePlayerDiedByArrows`);
            this.moveToNextPlayer();
          };

          player.arrowCount = 0;
        };
        this.winConditions();
        this.mainArrowSupply = 5;
      };
    },
    handleDragover(group, data, event) {
      if (group !== data.group) {
        event.dataTransfer.dropEffect = 'none';
      }
    },
    moveToNextPlayer(){
      if(this.activePlayer === 4) {
        this.activePlayer = 0;
      }
      else {
        this.activePlayer += 1;
      };
      if(this.players[this.activePlayer].currentHealth === 0) {
        this.moveToNextPlayer();
      }
      this.choosenDice = null;
      this.diceRoleComplete = false;
    },
    dropableDiceCheck() {

      let dropableDiceLeft = false;
      let allAtFullHealth = true;

      for(const dice of this.choosenDice){
        if(dice === 'health') {
          for(const player of this.players) {
            if(player.currentHealth !== player.maxHealth ) {
              allAtFullHealth = false;
            };
          };
          dropableDiceLeft = true;
        };

        if(dice === 'shoot1') {
          dropableDiceLeft = true;
        }
      };
      if(allAtFullHealth === true && this.dice === 'health') {
        dropableDiceLeft === false;
      };
      if(dropableDiceLeft === false) {
        alert(`No more dice can be used. Your turn is over.`);
        this.moveToNextPlayer();
      };
    },
    handleDrop0(data) {
      if(data.die === 'health') {
        if(this.players[0].currentHealth === this.players[0].maxHealth) {
          alert(`The player is at full health`);
        }
        else if (this.players[0].currentHealth === 0) {
            alert('This player is deid ya numpty!');
        }
        else {
          this.players[0].currentHealth += 1;
          this.choosenDice.splice( data.index, 1 );
          alert(`Thanks for the health man!`);
        }
      };

      if(data.die === 'shoot1') {
        if(this.players[0].currentHealth === 0) {
          alert(`The player is already deid`);
        }
        else {
          this.players[0].currentHealth -= 1;
          this.choosenDice.splice( data.index, 1 );
          if(this.players[0].currentHealth <= 0) {
            this.players[0].currentHealth = 0;
            alert(`Ya killed me ya no good dirty rat!`)
            this.winConditions();
          } else {
            alert(`Argh! You got me!`);
          }
        }
      };

      this.dropableDiceCheck();
    },
    handleDrop1(data) {
      if(data.die === 'health') {
        if(this.players[1].currentHealth === this.players[1].maxHealth) {
          alert(`The player is at full health`);
        }
        else if (this.players[1].currentHealth === 0) {
            alert('This player is deid ya numpty!');
        }
        else {
          this.players[1].currentHealth += 1;
          this.choosenDice.splice( data.index, 1 );
          alert(`Thanks for the health man!`);
        }
      };

      if(data.die === 'shoot1') {
        if(this.players[1].currentHealth === 0) {
          alert(`The player is already deid`);
        }
        else {
          this.players[1].currentHealth -= 1;
          this.choosenDice.splice( data.index, 1 );
          if(this.players[1].currentHealth <= 0) {
            this.players[1].currentHealth = 0;
            alert(`Ya killed me ya no good dirty rat!`)
            this.winConditions();
          } else {
            alert(`Argh! You got me!`);
          }
        }
      };

      this.dropableDiceCheck();
    },
    handleDrop2(data) {
      if(data.die === 'health') {
        if(this.players[2].currentHealth === this.players[2].maxHealth) {
          alert(`The player is at full health`);
        }
        else if (this.players[2].currentHealth === 0) {
            alert('This player is deid ya numpty!');
        }
        else {
          this.players[2].currentHealth += 1;
          this.choosenDice.splice( data.index, 1 );
          alert(`Thanks for the health man!`);
        }
      };

      if(data.die === 'shoot1') {
        if(this.players[2].currentHealth === 0) {
          alert(`The player is already deid`);
        }
        else {
          this.players[2].currentHealth -= 1;
          this.choosenDice.splice( data.index, 1 );
          if(this.players[2].currentHealth <= 0) {
            this.players[2].currentHealth = 0;
            alert(`Ya killed me ya no good dirty rat!`)
            this.winConditions();
          } else {
            alert(`Argh! You got me!`);
          }
        }
      };

      this.dropableDiceCheck();
    },
    handleDrop3(data) {
      if(data.die === 'health') {
        if(this.players[3].currentHealth === this.players[3].maxHealth) {
          alert(`The player is at full health`);
        }
        else if (this.players[3].currentHealth === 0) {
          alert('This player is deid ya numpty!');
        }
        else {
          this.players[3].currentHealth += 1;
          this.choosenDice.splice( data.index, 1 );
          alert(`Thanks for the health man!`);
        }
      };

      if(data.die === 'shoot1') {
        if(this.players[3].currentHealth === 0) {
          alert(`The player is already deid`);
        }
        else {
          this.players[3].currentHealth -= 1;
          this.choosenDice.splice( data.index, 1 );
          if(this.players[3].currentHealth <= 0) {
            this.players[3].currentHealth = 0;
            alert(`Ya killed me ya no good dirty rat!`);
            this.winConditions();
          } else {
            alert(`Argh! You got me!`);
          }
        };

        this.dropableDiceCheck();
      }
    },
    handleDrop4(data) {
      if(data.die === 'health') {
        if(this.players[4].currentHealth === this.players[4].maxHealth) {
          alert(`The player is at full health`);
        }
        else if (this.players[4].currentHealth === 0) {
            alert('This player is deid ya numpty!');
        }
        else {
          this.players[4].currentHealth += 1;
          this.choosenDice.splice( data.index, 1 );
          alert(`Thanks for the health man!`);
        }
      };

      if(data.die === 'shoot1') {
        if(this.players[4].currentHealth === 0) {
          alert(`The player is already deid`);
        }
        else {
          this.players[4].currentHealth -= 1;
          this.choosenDice.splice( data.index, 1 );
          if(this.players[4].currentHealth <= 0) {
            this.players[4].currentHealth = 0;
            alert(`Ya killed me ya no good dirty rat!`);
            this.winConditions();
          } else {
            alert(`Argh! You got me!`);
          };
        };
      };
      this.dropableDiceCheck();
    }
  }
}
</script>

<style lang="css" scoped>

#dragDice {
  padding: 10px;
  margin: 20px;
  width: 600px;
  background: rgba(9, 10, 9, 0.5);
  box-shadow: 0 0 25px 1px black;
  border: 5px solid black;
  border-radius: 15px;
  height: 100px;
  text-align: center;
}

#standardText{
  font-size: 47px;
  color: #990033;
  text-shadow: 3px 3px #ffffff;
  text-align: center;
}

#arrow-supply{
  font-size: 47px;
  color: #990033;
  text-shadow: 3px 3px #ffffff;
  text-align: center;
}

.char-image {
  width: 160px;
  height: 160px;
  background-repeat:no-repeat;
  background-size: cover;
}

.bart-cassidy {
  background-image: url("../assets/images/bartcassidy.png");
  border: 5px solid black;
}

.paul-regret {
  background-image: url("../assets/images/paulregret.png");
  border: 5px solid black;
}

.slab-the-killer {
  background-image: url("../assets/images/Slabkiller.png");
  border: 5px solid black;
}

.el-gringo {
  background-image: url("../assets/images/elgringo.png");
  border: 5px solid black;
}

.calamity-janet {
  background-image: url("../assets/images/calamityjanet.png");
  border: 5px solid black;
}

.rose-doolan {
  background-image: url("../assets/images/rosedoolan.png");
  border: 5px solid black;
}

.black-jack {
  background-image: url("../assets/images/blackjack.png");
  border: 5px solid black;
}

#player-div {
  display: flex;
  flex-direction: row;
  justify-content: center;
}
#player-div2 {
  display: flex;
  flex-direction: row;
  justify-content: center;
}
#dice-div {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  height: 400px;
}
.drag {
  display: inline-block;
  vertical-align: top;
  padding: 10px;
  /* margin-bottom: 20px; */
  width: 80px;
  height: 80px;
  text-align: center;
}
.drag.shoot1 {
  background-image: url("../assets/images/shoot1.png");
  background-repeat: no-repeat;
  background-position: center;
  background-size: contain;
  margin-right: 10px;
  border-radius: 15px;
}
.drag.shoot2 {
  background-image: url("../assets/images/shoot2.png");
  background-repeat: no-repeat;
  background-position: center;
  background-size: contain;
  margin-right: 10px;
  border-radius: 15px;
}
.drag.arrow {
  background-image: url("../assets/images/arrow.png");
  background-repeat: no-repeat;
  background-position: center;
  background-size: contain;
  margin-right: 10px;
  border-radius: 15px;
}
.drag.health {
  background-image: url("../assets/images/health.png");
  background-repeat: no-repeat;
  background-position: center;
  background-size: contain;
  margin-right: 10px;
  border-radius: 15px;
}
.drag.gatlin {
  background-image: url("../assets/images/gatlin.png");
  background-repeat: no-repeat;
  background-position: center;
  background-size: contain;
  margin-right: 10px;
  border-radius: 15px;
}
.drag.dynamite {
  background-image: url("../assets/images/dynomite.png");
  background-repeat: no-repeat;
  background-position: center;
  background-size: contain;
  margin-right: 10px;
  border-radius: 15px;
}
.drop {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  width: 200px;
  height: auto;
  border: 5px;
  border-radius: 15px;
  font-size: 20px;
  background: rgba(195, 147, 80, 0.5);
  box-shadow: 0 0 25px 1px black;
}
.drop.allowed {
		background-color: #dfd;
}
#whole-game{
  height: 1100px;
  padding: 20px;
}

</style>

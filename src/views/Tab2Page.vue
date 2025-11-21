<template>
  <ion-page>
    <ion-header>
    </ion-header>
    <ion-content class="ion-padding">
      <p class="question-text">1. Which space agency decided to carry out first all-female spacewalk at the international Space Station (ISS)?</p>
        <QuizzButton v-for="(item, i) in answers" :key="i" :index="i" :answer-text="item" @click="clickedQuestion(i)" :class="[selectedAnswer.includes(i) ? 'selected' : '']"></QuizzButton>
      <ion-button slot="fixed" :disabled="selectedAnswer.length >= 1 ? false : true" class="confirm-btn" expand="block" @click="clickedConfirm()">Confirm Answer</ion-button>
    </ion-content>
  </ion-page>
</template>

<script setup>
import { ref } from 'vue'
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonItem, IonLabel, IonButton } from '@ionic/vue';
import QuizzButton from '../components/quizz/Button.vue';

const answers = ["Ans1","Ans2","Ans3","Ans4"];
const correctArray = ["Ans1","Ans2"];
const correctSingle = 2;

const questionType = 1;
let selectedAnswer = ref([]);

let checker = (arr, target) => target.every(v => arr.includes(v));

function clickedQuestion(index) {
  switch(questionType) {
  case 0:
    selectedAnswer.value = [index]
    break;
  case 1:
    if (!selectedAnswer.value.includes(index)) {
    selectedAnswer.value.push(index)
    } else {
      selectedAnswer.value = selectedAnswer.value.filter(item => item !== index);
    }
    break;
  default:
}
}

function clickedConfirm() {
  let isCorrect = false;
  switch(questionType) {
  case 0:
    if (selectedAnswer.value.includes(correctSingle)) { isCorrect = true }
    break;
  case 1:
    if (checker(answers, correctArray)) { isCorrect = true }
    break;
  default:
}
console.log("The answers were ",isCorrect)
}
</script>

<style scoped>
.question-text {
  margin-top: 50px;
  margin-bottom: 50px;
}

.confirm-btn {
--background: #4aabff;
--background: linear-gradient(180deg, rgba(74, 171, 255, 1) 0%, rgba(25, 148, 254, 1) 50%, rgba(0, 136, 255, 1) 100%);
--border-radius: 10px;
  text-transform: none !important;
  font-weight: 600 !important;
  color: var(--ion-background-color);
  height: 50px;
  font-size: 1em;
  width: 92%;
}

#question-content {
  height: calc(100% - 110px);
  overflow: auto;
  margin-bottom: 50px;
}

  ion-button[slot='fixed'] {
    bottom: 20px;
    right: 50%;
    transform: translateX(50%);
  }
</style>
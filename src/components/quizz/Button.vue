<template>
  <ion-button class="quizz-choice_btn" expand="block">
    <!-- <ion-label>{{ index + 1 }}. {{ answerText }}</ion-label> -->
    <ion-label>{{ answerText }}</ion-label>
  </ion-button>
</template>

<script setup>
import { IonButton, IonLabel} from '@ionic/vue';
defineProps({
  answerText: String,
  index: Number
});

</script>

<style scoped>
.quizz-choice_btn {
  text-transform: none !important;
  font-weight: 600 !important;
  color: var(--ion-text-color);
  --background: none;

    --border-color: #2C2E41;
    --border-style: solid;
    --border-width: 1px;
    --border-radius: 10px;
    
  --padding-top: 15px;
  --padding-bottom: 15px;
  margin-bottom: 10px;
}

.quizz-choice_btn.selected {
  color: #fff;
  --background: #2C2E41;
}

.quizz-choice_btn ion-label {
  /* text-align: left; */
  width: 100%;
}
</style>
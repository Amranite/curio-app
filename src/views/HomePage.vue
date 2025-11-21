<template>
  <ion-page>
    <ion-header class="main-tab">
      <ion-toolbar>
        <ion-img src="public/logo.png" alt="logo curio" class="main-tab_logo"></ion-img>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-card>
        <ion-card-content>
          <div class="x-counter">
            <div class="x-counter_side">
              <p class="x-counter_title">Questions Correct</p>
              <p class="x-counter_value">123</p>
            </div>
            <div class="x-counter_side">
              <p class="x-counter_title">Quizzes Answered</p>
              <p class="x-counter_value">123</p>
            </div>
          </div>
        </ion-card-content>
      </ion-card>
    </ion-content>
  </ion-page>
</template>

<script setup>
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonImg, IonCard, IonCardContent, IonCardHeader } from '@ionic/vue';
</script>
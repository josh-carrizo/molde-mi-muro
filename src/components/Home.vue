<template>
<div>
  <b-row>
    <b-col></b-col>
    <b-col cols="6">
      <br>
      <b-jumbotron bg-variant="info" text-variant="white" border-variant="dark">
      <router-link class="link-play" v-bind:to="{path: '/playTrivia'}">
        <b-button variant="outline-dark">Play!</b-button>
      </router-link>
        <br>
        <h6>Click the button above to start the trivia game</h6>
      </b-jumbotron>
    </b-col>
    <b-col></b-col>
  </b-row>
  <!--Table-->
  <b-row>
    <b-col></b-col>
    <b-col cols="6">
      <b-list-group horizontal="md" v-for="(qpoint, i) in qpoints" :key="i">
        <b-list-group-item>{{qpoint.userName}}</b-list-group-item>
        <b-list-group-item>{{qpoint.points}}/3</b-list-group-item>
        <b-list-group-item>100%</b-list-group-item>
      </b-list-group>
    </b-col>
    <b-col></b-col>

  </b-row>
</div>
</template>

<script>
import { db } from '@/firebase';  

  export default {
    name:"Home",
     firestore() { 
      return {
        qpoints: db.collection('qpoints')
      }
    },
    /*data() {
      return {
        items: [
          { age: 40, first_name: 'Dickerson', last_name: 'Macdonald' },
          { age: 21, first_name: 'Larsen', last_name: 'Shaw' },
          { age: 89, first_name: 'Geneva', last_name: 'Wilson' },
          { age: 38, first_name: 'Jami', last_name: 'Carney' }
        ]
      }
    }*/
  }
</script>
<!-- LETS FETCH THE DATA HERE,, USING THIS APROACH -->
<script setup>

import { onMounted, ref } from "vue";

const myGithubData = ref('null(WAITING FOR THE "FETCH Function")');

const fetch = fetch("YOUR GITHUB API LINK(eg api.github.com/user)");

// WHEN YOUR APP MOUNTS IT SHOULD FETCH THE DATA

onMounted(() => {

  //  CALL THE 'FETCH FUNCTION HERE'

  fetch()

  .then((Responsefromtheapi) => {

    //CONVERT THE RESPONSE FROM THE GITHUB API TO A JSON FILE SO YOU CAN BEGIN TO USE

    return Responsefromtheapi.json();

  })

  .then((Responsefromtheapi) => {

    // NOW LETS PUT EVERYTHING IN "MYGITHUBDATA" CREATED ABOVE

    myGithubData = Responsefromtheapi;

  });

});

</script>

<!-- NOW BEGIN TO USE THE RESPONSE IN UR IN YOUR HTML -->

<template>

<p>{{ myGithubData.name }}</p>

</template>

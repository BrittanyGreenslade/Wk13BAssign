<template>
  <div id="componentContainer">
    <!-- on click, call the function 'toggleView' -->
    <button @click="toggleView">
      Toggle
    </button>
    <br />
    <!-- bind the class cardView to this div for styling when cardViewOn===true and bind the class listView when 
    cardViewOn===false -->
    <!-- toggles trueness of cardViewOn boolean here -->
    <div v-bind:class="{ cardView: cardViewOn, listView: !cardViewOn }">
      <!-- loop through 'manyTweets' to find each 'tweet' with individual ids  -->
      <section v-for="tweet in manyTweets" :key="tweet.id">
        <!-- for every tweet in manyTweets, get the username and put it in an h3 tag -->
        <h3>
          {{ tweet.username }}
        </h3>
        <!-- for every tweet in manyTweets, get the tweet and put it in a p tag -->
        <p>
          {{ tweet.tweet }}
        </p>
        <!-- for every tweet in manyTweets, get the createdAt (date) and put it in a p tag -->
        <p>
          {{ tweet.createdAt }}
        </p>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  name: "tweets-section",
  //putting the tweet data here so it is accessible in mustaches in HTML
  data() {
    return {
      //returns the array of tweets
      manyTweets: [
        {
          tweet: `Yea your booty is nice but how thicc is your love for the environment.`,
          username: `@BillNye`,
          createdAt: `10-06-2017`,
          age: 62,
          id: 1,
        },
        {
          tweet: `My daughter's only 6 months old and already drawing. I'd hang it on the fridge but honestly, it's absolute garbage.`,
          username: `@RyanReynolds`,
          createdAt: `12-06-2017`,
          age: 44,
          id: 2,
        },
        {
          tweet: `Hey guys, wanna feel old? I'm 40. You're welcome.`,
          username: `@MacaulayCulkin`,
          createdAt: `08-26-2020`,
          age: 40,
          id: 3,
        },
        {
          tweet: `I like to think of myself less like an 'adult' and more like a 'former fetus'.`,
          username: `@AnnaKendrick`,
          createdAt: `12-22-2018`,
          age: 24,
          id: 4,
        },
        {
          tweet: `Is there an Uber eats that gets you the food but also feeds it to you and asks you about your day?`,
          username: `@Adamripp`,
          createdAt: `03-18-2018`,
          age: 16,
          id: 5,
        },
        {
          tweet: `@gerardway when you step on a scale does it tell you how much Gerard weighs please respond`,
          username: `@smosh`,
          createdAt: `10-05-2016`,
          age: 30,
          id: 6,
        },
        {
          tweet: `Every once in a while if I really need one, I ask my dog to give me a shoulder massage, and she never does`,
          username: `@SarahKSilverman`,
          createdAt: `09-5-2018`,
          age: 35,
          id: 7,
        },
        {
          tweet: `U a software update? because not now`,
          username: `@pakalupapito`,
          createdAt: `06-23-2017`,
          age: 14,
          id: 8,
        },
        {
          tweet: `2020 is what 2012 tried so hard to be`,
          username: `@TheSanPlanet`,
          createdAt: `04-26-2020`,
          age: 30,
          id: 9,
        },
        {
          tweet: `My closet is like 16 shirts I plan to fit into again and 1 shirt I wear every day`,
          username: `@TheCatWhisperer`,
          createdAt: `03-15-2019`,
          age: 12,
          id: 10,
        },
      ],
      //declare cardViewOn as true here so it can be accessed out of the function - it is updated on click
      cardViewOn: true,
    };
  },
  methods: {
    toggleView: function() {
      //the 'trueness' of cardViewOn is toggled in the {{}} above. this toggles between what the status of the
      //cardViewOn variable is AT THE TIME of the click - if it's false at click, it becomes true; if it's true at
      //click, it becomes false
      this.cardViewOn = !this.cardViewOn;
    },
  },
};
</script>

<style scoped>
/* styling for THIS component only */
#componentContainer {
  display: grid;
  place-items: center;
}
/* css for tweets in class listView (bound to the div above when cardViewOn===false) */
.listView {
  display: grid;
  width: 50%;
  row-gap: 20px;
}
/* css for tweets in class cardView (bound to the div above when cardViewOn===true) */
.cardView {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
  column-gap: 20px;
  row-gap: 20px;
  width: 70%;
}
/* styling for each individual tweet container */
section {
  box-shadow: 5px 5px 5px #888;
}
</style>

<template>
  <div id="pageContainer">
    <button id="toggleButton" @click="toggleView">
      Toggle
    </button>
    <br />
    <div v-bind:class="{ cardView: cardViewOn, listView: !cardViewOn }">
      <section v-for="tweet in manyTweets" :key="tweet.id">
        <h3>
          {{ tweet.username }}
        </h3>
        <p>
          {{ tweet.tweet }}
        </p>
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
  data() {
    return {
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
      //need to declare this here so it can be updated on click, otherwise the cardViewOn variable can't be
      //accessed outside of the function below. making it a 'global' variable I guess?
      cardViewOn: true,
    };
  },
  methods: {
    //changes the value of the variable when the fn is called
    toggleView: function() {
      this.cardViewOn = !this.cardViewOn;
    },
  },
};
</script>

<style scoped>
#pageContainer {
  display: grid;
  place-items: center;
}

.listView {
  display: grid;
  width: 50%;
  row-gap: 20px;
}
.cardView {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
  column-gap: 20px;
  row-gap: 20px;
  width: 70%;
}
section {
  box-shadow: 5px 5px 5px #888;
}
</style>

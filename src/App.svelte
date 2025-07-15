<script>
  let name = "Sophie C"; // Change this to your name
  let bio =
    "I am a rising 'Sophie'-more @ Cornell, with a penchant for pens, puns, and chants.";
  let hobbies = ["Alliteration", "Art", "Ambling"]; // List some hobbies

  import ImageCard from "./lib/ImageCard.svelte";
  import Expander from "./lib/Expander.svelte";

  let cardData = [
    {
      image: "/assets/aiCat 1.png",
      title: "Sophware",
      description: "(Software). I've built Swift-based apps and websites!",
      color: "#3AA6B9",
    },
    {
      image: "/assets/rumi.png",
      title: "Drawing",
      description: "I'm familiar with digital, traditional, and doodling!",
      color: "#FFD0D0",
    },
    {
      image: "/assets/iconAlt.png",
      title: "Language",
      description:
        "I like learning new languages -- of people, 'puters, puns, and patterns.",
      color: "#FF9EAA",
    },
  ];

  let funData = [
    {
      image: "/assets/meowfficial.png",
      title: "Meow",
      description:
        "I once built an app demonstrating the effects of AI on our cultural and physical climate using cats.",
    },
    {
      image: "/assets/icon.png",
      title: "Misfortune",
      description:
        "I stayed overnight at a jail once, because there were no vacant hotels that night (due to a local poker competition).",
    },
    {
      image: "/assets/jinu.png",
      title: "Muse",
      description: "I am in K-Pop Demon Hunters jail right now. #FREEJINU",
    },
  ];
</script>

<base href="/svelte-about-me/" />

<div class="container">
  <h1>Hello, World!</h1>
  <p>Hello, my name is <strong>{name}</strong>!</p>
  <p>{bio}</p>

  <h2>Some of My Favorite Things</h2>
  <div class="fav-section">
    <div class="thread"></div>
    <div class="card-container">
      {#each cardData as { image, title, description, color }}
        <ImageCard {image} {title} {description} {color} />
      {/each}
    </div>
  </div>

  <h2>Fun Facts</h2>
  <div class="fact-container">
    {#each funData as { image, title, description }}
      <Expander {image} {title} {description} />
    {/each}
  </div>

  <h2>My Hobbies</h2>
  <div class="hobbies">
    {#each hobbies as hobby}
      <div class="hobby">{hobby}</div>
    {/each}
  </div>
</div>

<style>
  h1 {
    color: #edd088;
    font-family: "Monaco", "monospace";
    letter-spacing: 5px;
    text-transform: uppercase;
  }
  h2 {
    color: lightcyan;
    font-family: "Monaco", "monospace";
    letter-spacing: 5px;
    text-transform: uppercase;
    padding-top: 15px;
  }
  .container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    max-width: 1000px;
    margin: 0 auto;
    padding: 30px;
    text-align: center;
    border-style: inset;
    border-radius: 30px;
    border-color: lightcyan;
    background-color: #844979;
    /* background-color: #493D9E; */
  }

  /* .fav-section {
    display: flex;
    flex-direction: column;
    justify-self: flex-start;
    border-style: inset;
    padding: 20px;
    border-radius: 20px;

  } */

  .thread {
    width: 100%;
    height: 10px;
    background-color: black;
    border-style: none;
    border-radius: 5px;
    /* position: absolute;
    z-index: 2; */
  }

  .card-container {
    display: flex;
    justify-content: center;
    /* position: absolute;
    z-index: 1; */

    /* align-items: center; */
    /* flex-direction: column; */
  }

  .fact-container {
    display: flex;
    justify-content: center;
    /*
    border-style: groove;
    background-color: bisque;
    color: #844979;
    border-radius: 20px; */
  }

  .hobbies {
    display: flex;
    justify-content: center;
    gap: 15px;
    flex-wrap: wrap;
  }
  .hobby:hover {
    color: #ffffff;
    border-color: #365e32;
    background-color: #242424;
    transition: 0.2s;
  }
  .hobby {
    background-color: #3498db;
    color: white;
    padding: 10px 15px;
    border-radius: 5px;
  }
</style>

<template>
  <div>
    <SwimLane
      header="New On Netflix"
      :cards="NewOnNetflix"
      className="NewOnNetflix"
    />
    <SwimLane
      header="Top 10 Movies"
      :cards="top10Movies"
      className="top10Movies"
    />
    <SwimLane
     header="US TV Shows" 
     :cards="USTVShows" 
     className="USTVShows" />
  </div>
</template>

<script>
import SwimLane from "./components/SwimLane.vue";

export default {
  name: "App",
  components: {
    SwimLane,
  },
  data() {
    return {
      NewOnNetflix: [
        { title: "Family Of Two", image: "/new1.PNG" },
        { title: "Charging Card", image: "/new2.PNG" },
        { title: "Pilecki's Report", image: "/new3.PNG" },
        { title: "Vow", image: "/new4.PNG" },
        { title: "Hacks", image: "/new5.PNG" },
        { title: "Agak Laen", image: "/new6.PNG" },
        { title: "The Titan Games", image: "/new7.PNG" },
        { title: "Lumberjack The Monster", image: "/new8.PNG" },
        { title: " Summer Vacation", image: "/new9.PNG" },
        { title: "Moving On", image: "/new10.PNG" },
      ],
      top10Movies: [
        { title: "Crew", image: "/top1.PNG" },
        { title: "Megan", image: "/top2.PNG" },
        { title: "Laapataa Ladies", image: "/top3.PNG" },
        { title: "Atlas", image: "/top4.PNG" },
        { title: "Shaitaan", image: "/top5.PNG" },
        { title: "Puss Boots", image: "/top6.PNG" },
        { title: "Article 370", image: "/top7.PNG" },
        { title: "Madame Web", image: "/top8.PNG" },
        { title: "Leo", image: "/top9.PNG" },
        { title: "Fighter", image: "/top10.PNG" },
      ],
     USTVShows: [
        { title: "Friends", image: "/us1.PNG" },
        { title: "The Vampire Diaries", image: "/us2.PNG" },
        { title: "Monk", image: "/us3.PNG" },
        { title: "Gilmore Girls", image: "/us4.PNG" },
        { title: "Young Sheldon", image: "/us5.PNG" },
        { title: "The Good Doctor", image: "/us6.PNG" },
        { title: "Suits", image: "/us7.PNG" },
        { title: "Resident Alien", image: "/us8.PNG" },
        { title: "Breaking Bad", image: "/us9.PNG" },
        { title: "Brooklyn nine-nine", image: "/us10.PNG" },
      ],
    };
  },
};
</script>

<style>
@import "./assets/styles.css";
</style>

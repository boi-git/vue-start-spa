<template>

<nav-bar
        :pages="pages"
        :active-page="activePage"
        :nav-link-click="(index) => (activePage = index)"
      ></nav-bar>
  
      <page-viewer :page="pages[activePage]"></page-viewer>

  </template>
  
  <script>
  import PageViewer from "./components/PageViewer.vue";
  import NavBar from "./components/NavBar.vue";
  
  export default {
    components: {
      PageViewer,
      NavBar,
    },
    data() {
      return {
        theme: "dark",
        activePage: 0,
        pages: [
          {
            link: { text: "Rosters", url: "index.html" },
            pageTitle: "Rosters Page",
            content: "This the Rosters content",
          },
          {
            link: { text: "Courts", url: "index.html" },
            pageTitle: "Courts Page",
            content: "This the Courts content",
          },
          {
            link: { text: "Events", url: "index.html" },
            pageTitle: "Events Page",
            content: "This the Events content",
          },
          {
            link: { text: "Shops", url: "index.html" },
            pageTitle: "Shops Page",
            content: "This the Shops content",
          },
        ],
        courts: [
          {
            courtName: "Court A",
            upcomingMatchName: "UBL Eagles vs UBL Eagles",
            upcomingMatchDetails: "Thu-Nov. 11- 8:00pm",
          },
          {
            courtName: "Court B",
            upcomingMatchName: "UBL Eagles vs UBL Eagles",
            upcomingMatchDetails: "Thu-Nov. 11- 8:00pm",
          },
          {
            courtName: "Court C",
            upcomingMatchName: "UBL Eagles vs UBL Eagles",
            upcomingMatchDetails: "Thu-Nov. 11- 8:00pm",
          },
        ],
      };
    },
  };
  </script>
  
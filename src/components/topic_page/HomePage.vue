<template>
  <div class="home-page">
    <TopicPageHeader></TopicPageHeader>
    <div ref="wikirow" class="row" :class="[isExpanded ? 'expanded' : 'notexpanded']">
      <WikipediaArticle class="column one"></WikipediaArticle>
      <WikidataItem class="column two"></WikidataItem>
      <div class="haze" id="wiki">
        <div class="toolbar-item block">
          <a @click="isExpanded = !isExpanded" class="toolbar-item-a">
            <i
              class="wikiglyph"
              :class="[isExpanded ? 'wikiglyph-caret-up' : 'wikiglyph-caret-down']"
            ></i>
          </a>
          <span class="tooltip">{{ isExpanded ? $t('general.collapse') : $t('general.expand') }}</span>
        </div>
      </div>
    </div>
    <Location id="location"></Location>
    <Instances id="instances"></Instances>
    <Subclasses id="subclasses"></Subclasses>
    <Kartta id="kartta"></Kartta>
<!--     <Partof id="partof"></Partof> -->
    <Parts id="parts"></Parts>
    <Twins id="twins"></Twins>
    <Locations id="locations"></Locations>
    <Effects id="effects"></Effects>
    <Works id="works"></Works>
    <Awards id="awards"></Awards>
    <Depicts id="depicts"></Depicts>
    <People id="people"></People>
    <Things id="things"></Things>
    <Affiliations id="affiliations"></Affiliations>
    <Depicted id="depicted"></Depicted>
    <TopicMap id="topicMap"></TopicMap>
<!--     <TopicTimeline id="topicTimeline"></TopicTimeline> -->
<!--     <EventList id="events"></EventList> -->
    <Similar id="similar"></Similar>
    <TopicImages
      @showImagesOnMap="onShowImagesOnMap"
      @showImagesOnTimeline="onShowImagesOnTimeline"
    ></TopicImages>
    <Footer></Footer>
  </div>
</template>

<script>
import Affiliations from "@/components/topic_page/Affiliations";
import Awards from "@/components/topic_page/Awards";
import Depicted from "@/components/topic_page/Depicted";
import Depicts from "@/components/topic_page/Depicts";
import Effects from "@/components/topic_page/Effects";
import Footer from "@/components/Footer";
import Instances from "@/components/topic_page/Instances";
import Location from "@/components/topic_page/Location";
import Locations from "@/components/topic_page/Locations";
import Kartta from "@/components/topic_page/Kartta";
import People from "@/components/topic_page/People";
import Partof from "@/components/topic_page/Partof";
import Parts from "@/components/topic_page/Parts";
import Similar from "@/components/topic_page/Similar";
import Subclasses from "@/components/topic_page/Subclasses";
import Things from "@/components/topic_page/Things";
import TopicImages from "@/components/topic_page/TopicImages";
import TopicMap from "@/components/topic_page/TopicMap";
import TopicPageHeader from "@/components/topic_page/TopicPageHeader";
import Twins from "@/components/topic_page/Twins";
import WikipediaArticle from "@/components/topic_page/Wikipedia";
import WikidataItem from "@/components/topic_page/Wikidata";
//import TopicTimeline from "@/components/topic_page/TopicTimeline";
//import EventList from "@/components/topic_page/EventList";
import Works from "@/components/topic_page/Works";
//import TopicNewspapers from '@/components/topic_page/TopicNewspapers'

export default {
  name: "TopicPage",
  props: {},
  data() {
    return {
      isExpanded: false
    };
  },
  components: {
    Affiliations,
    Awards,
    Depicted,
    Depicts,
    Effects,
    Footer,
/*     TopicTimeline, */
/*     EventList, */
    Instances,
    Location,
    Locations,
    Kartta,
    People,
    Parts,
    Partof,
    Similar,
    Subclasses,
    Things,
    TopicPageHeader,
    TopicMap,
    TopicImages,
    Twins,
    WikidataItem,
    WikipediaArticle,
    Works
  },
  computed: {},
  mounted: {
  },
  methods: {
    onShowImagesOnMap() {
      this.$nextTick(function() {
        //console.log("HomePage.onShowImagesOnMap");
        this.$scrollTo("#topicMap");
      });
    },
    onShowImagesOnTimeline() {
      //console.log("HomePage.onShowImagesOnTimeline");

      this.$scrollTo("#topicTimeline");
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>

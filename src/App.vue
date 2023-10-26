<template>
  <div id="wrapper">
    <div id="movie-list">
      <MovieList @movieSelect="movieSelectHandler" />
    </div>

    <div id="details">
      <MovieDetails :movieObject="selectedMovie" />
    </div>
    <div class="fade"></div>
    <section class="star-wars">
      <div class="crawl">
        <div class="quote">
          <span>
            Rebellions are built on hope. - Jyn The ability to speak does not make you intelligent.
            - Qui-Gon Jinn
          </span>
          <span> Try not. Do or do not. There is no try. —Yoda </span>
          <span>
            Who's the more foolish: the fool or the fool who follows him? —Obi-Wan Kenobi
          </span>
          <span> Your focus determines your reality. —Qui-Gon Jinn </span>
          <span> No longer certain that one ever does win a war, I am. —Yoda</span>
          <span>
            In a dark place we find ourselves and a little more knowledge lights our way. —Yoda
          </span>
          <span>
            Sometimes we must let go of our pride and do what is requested of us. —Anakin Skywalker
          </span>
          <span> I like firsts. Good or bad, they're always memorable. —Ahsoka Tano </span>
          <span>
            Once you start down the dark path, forever will it dominate your destiny. —Yoda
          </span>
          <span>Fear leads to anger, anger leads to hate, hate leads to suffering. —Yoda </span>
          <span>I am one with the Force and the Force is with me. —Chirrut </span>
          <span
            >You can't stop change any more than you can stop the suns from setting. —Shmi Skywalker
          </span>
          <span
            >That's how we're gonna win. Not fighting what we hate, saving what we love. —Rose
          </span>
          <span> Rebellions are built on hope. —Jyn Erso </span>
          <span>
            We'll always be with you. No one's ever really gone. A thousand generations live in you
            now. —Luke Skywalker
          </span>
        </div>
      </div>
    </section>
  </div>
</template>
<script>
import MovieList from './components/MovieList.vue'
import MovieDetails from './components/MovieDetails.vue'

export default {
  components: {
    MovieList,
    MovieDetails
  },
  data() {
    return {
      selectedMovie: undefined
    }
  },
  methods: {
    movieSelectHandler(movieObject) {
      this.selectedMovie = movieObject
    }
  }
}
</script>
<style scoped>
.fade {
  position: relative;
  width: 100%;

  background-image: linear-gradient(0deg, transparent, black 75%);
  z-index: 1;
}

.star-wars {
  display: flex;
  justify-content: center;
  position: relative;
  height: 800px;
  color: #feda4a;
  font-family: 'Pathway Gothic One', sans-serif;
  font-size: 500%;
  font-weight: 600;
  letter-spacing: 6px;
  line-height: 150%;
  perspective: 250px;
  text-align: justify;
}

.crawl {
  position: relative;
  top: 99999px;
  transform-origin: 50% 100%;
  animation: crawl 60s linear infinite;
}

.crawl > .quote {
  font-size: 90%;
  text-align: left;
}

.crawl > .quote {
  margin: 0 0 100px;
  text-transform: uppercase;
}

@keyframes crawl {
  0% {
    top: -100px;
    transform: rotateX(20deg) translateZ(0);
  }
  100% {
    top: -6000px;
    transform: rotateX(25deg) translateZ(-2500px);
  }
}

span {
  display: inline-block;
  margin-top: 15px;
}

#wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

#details {
  display: flex;
  flex-direction: row;
  align-items: center;

  margin: 50px 15vw;
  color: white;
}
#movie-list {
  color: white;
}

#quote {
  max-width: 500px;
}
</style>

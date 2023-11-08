<template>
  <div class="svg-img">
    <div class="hero p-4">
      <div class="stay-put-head">
        <h1 class="mb-1">Welcome To My World</h1>
        <p class="mb-4">Discover New Experiences With Me</p>
        <hr>
      </div>
      <section>
        <div class="home row" id="home">
          <div class="content-Container col-12 col-md-8 col-sm-6 m-0" style="height: 50vh; overflow: hidden;">
            <h3>{{ paragraphTitle }}</h3>
            <div class="row pt-4" style="height: 30vh">
              <div class="col-1 text-center content-navigator" style="height: 100%; overflow: hidden;">
                <button @click="scrollToParagraph(1, 'Me, Myself and I 1')" class="content-button"></button>
                <button @click="scrollToParagraph(2, 'Me, Myself and I 2')" class="content-button"></button>
                <button @click="scrollToParagraph(3, 'Me, Myself and I 3')" class="content-button"></button>
                <button @click="scrollToParagraph(4, 'Me, Myself and I 4')" class="content-button"></button>
                <button @click="scrollToParagraph(5, 'Me, Myself and I 5')" class="content-button"></button>
              </div>
              <div class="col-11 p-5" style="height: 100%; overflow-y: hidden;">
                <div class="self-intro mb-5 mt-1" :id="'paragraphId1'">
                  <p>... Lorem ipsum dolor sit amet consectetur adipisicing elit.
                    Obcaecati velit
                    commodi tempora fugiat maxime facere incidunt saepe, temporibus dolorum veritatis unde reprehenderit
                    iusto
                    assumenda, molestiae iure debitis. At, tempore atque?</p>
                </div>
                <div class="self-intro mb-5" :id="'paragraphId2'">
                  <p>... Lorem ipsum dolor sit amet consectetur adipisicing elit.
                    Obcaecati velit
                    commodi tempora fugiat maxime facere incidunt saepe, temporibus dolorum veritatis unde reprehenderit
                    iusto
                    assumenda, molestiae iure debitis. At, tempore atque?</p>
                </div>
                <div class="self-body mb-5" :id="'paragraphId3'">
                  <p>... Lorem ipsum dolor, sit amet consectetur adipisicing elit.
                    Voluptates ratione
                    id tenetur aperiam unde beatae, necessitatibus similique minima est quis soluta eligendi laudantium
                    doloribus in atque vero ut nobis tempora?</p>
                </div>
                <div class="self-conclusion mb-5" :id="'paragraphId4'">
                  <p>... Lorem ipsum dolor sit amet consectetur adipisicing
                    elit. Modi molestias natus ipsum fugit soluta facilis, distinctio itaque rem cumque voluptates ad?
                    Dolorum
                    fugit velit repudiandae ipsum neque enim consequatur unde.</p>
                </div>
                <div class="self-conclusion mb-5" :id="'paragraphId5'">
                  <p>... Lorem ipsum dolor sit amet consectetur adipisicing
                    elit. Modi molestias natus ipsum fugit soluta facilis, distinctio itaque rem cumque voluptates ad?
                    Dolorum
                    fugit velit repudiandae ipsum neque enim consequatur unde.</p>
                </div>
              </div>
            </div>
          </div>
          <div class="img-Container col-12 col-md-3 col-sm-6 m-0">
            <img class="homeImg" src="https://i.postimg.cc/02V0Sk0Q/C12-C1-Sidwell-Batyi-1-removebg-preview.png" alt="">
          </div>
        </div>
      </section>
      <div class="section" id="about">
        <router-view></router-view>
      </div>
      <div class="section" id="references">
        <router-view></router-view>
        <References v-if="showReferences" />
      </div>
      <section class="section" id="references">
        <References />
      </section>
      <div>
        <h1>Sidwell</h1>
        <h1>Sidwel</h1>
        <h1>Sidwel</h1>
        <h1>Sidwel</h1>
        <h1>Sidwel</h1>
        <h1>Sidwel</h1>
        <h1>Sidwel</h1>
        <h1>Sidwel</h1>
        <h1>Sidwel</h1>
        <h1>Sidwel</h1>
        <h1>Sidwel</h1>
        <h1>Sidwel</h1>
        <h1>Sidwel</h1>
        <h1>Sidwel</h1>
      </div>
    </div>
  </div>
</template>

<script>
import References from "@/components/References.vue";

export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  components: {
    References
  },

  data() {
    return {
      paragraphTitle: 'Me, Myself and I',
      paragraphTitle: 'Me, Myself and I 2',
      paragraphTitle: 'Me, Myself and I 3 ',
      paragraphTitle: 'Me, Myself and I 4',
      paragraphTitle: 'Me, Myself and I 5',
      isReferencesModalOpen: true
    }
  },
  methods: {
    scrollToParagraph(paragraphId, title) {
      this.paragraphTitle = title;
      const element = document.getElementById(`paragraphId${paragraphId}`);
      if (element) {
        const container = document.querySelector('.col-11');
        const offset = element.offsetTop - container.offsetTop;
        container.scrollTo({ top: offset, behavior: 'smooth' });
      }
    },
    setParagraphTitle(title) {
      this.paragraphTitle = title;
    },
  },
};
</script>



<style scoped>
/* Your styles */
</style>


<style scoped>
* {
  text-align: center;
  font-family: 'Irish Grover';
  color: #bfc0c6;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  letter-spacing: 3px;
}

.svg-img {
  height: 100vh;
  /* width: 100vw; */
  background-image: linear-gradient(rgba(0, 0, 0, 0.65), rgba(0, 0, 0, 0.65)), url(https://i.postimg.cc/SKXT0HfQ/Mac-Book-Pro-16-2.png);
  background-repeat: no-repeat;
  background-size: cover;
  display: flex;
  justify-content: center;
  align-items: center;
}

.hero {
  width: 75%;
  height: 600px;
  text-align: center;
  margin: auto;
  background-color: #000;
  opacity: 0.85;
  box-shadow: 0 0 4px rgba(15, 166, 110, 0.5);
  border-radius: 5px;
  position: relative;
  overflow-y: scroll;
  overflow-x: hidden;
}

.hero::after {
  content: '';
  background-color: #1BF2B5;
  width: 5px;
  height: 90%;
  position: absolute;
  right: -5px;
  top: 5%;
}

::-webkit-scrollbar {
  width: 10px;
  background-color: #0D0D0D;
  border: 4px;
  border-color: #0FA66E;
}

::-webkit-scrollbar-thumb {
  background-color: #D90754;
  border-radius: 10em;
  transition: 1s ease;
}

::-webkit-scrollbar-thumb:hover {
  border: 0.5px solid #1BF2B5;
}

html {
  scroll-behavior: smooth;
}

#home {
  height: 90%;
}

.homeImg {
  height: 100%;
  width: 100%;
  background-color: #000;
  opacity: 0.8;
  transform: scaleX(-1);
  margin: auto;
}

h1 {
  color: #D90754;
}

h5 {
  margin-bottom: 1.5rem;
}

h3 {
  color: #1BF2B5;
  margin-bottom: 1.5rem;
}

p {
  font-size: medium;
}

hr {
  margin: auto;
  margin-bottom: 1.5rem;
  width: 85%;
  color: #1BF2B5;
}

button {
  width: 1.5rem;
  margin-bottom: 15px;
  border-radius: 50%;
  height: 1.5rem;
}

.inner-content {
  height: 10vh;
  background-color: red;
}

.content-navigator {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  position: sticky;
  top: 20vh;
}

.content-button {
  width: 1.5rem;
  margin-bottom: 15px;
  border-radius: 50%;
  height: 1.5rem;
  background-color: #D90754;
  transition: transform 0.4s;
}

.content-button:nth-child(3) {
  width: 1.8rem;
  height: 1.8rem;
  transform: scale(1.1);
}

.content-button:nth-child(1) {
  width: 0.8rem;
  height: 0.8rem;
  transform: scale(1);
}

.content-button:nth-child(5) {
  width: 0.8rem;
  height: 0.8rem;
  transform: scale(1);
}

.content-button:hover {
  transform: scale(1.3);
}

.content {
  overflow-y: scroll;
  overflow-x: hidden;
  max-height: 70vh;
  padding-right: 10px;
}

.img-Container {
  height: 80%;
  padding: 1rem;
}





.img-Container {
  position: relative;
  overflow: hidden;
}

.img-Container::before {
  content: "";
  position: absolute;
  left: 0;
  top: 0;
  bottom: 0;
  width: 1px;
  background-color: #0FA66E;
  transition: height 3s ease;
  z-index: 1;
  height: 5%;
  margin-top: auto;
  margin-bottom: auto;
}

.img-Container:hover::before {
  height: 50%;
}

hr {
  border: 1px solid #0FA66E;
  border-radius: 1px;
  color: #0FA66E;
}

@media (max-width: 500px) {
  .hero {
    width: 100%;
    height: auto;
    margin-left: 0;
  }

  .homeImg {
    height: 40%;
  }
}
</style>
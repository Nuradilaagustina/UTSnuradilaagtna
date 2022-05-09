<script setup>
import NavBar from "../components/Navbar.vue";
</script>

<script>

export default {
  name: "Ad-Duhaa",
  data(){
    return{
      chapter: null,
      verses: [],
      translations: [],
      audio_file: null,
      info_surat: null,

    }
  },
  methods: {
    getChapter(){
      fetch('https://api.quran.com/api/v4/chapters/93?language=id',{
        method: 'GET'
      })
          .then(response => {
            if(response.ok){
              return response.json();
            }
          })
          .then(json => {
            this.chapter = json.chapter;
          })
    },
    getVerses(){
      fetch('https://api.quran.com/api/v4/quran/verses/uthmani?chapter_number=93&juz_number=30', {
        method: 'GET'
      })
          .then(res =>{
            if(res.ok){
              return res.json()
            }
          })
          .then(json => {
            this.verses = json.verses;
          })
    },
    getTranslate() {
      fetch('https://api.quran.com/api/v4/quran/translations/33?chapter_number=93&juz_number=30', {
        method: 'GET'
      })
          .then(response => {
            if (response.ok) {
              return response.json();
            }
          })
          .then(json => {
            this.translations = json.translations;
          });
    },
    getAudio() {
      fetch('https://api.quran.com/api/v4/chapter_recitations/5/93', {
        method: 'GET'
      })
          .then(response => {
            if (response.ok) {
              return response.json();
            }
          })
          .then(json => {
            this.audio_file = json.audio_file;


          });
    },

  getInfosurat() {
    fetch('https://api.quran.com/api/v4/chapters/91/info?language=id', {
      method: 'GET'
      })
        .then(response => {
          if (response.ok) {
            return response.json();
          }
      })
          .then(json => {
            this.info_surat = json.info_surat;
          });
  },

  },

  mounted() {
    this.getChapter();
    this.getVerses();
    this.getTranslate();
    this.getAudio();
    this.getInfosurat();
  }
}


</script>
<template>
  <main>
    <NavBar/>
    <div class="text">
      <p class="title text-center text-black">
        QS. Ad-Duha (1-11) </p>
      <p class="subtitle text-center text-black">
        Surah ke 93 </p>
    </div>
    <div class="bismillah text-center">بِسْمِ اللَّهِ الرَّحْمَنِ الرَّحِيْم </div>

    <hr>
    <section>
      <h1 class="surah text-start" v-if="chapter">{{chapter.name_arabic}}
        <br>{{chapter.verses_count}} Ayat</h1>
      <hr>
      <p v-if="audio_file" class="has-text-right">
        <audio controls>
          <source :src=audio_file.audio_url type="audio/mpeg">
          Your browser does not support the audio element.
        </audio>
      </p>
      <hr>
      <div v-for="verse in verses">
        <p class="ayat text-end">
          {{verse.text_uthmani}} {{verse.verse_key}}
        </p>
        <hr>
      </div>
      <div v-for="translations in translations">
        <p class="translate text-start">
          {{translations.text}}
        </p>
        <hr>
        <p class="info" v-if="info_surat">{{info_surat.text}}</p>
      </div>

    </section>
  </main>
</template>

<style>
.text{
  margin-top: 3rem;
  font-size: 35px;
  padding: 20px 25px;
  border: 4px solid #4a914a;
 }
.bismillah{
  margin-top: 50px;
  font-size: 30px;
  background-color: green;
}
.ayat{
  font-size: 25px;
}
.translate{
  font-size: 20px;
}
</style>



<template>
  <div>
    <h1>This is an profile page. My name is Marko!</h1>

    <zbroji-brojeve broj1="37" broj2="74" />

    <moja-kartica naslov="Prva kartica" tekst="Ovo je moja prva komponenta." />
    <moja-kartica naslov="Druga kartica" tekst="Ovo je moja prva komponenta." />
    <moja-kartica naslov="Treća kartica" tekst="Ovo je moja prva komponenta." />


    Napraviti komponentu ZbrojiBrojeve koja prima dva argumenta "broj1" i "broj2"
    i ispisuje tekst unutar paragrafa "Zbroj unesenih brojeva iznosi {{ zbroj }}"
  </div>
</template>

<script>
import MojaKartica from '../components/MojaKartica.vue'
import ZbrojiBrojeve from '../components/ZbrojiBrojeve.vue'

export default {
  name: 'Profile',
  components: {
    MojaKartica,
    ZbrojiBrojeve
  }
}
</script>

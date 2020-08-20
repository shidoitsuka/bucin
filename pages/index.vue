<template>
  <v-container>
    <v-card class="mx-auto" width="300" max-height="300" outlined>
      <v-list-item two-line>
        <v-list-item-content>
          <v-card-text>{{ stories[currentPage] }}</v-card-text>
        </v-list-item-content>
      </v-list-item>
      <hr />
      <v-card-actions>
        <v-btn text :disabled='currentPage == 0' @click="currentPage--">Prev</v-btn>
        <v-spacer></v-spacer>
        <v-btn text @click="currentPage == 23 ? '' : currentPage++" :to="currentPage == 23 ? '/landing' : '#'">Next</v-btn>
      </v-card-actions>
    </v-card>
    <audio src="~/assets/music.mp3" autoplay controls loop style="position: fixed; top: -500vh" />
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      stories: {
        0: `Hi! Makasih udah buka ini.
        Jangan klik next kalo belum siap nahan cringe ya,
        soalnya kamu tau sendiri kan kalo aku udah ngomong panjang lebar itu biasanya berakhir cringe :p`,
        1: `Jadi gini, paling pertama aku mau minta maaf karna ngecewain kamu.
        Jujur aja, aku beneran ga ada niatan lain selain ngejaga perasaanmu waktu berangkat ke malang itu.`,
        2: `Aku mau minta maaf juga karena udah ngehabisin 4 bulan mu sama orang kayak aku,
        ntah knp aku udah ngerasa kalo waktu - waktu kaya gini tuh bakalan dateng. Cepat/lambat.`,
        3: "Tau ga kok aku bisa tau?",
        4: `We live on different world, baby.
        I have literally nothing on my life:) Se-keras apapun aku nyoba buat ngimbangin kamu, fakta gak bakalan bisa berubah kalo aku ini ya... gini.`,
        5: "You have almost everything, and I have almost nothing.",
        6: `Ga perlu kujelasin lagi pasti udah paham kan? wkwk
        Oiya, tenang aja. Aku ga ada maksud aneh - aneh lewat web sederhana ini kok.`,
        7: `Aku ga minta kamu balik ke aku juga kok. Aku cuma pengen kamu ga benci aku, atau minimal berkurang deh rasa benci nya.`,
        8: "Aku memang gak pernah pantes buat kamu, dan gak ada yang bisa ngubah fakta itu.",
        9: `Kedua, aku pernah bilang kan "kalopun kita ga bareng selamanya, minimal aku mau berguna buat kamu dengan cara ngerubah kamu menjadi lebih baik lagi"?`,
        10: `Aku mau bilang kamu itu cantik, suaramu itu bagus, pola pikirmu juga ok walaupun beberapa harus di benahi (menurutku sih hehe). Tanggal 19 Agustus waktu aku nongkong sama temenku yang dari sidoarjo, semuanya setuju kalo kamu itu memang lebih good looking daripada mantanku yang aku ga mau nyebutin namanya.`,
        11: `Kelebihanmu jauh lebih banyak kalo ku jabarin satu - persatu.`,
        12: "Ketiga, aku mau minta maaf kalo selama ini aku juga gak sepenuhnya jujur sama kamu. Mulai dari soal kondisi pribadiku, keluargaku, dan lain sebagainya.",
        13: `Bukannya aku pembohong. Karena tiap kamu nanya, aku selalu jawab apa adanya. Tapi ketika kamu gak nanya, aku gak pernah cerita.`,
        14: "Karena aku sadar, aku ini se-nggak pantes itu buat kamu.",
        15: "Maafin keegoisanku yang bikin aku gak mau cerita soal semuanya.",
        16: "Maafin keegoisanku yang bikin aku gak mau ninggalin kamu secepat itu.",
        17: "Maafin keegoisanku yang bikin aku pengen kamu seutuhnya.",
        18: "Se-egois itu aku? Iya. Bener kok. Maaf ya chelsea",
        19: "Waktu kita emang singkat. Sangat singkat. Tapi kamu ngasih aku warna baru di kehidupanku.",
        20: "Aku gak mau kita berakhir.",
        21: "Tapi udah saatnya aku sadar, kalo aku memang gak bakalan bisa pantes buat kamu.",
        22: "Maafin latar belakangku yang begini ya.",
        23: "I ❤ You."
      },
      currentPage: 0
    };
  }
};
</script>

<style lang="scss">
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>

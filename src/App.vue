<script setup>
  import { ref } from 'vue';

  let msg = "Ini adalah teks interpolaris";;
  let headName = "<h1>Nama Saya Sandy</h1>";
  let pesan = "sekarang kamu bisa melihat binding attribute";
  let number = 7;
  let seen = true;

  // Split Reverse Message
  let message = ref("Coba Balikan Pesan Ini !");
  function balikkanMessage(){
    message.value = message.value.split('').reverse().join('')
  }

  // Pengulangan
  let coba = [
    {text: 'Belajar JavaScript' },
    {text: 'Belajar Vue.js' },
    {text: 'Belajar React.js' }
  ]
  
  // Input
  let pesan2 = ref("Hai Nama Saya Sandy Saputra");
  
</script>

<template>
  <div>
    <span>{{ msg }}</span> <br>

    <span style="color: aqua;">Ini adalah text RAW HTML</span><br>
    <span>{{ headName }}</span><br>

    <button v-bind:on-click="tombolSandy">KLIK</button><br>

    {{ number + 1 }} <br>

    {{ msg.split('').reverse().join('')}} <br>
    
    <span v-if="seen">Saya bisa melihat kamu</span><br>

    <span :title="pesan">Coba arahkan kursor ke sini, maka anda akan melihat binding attribute</span>

    <!-- Pengulangan / For -->
    <ol>
      <li v-for="pengulangan in coba">
        {{ pengulangan.text }}
      </li>
    </ol>
    
    <!-- Split Button / Membalikan Pesan -->
    <span>{{ message }}</span><br>
    <button v-on:click="balikkanMessage">Balikan Message</button>

    <!-- Input -->
    <p>{{ pesan2 }}</p>
    <input v-model="pesan2">

  </div>
</template>
<template>
  <div class="">
    <video
      ref="video"
      src="/videobg.mp4"
      class="fixed top-0 left-0 h-full w-full object-cover z-0 fade-in"
      autoplay
      loop
    />

    <div class="fixed bottom-10 left-5 z-20 fade-in">
      <input
        type="range"
        v-model="volume"
        class="w-32 volume-slider"
        min="0"
        max="1"
        step="0.05"
      />
    </div>

    <section class="relative text-8xl mx-auto w-fit">
      <div class="mx-12 backdrop-blur-[7rem] rounded-[1.4rem] my-12 py-5 px-5 fade-in-up">
        <h1 class="text-white text-center mb-12">Київстар: Зона Кiбернетичного Вiдродження</h1>

        <p class="text-2xl fade-in-up">
          <i>12 грудня 2023 року мобiльний оператор «Київстар» зазнав масштабної хакерської атаки, яка призвела до значних збоїв у роботi його мережi.
            Це стала одна з найбiльших кiберзагроз для української телекомунiкацiйної iнфраструктури, що змусила компанiю вжити екстрених заходiв
            для вiдновлення послуг i забезпечення безпеки зони.</i>
        </p>

        <b class="text-5xl fade-in-up">Хронологiя атаки:</b>
        <p class="text-2xl fade-in-up">
          12 грудня 2023 року стала чорним днем для «Київстар», коли компанiя виявила потужну хакерську атаку на свої системи. Проблеми з доступом до послуг зв'язку та iнтернету вiдчули мiльйони абонентiв, особливо у великих мiстах України. Це стало першим масштабним кiбернападом на компанiю за багато рокiв, що поставило пiд загрозу стабiльнiсть мобiльних комунiкацiй в країнi.
        </p>

        <b class="text-5xl fade-in-up">Метод проникнення та першi кроки вiдновлення:</b>
        <p class="text-2xl fade-in-up">
          Згiдно з офiцiйною iнформацiєю вiд «Київстар», зловмисники проникли в системи оператора через акаунт одного з партнерiв. Завдяки цьому хакери здобули доступ до важливих компонентiв iнфраструктури компанiї. Першi перебої в роботi з'явилися вже вранцi 12 грудня, i навiть пiсля кiлькох годин технiчної роботи частина абонентiв залишалася без зв'язку.
          <br><br>
          Розслiдування iнциденту показало, що зловмисники могли залишатися в системах компанiї кiлька мiсяцiв, починаючи з травня 2023 року, що дозволило їм пiдготуватися до атаки. У вiдновленнi послуг брали участь всi технiчнi ресурси «Київстар», i бiльшiсть послуг були вiдновленi протягом двох дiб.
        </p>

        <b class="text-5xl fade-in-up">Технiчнi наслiдки:</b>
        <p class="text-2xl fade-in-up">
          Атака призвела до тимчасових збоїв у роботi кiлькох ключових послуг, зокрема iнтернету та мобiльного зв'язку, що спричинило незручностi для користувачiв. Найдовше тривали вiдновлювальнi роботи у мiжнародному роумiнгу, однак вже до вечора 14 грудня ситуацiя була стабiлiзована.
          <br><br>
          Водночас, незважаючи на масштаби атаки, «Київстар» заявив, що персональнi данi абонентiв не постраждали. Усi системи, в яких зберiгаються цi данi, не були
        </p>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref, watch, onMounted } from 'vue';

const video = ref(null);
const volume = ref(0.5);

onMounted(() => {
  if (video.value) {
    video.value.volume = volume.value;
  }
});

watch(volume, (newVolume) => {
  if (video.value) {
    video.value.volume = newVolume;
  }
});
</script>

<style scoped>
.fade-in {
  animation: fadeIn 2s ease-in;
}

.fade-in-up {
  animation: fadeInUp 1.5s ease-in-out;
}

.volume-slider {
  transition: transform 0.3s ease;
}

.volume-slider:hover {
  transform: scale(1.1);
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>

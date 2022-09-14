<template>
  <aside
    :class="{ 'translate-x-72': !sidebarSiswa }"
    class="flex-none overflow-y-auto fixed z-40 right-0 h-screen bg-white transform duration-300 xl:transform-none w-72 p-4"
  >
    <!-- siswa online -->
    <section class="mb-8">
      <h1 class="mb-4 font-bold text-gray-800">Siswa Online</h1>
      <div
        v-for="student in onlineStudents"
        class="mb-2 bg-background flex items-center space-x-2 p-2 rounded-lg"
      >
        <div
          class="w-10 h-10 grid place-items-center rounded-full font-bol text-white text-xl"
          :style="{ background: student.color }"
        >
          {{ student.initial }}
        </div>
        <h1 class="font-semibold text-gray-800">{{ student.name }}</h1>
      </div>
    </section>
    <!-- siswa offline -->
    <section>
      <h1 class="mb-4 font-bold text-gray-800">Siswa Offline</h1>
      <div
        v-for="student in offlineStudents"
        class="mb-2 bg-background flex items-center space-x-2 p-2 rounded-lg"
      >
        <div
          class="w-10 h-10 grid place-items-center rounded-full font-bol text-white text-xl"
          :style="{ background: student.color }"
        >
          {{ student.initial }}
        </div>
        <h1 class="font-semibold text-gray-800">{{ student.name }}</h1>
      </div>
    </section>
  </aside>
  <div
    v-if="sidebarSiswa"
    @click="store.commit('toggleSidebarSiswa', false)"
    class="bg-gray-400 w-screen xl:w-0 fixed h-screen xl:h-0 z-30 top-0 bg-opacity-50 transform duration-300"
  ></div>
</template>

<script setup>
import { computed, reactive } from 'vue'
import { useStore } from 'vuex'

const store = useStore()

const sidebarSiswa = computed(() => store.state.sidebarSiswa)

const onlineStudents = reactive([
  {
    initial: 'M',
    name: 'Mangprema',
    color: '#ED9A9A',
  },
  {
    initial: 'S',
    name: 'Sugik',
    color: '#83C2FD',
  },
  {
    initial: 'C',
    name: 'Cahya',
    color: '#70DB7B',
  },
  {
    initial: 'D',
    name: 'Dwika',
    color: '#7D7C7C',
  },
  {
    initial: 'B',
    name: 'Bintang',
    color: '#7974DE',
  },
])

const offlineStudents = reactive([
  {
    initial: 'J',
    name: 'Jokowi',
    color: '#F55555',
  },
  {
    initial: 'A',
    name: 'Aden',
    color: '#837CFB',
  },
  {
    initial: 'N',
    name: 'Nopen',
    color: '#9E616A',
  },
  {
    initial: 'M',
    name: 'Megawati',
    color: '#F3A974',
  },
])
</script>

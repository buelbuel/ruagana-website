<script setup lang="ts">
import { Disclosure, DisclosureButton, DisclosurePanel } from '@headlessui/vue'

const navigation = [
  { name: 'Legende', to: '/wiki/legende', level: '0' },
  { name: 'Tagebücher', to: '/wiki/tagebuecher/start', level: '0' },
  { name: 'Jokireka', to: '/wiki/tagebuecher/jokireka', level: '1' },
  { name: 'Lukanies', to: '/wiki/tagebuecher/lukanies', level: '1' },
  { name: 'Vyronahakuzzo', to: '/wiki/tagebuecher/vyronahakuzzo', level: '1' },
  { name: 'Sarbanktschas', to: '/wiki/tagebuecher/sarbanktschas', level: '1' },
  { name: 'Ukaipnaus', to: '/wiki/tagebuecher/ukaipnaus', level: '1' },
  { name: 'Kunchai', to: '/wiki/tagebuecher/kunchai', level: '1' },
  { name: 'Das Spiel', to: '/wiki/das-spiel/start', level: '0' },
  { name: 'Götterwelt', to: '/wiki/das-spiel/goetterwelt', level: '1' },
  { name: 'Arukan', to: '/wiki/das-spiel/arukan', level: '1' },
  { name: 'Der Kalender', to: '/wiki/das-spiel/der-kalender', level: '1' },
  { name: 'Aufgaben, Rätsel', to: '/wiki/das-spiel/aufgaben-raetsel', level: '1' },
  { name: 'Gesinnungspfad', to: '/wiki/das-spiel/gesinnungspfad', level: '1' },
  { name: 'Ruagana', to: '/wiki/das-spiel/ruagana', level: '1' },
  { name: 'Weltkarte', to: '/wiki/das-spiel/weltkarte', level: '1' },
  { name: 'Völker', to: '/wiki/voelker', level: '0' },
  { name: 'Giftnickel', to: '/wiki/giftnickel', level: '1' },
  { name: 'Elder', to: '/wiki/elder', level: '1' },
  { name: 'Wringo', to: '/wiki/wringo', level: '1' },
  { name: 'Dunkelelfen', to: '/wiki/dunkelelfen', level: '1' },
  { name: 'Loprer', to: '/wiki/loprer', level: '1' },
  { name: 'Mureno', to: '/wiki/mureno', level: '1' },
  { name: 'Azkan', to: '/wiki/azkan', level: '1' },
  { name: 'Tureigan', to: '/wiki/tureigan', level: '1' },
  { name: 'Ripakku', to: '/wiki/ripakku', level: '1' },
  { name: 'Warani', to: '/wiki/warani', level: '1' },
  { name: 'Pikor', to: '/wiki/pikor', level: '1' },
  { name: 'Norker', to: '/wiki/norker', level: '1' },
  { name: 'Euer Held', to: '/wiki/euer-held', level: '0' },
  { name: 'Attribute', to: '/wiki/attribute', level: '1' },
  { name: 'Ansehen', to: '/wiki/ansehen', level: '1' },
  { name: 'Befindlichkeiten', to: '/wiki/befindlichkeiten', level: '1' },
  { name: 'Eigenheim', to: '/wiki/eigenheim', level: '1' },
  { name: 'Fähigkeiten', to: '/wiki/faehigkeiten', level: '1' },
  { name: 'Kampffähigkeiten', to: '/wiki/kampffaehigkeiten', level: '1' },
  { name: 'Gefahrsinn', to: '/wiki/gefahrsinn', level: '1' },
  { name: 'Grundlagen', to: '/wiki/grundlagen', level: '1' },
  { name: 'Artefakte', to: '/wiki/artefakte', level: '1' },
  { name: 'Magie', to: '/wiki/magie', level: '1' },
  { name: 'Relikte', to: '/wiki/relikte', level: '1' },
  { name: 'Rüstungssystem', to: '/wiki/ruestungssystem', level: '1' },
  { name: 'Waffensystem', to: '/wiki/waffensystem', level: '1' },
  { name: 'Hauptberufe', to: '/wiki/hauptberufe', level: '0' },
  { name: 'Kämpfer', to: '/wiki/kaempfer', level: '1' },
  { name: 'Assassine', to: '/wiki/assassine', level: '1' },
  { name: 'Schütze', to: '/wiki/schuetze', level: '1' },
  { name: 'Beschwörer', to: '/wiki/beschwoerer', level: '1' },
  { name: 'Illusionist', to: '/wiki/illusionist', level: '1' },
  { name: 'Wandler', to: '/wiki/wandler', level: '1' },
  { name: 'Bannwirker', to: '/wiki/bannwirker', level: '1' },
  { name: 'Hexer', to: '/wiki/hexer', level: '1' },
  { name: 'Ordensbruder', to: '/wiki/ordensbruder', level: '1' },
  { name: 'Nebenberufe', to: '/wiki/nebenberufe', level: '0' },
  { name: 'Alchymist', to: '/wiki/alchymist', level: '1' },
  { name: 'Bergmann', to: '/wiki/bergmann', level: '1' },
  { name: 'Forstwart', to: '/wiki/forstwart', level: '1' },
]
</script>

<template>
  <Disclosure v-slot="{ open }" as="nav">
    <div class="relative">
      <div class="absolute inset-y-0 left-0 flex items-center lg:hidden">
        <!-- Mobile menu button-->
        <DisclosureButton
          class="inline-flex items-center p-2 justify-center rounded-md
          text-gray-400 hover:text-white hover:bg-gray-700
          focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white"
        >
          <span class="sr-only">Open main menu</span>
          <carbon-menu v-if="!open" class="block h-6 w-6" aria-hidden="true" />
          <carbon-close v-else class="block h-6 w-6" aria-hidden="true" />
        </DisclosureButton>
      </div>
      <div class="hidden lg:block">
        <div class="flex flex-col space-y-2">
          <router-link
            v-for="item in navigation"
            :key="item.name"
            class="wiki-nav-btn"
            :class="[item.level == '0' ? 'pl-0' : 'pl-6', $route.path == item.to ? 'text-teal-500' : '' ]"
            :to="item.to"
            :title="item.name"
          >
            {{ item.name }}
          </router-link>
        </div>
      </div>
    </div>

    <DisclosurePanel class="lg:hidden">
      <div class="py-6 space-y-2 flex flex-col">
        <router-link
          v-for="item in navigation"
          :key="item.name"
          :to="item.to"
          :class="[item.level == '0' ? 'pl-0' : 'pl-6']"
          :title="item.name"
        >
          {{ item.name }}
        </router-link>
      </div>
    </DisclosurePanel>
  </Disclosure>
</template>

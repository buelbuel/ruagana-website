<script setup lang="ts">
import { Disclosure, DisclosureButton, DisclosurePanel, Menu, MenuButton, MenuItem, MenuItems } from '@headlessui/vue'

const navigation = [
  { name: 'Ruagana', to: '#' },
  { name: 'Legende', to: '#' },
  { name: 'Tagebücher', to: '#' },
  { name: 'Jokireka', to: '#' },
  { name: 'Lukanies', to: '#' },
  { name: 'Vyronahakuzzo', to: '#' },
  { name: 'Sarbanktschas', to: '#' },
  { name: 'Ukaipnaus', to: '#' },
  { name: 'Kunchai', to: '#' },
  { name: 'Das Spiel', to: '#' },
  { name: 'Götterwelt', to: '#' },
  { name: 'Arukan', to: '#' },
  { name: 'Der Kalender', to: '#' },
  { name: 'Aufgaben, Rätsel', to: '#' },
  { name: 'Gesinnungspfad', to: '#' },
  { name: 'Weltkarte', to: '#' },
  { name: 'Völker', to: '#' },
  { name: 'Giftnickel', to: '#' },
  { name: 'Elder', to: '#' },
  { name: 'Wringo', to: '#' },
  { name: 'Dunkelelfen', to: '#' },
  { name: 'Loprer', to: '#' },
  { name: 'Mureno', to: '#' },
  { name: 'Azkan', to: '#' },
  { name: 'Tureigan', to: '#' },
  { name: 'Ripakku', to: '#' },
  { name: 'Warani', to: '#' },
  { name: 'Pikor', to: '#' },
  { name: 'Norker', to: '#' },
  { name: 'Euer Held', to: '#' },
  { name: 'Attribute', to: '#' },
  { name: 'Ansehen', to: '#' },
  { name: 'Befindlichkeiten', to: '#' },
  { name: 'Eigenheim', to: '#' },
  { name: 'Fähigkeiten', to: '#' },
  { name: 'Kampffähigkeiten', to: '#' },
  { name: 'Gefahrsinn', to: '#' },
  { name: 'Grundlagen', to: '#' },
  { name: 'Artefakte', to: '#' },
  { name: 'Magie', to: '#' },
  { name: 'Relikte', to: '#' },
  { name: 'Rüstungssystem', to: '#' },
  { name: 'Waffensystem', to: '#' },
  { name: 'Hauptberufe', to: '#' },
  { name: 'Kämpfer', to: '#' },
  { name: 'Assassine', to: '#' },
  { name: 'Schütze', to: '#' },
  { name: 'Beschwörer', to: '#' },
  { name: 'Illusionist', to: '#' },
  { name: 'Wandler', to: '#' },
  { name: 'Bannwirker', to: '#' },
  { name: 'Hexer', to: '#' },
  { name: 'Ordensbruder', to: '#' },
  { name: 'Nebenberufe', to: '#' },
  { name: 'Alchymist', to: '#' },
  { name: 'Bergmann', to: '#' },
  { name: 'Forstwart', to: '#' },
]
</script>

<template>
  <Disclosure v-slot="{ open }" as="nav">
    <div class="relative">
      <div class="absolute inset-y-0 left-0 flex items-center sm:hidden">
        <!-- Mobile menu button-->
        <DisclosureButton class="inline-flex items-center justify-center rounded-md text-gray-400 hover:text-white hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white">
          <span class="sr-only">Open main menu</span>
          <carbon-menu v-if="!open" class="block h-6 w-6" aria-hidden="true" />
          <carbon-close v-else class="block h-6 w-6" aria-hidden="true" />
        </DisclosureButton>
      </div>
      <div class="hidden sm:block">
        <div class="flex flex-col space-y-2">
          <router-link v-for="item in navigation" :key="item.name" class="wiki-nav-btn" :to="item.to" :title="item.name">
            {{ item.name }}
          </router-link>
        </div>
      </div>
    </div>

    <DisclosurePanel class="sm:hidden">
      <div class="py-6 space-y-2 flex flex-col">
        <router-link v-for="item in navigation" :key="item.name" :to="item.to">
          {{ item.name }}
        </router-link>
      </div>
    </DisclosurePanel>
  </Disclosure>
</template>

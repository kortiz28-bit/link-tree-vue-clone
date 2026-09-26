<script setup>
import { ref } from 'vue'
import LinkCard from '@/components/LinkCard.vue'

const profile = ref({
  name: 'Khrystal Ortiz',
  slogan: 'IT & Cybersecurity Student',
  avatar: 
  'https://api.dicebear.com/10.x/lorelei/svg?beardVariant=&earringsVariant=&eyebrowsVariant=variant07&mouthVariant=happy01&headVariant=variant04&hairAccessoriesVariant=&hairVariant=variant35&noseVariant=variant02&eyesVariant=variant23&frecklesColor=&seed=Felix',
  links: [
    {
      id: 1,
      title: 'GitHub',
      url: 'https://github.com/kortiz28-bit',
      icon: 'code',
      description: 'Check out my projects',
    },
    {
      id: 2,
      title: 'South Texas College',
      url: 'https://www.southtexascollege.edu/',
      icon: 'cap',
      description: 'Visit South Texas College',
    },
    {
      id: 3,
      title: 'Expense Splitter',
      url: 'https://expense-splitter-vue.kortiz28.workers.dev',
      icon: 'dollar',
      description: 'Split expenses between friends',
    },
  ]
})
</script>

<template>
  <main class="flex min-h-screen flex-col items-center px-4 py-8">
    <!-- Profile Header -->
     <div class="mb-8 flex flex-col items-center text-center">
       <div
         class="mb-4 h-24 w-24 overflow-hidden rounded-full border-4 border-blue-400 shadow-lg shadow-blue-500/20">
       
         <img
           :src="profile.avatar"
           :alt="profile.name"
           class="h-full w-full object-cover"
         />
      </div>
      <h1 class="mb-2 font-display text-2xl font-bold text-white sm:text-3xl">
        {{profile.name}}
      </h1>
      <p class="max-w-xs text-gray-300 sm:text-lg">{{profile.slogan}}</p>
    </div>

    <!-- Link List-->
    <div class="flex w-full max-w-md flex-col gap-4">
      <LinkCard 
        v-for="link in profile.links"
        :key="link.id"
        :title="link.title"
        :url="link.url"
        :description="link.description"
        :icon="link.icon"
      />
    </div>

    <!-- Navigate to Info -->
    <RouterLink 
      to="/info" 
      class="mt-8 text-sm text-gray-400 underline-offset-4 transition-colors duration-200 hover:text-blue-400 hover:underline"
    > About me ➡ </Routerlink>
  </main>
</template>

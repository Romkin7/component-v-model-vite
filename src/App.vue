<script setup lang="ts">
import { ref } from 'vue'
import Card from '@/components/Card/card-element.vue'
import CardHeader from '@/components/Card/card-header.vue'
import CardStats from '@/components/Card/card-stats.vue'
import EditForm from '@/components/Form/edit-form.vue'

//starter data
const data = {
  name: 'Flora',
  level: 100,
  job: 'sorcerer',
  race: 'human',
  bio: 'Flora is an Exclusive Legendary Wild Hero from the Fire element, known for her powerful single-target damage and her pet dragon. With high attack and enlightenment stats, Flora excels when paired with multi-hitting Wild allies, making her the queen of precise, devastating strikes. Ideal companions include the Epic Hero Tonalnan and Legendaries such as Felicity and Errich, who complement her abilities perfectly. To maximize Flora’s potential, it is crucial to time her skills effectively, ensuring that her Ultimate skill is used first, followed by the ultimates of her Wild allies. This strategy allows her dragon to unleash a torrent of incredibly powerful damage on enemies, securing Flora’s place as a top-tier hero in any Wild team. Her unique combination of strength and synergy makes her an indispensable asset for players aiming to dominate their foes with fiery precision.',
}

//data
const name = ref(data.name)
const level = ref(data.level)
const job = ref(data.job)
const race = ref(data.race)
const bio = ref(data.bio)

//respawn function
const respawn = () => {
  name.value = data.name
  level.value = data.level
  job.value = data.job
  race.value = data.race
  bio.value = data.bio
}
</script>

<template>
  <main>
    <section>
      <Card v-bind:respawn="respawn">
        <CardHeader :name="name" :level="level" :job="job" />
        <CardStats :race="race" :bio="bio" />
      </Card>
    </section>
    <section>
      <EditForm
        v-model:name.trim.capitalize_first_letter="name"
        v-model:level.number="level"
        v-model:job="job"
        v-model:race="race"
        v-model:bio="bio"
      />
    </section>
  </main>
</template>

<style scoped>
main {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 50px;
  padding: 50px 20px;
}
section {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>

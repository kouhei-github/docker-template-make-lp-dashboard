<template>
  <div>
    <h1>{{ title }}</h1>
    <ul>
      <li v-for="u in data.users" :key="u.id">{{ u.id }} {{ u.name }}</li>
    </ul>
  </div>
</template>s

<script lang="ts">
import { defineComponent, reactive, ref } from '@nuxtjs/composition-api'

export default defineComponent({
  setup() {
    const data = reactive({
      users: [
        { id: 1, name: '加藤かな' },
        { id: 2, name: '田中紘一' },
        { id: 3, name: '山田太郎' },
      ],
    })
    const title = ref("タイトル")

    setTimeout(() => {
      data.users.push({ id: 4, name: '新藤誠' })
      title.value = "タイトルが変更できること"
    }, 1000);

    return {
      data,
      title,
    }
  },
})
</script>


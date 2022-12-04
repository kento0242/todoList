<script setup lang="ts">
// import axios from "axios"

const ENDPOINT =
  'https://hbsfw9usr6.execute-api.ap-northeast-1.amazonaws.com/TestStage/test-resource'
const getAPITest = (): void => {
  fetch(ENDPOINT, {})
    .then((r) => r.json())
    .then((json) => {
      console.log(json)
    })
}
interface bodyType {
  id: string
  sort_key: string
  name: string
}
const body: bodyType = {
  id: '003',
  sort_key: '003',
  name: 'Saburo Tanaka',
}

const putAPITest = (): void => {
  fetch(ENDPOINT, {
    method: 'PUT',
    body: JSON.stringify(body),
  })
    .then((r) => r.json())
    .then((json) => {
      console.log(json)
    })
}
</script>

<template>
  <div>
    <button @click="getAPITest">getAPI実行</button>
    <button @click="putAPITest">putAPI実行</button>
  </div>
</template>

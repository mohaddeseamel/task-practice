

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
    <h1 class="green">{{ prp }}</h1>
    <h1>{{ tavak }}</h1>
    <button @click="testAlert">test</button>
    <h3>
      You’ve successfully created a project with
      <a href="https://vitejs.dev/" target="_blank" rel="noopener">Vite</a> +
      <a href="https://vuejs.org/" target="_blank" rel="noopener">Vue 3</a>.
    </h3>
    <button @click="changeUser()">ChangeUserName</button>
    <h1>{{ userName }}</h1>
  </div>
</template>
<script >
import { ref, watch } from 'vue'
export default {
  props: {
    tavak: { default: null },
    msg: { default: null },
    userName: { type: String }
  },
  emits: ['tempo', 'changeData'],
  setup(props, { emit }) {
    // console.log(emit)
    // console.log('props in hello world')
    // console.log(props)
    console.log('tavaktavaktavaktavaktavak', props.tavak)
    let item = ref(null)
    const temp = ref('hossein')
    const prp = ref(null)
    prp.value = props.tavak
    async function testAlert() {}

    const changeUser = () => {
      item.value = props.userName
      emit('changeData')
    }

    // watch(item, (oldValue, newValue) => {
    //   console.log('old value', oldValue)
    //   console.log('new value', newValue)
    //   changeUser()
    // })

    return { testAlert, temp, prp, changeUser, item }
  }
}
</script>
<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>

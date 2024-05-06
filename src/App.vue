

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
    <button style="margin-right: 10px" @click="clickf">click number</button>
    <div class="wrapper">
      <HelloWorld
        ref="testg"
        :userName="userName"
        :tavak="data"
        msg="You did it!"
        @changeData="showData()"
      />
    </div>
  </header>

  <main>
    <TheWelcome />
  </main>
</template>
<script >
import { ref } from 'vue'
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
export default {
  components: {
    TheWelcome,
    HelloWorld
  },

  setup(props, { emit }) {
    console.log('app.js')
    console.log(props, emit)
    let userName = ref('mohaddese')
    let data = ref(2503)
    function clickf() {
      return (data.value = 2)
    }
    const showData = () => {
      console.log('cccccccccccccccccccccccccccccccccccccccc')
      return (userName.value = 'moha Amel')
    }
    return {
      data,
      clickf,
      userName,
      showData
    }
  }
}
</script>
<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>

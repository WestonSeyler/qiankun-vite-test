<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view />
  </div>
  <div>

    <div id="name">

    </div>
    <div>
      <n-popover trigger="hover"  :to="element">
        <template #trigger>
          <n-button>悬浮111</n-button>
        </template>
        <span>或许不想知道你的花园长得咋样</span>
      </n-popover>

      <n-dropdown trigger="click" :options="options" @select="handleSelect" :to="element">
        <n-button>找个地方休息</n-button>
      </n-dropdown>
    </div>
    <div style="width:300px" ref="popover">
      <n-select v-model:value="value" to="__disabled__" :options="options" />
    </div>


    <!-- <el-popover placement=" top-start" title="Title" :width="200" trigger="click"
      content="this is content, this is content, this is content" :teleported="true">
      <template #reference>
        <el-button>Hover to activate</el-button>
      </template>
      </el-popover> -->

    <!--
    <a-popover title="Title" trigger="click" :getPopupContainer='triggerNodeFunction'>
      <template #content>
        <p>Content</p>
        <p>Content</p>
      </template>
      <a-button type="primary">Hover me</a-button>
    </a-popover> -->


    <!-- <a-tooltip :getPopupContainer="(triggerNode) => triggerNode" trigger="click">
      <template #title>prompt text</template>
      Tooltip will show when mouse enter.
    </a-tooltip> -->

    <br>
  </div>
</template>
<script >
import { defineComponent, onMounted, ref } from 'vue'

export default defineComponent({
  setup() {
    // const message = useMessage()
    // const triggerNodeFunction = (node) => {
    //   return node
    // }
    const popover = ref(null)
    const element = ref(null)
    const value = ref(null)
    onMounted(() => {
      // console.log(popover.value, '11111')
      // popover.value-
      element.value = popover.value
    })
    return {
      value,
      // triggerNodeFunction,
      popover,
      element,
      value: ref(null),
      options: [
        {
          label: "Everybody's Got Something to Hide Except Me and My Monkey",
          value: 'song0',
          disabled: true
        },
        {
          label: 'Drive My Car',
          value: 'song1'
        },
        {
          label: 'Norwegian Wood',
          value: 'song2'
        },
        {
          label: "You Won't See",
          value: 'song3',
          disabled: true
        },
        {
          label: 'Nowhere Man',
          value: 'song4'
        },
        {
          label: 'Think For Yourself',
          value: 'song5'
        },
        {
          label: 'The Word',
          value: 'song6'
        },
        {
          label: 'Michelle',
          value: 'song7',
          disabled: true
        },
        {
          label: 'What goes on',
          value: 'song8'
        },
        {
          label: 'Girl',
          value: 'song9'
        },
        {
          label: "I'm looking through you",
          value: 'song10'
        },
        {
          label: 'In My Life',
          value: 'song11'
        },
        {
          label: 'Wait',
          value: 'song12'
        }
      ],
      handleSelect(key) {
        // console.log(key)
      }
    }
  }
})
</script>
<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>

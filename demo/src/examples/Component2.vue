<template>
  <div class="q-ma-md row justify-evenly" style="max-width: 700px; width: 100%;">

    <div class="q-ma-md row justify-center items-center full-width">
      <q-toggle v-model="hover" label="Toggle Hover" />
      <q-toggle v-model="active" label="Toggle Transitions" />
    </div>

    <div class="description text-center rounded-borders">
      <q-flashcard :no-hover="hover" :style="style">
        <q-flashcard-section transition="nudge-out" :active="active">
          <img :src="getImage(0)" width=300 height=200>
        </q-flashcard-section>
        <q-flashcard-section transition="slide-up-in" class="fit" :active="active">
          <div style="margin-top: 50%; opacity:0.65">
              <q-toolbar class="bg-white text-black q-my-md shadow-2">

                <q-space></q-space>

                <q-btn-toggle
                  v-model="model"
                  flat stretch
                  toggle-color="yellow"
                  :options="[
                    {label: 'Task#1', value: 'one'},
                    {label: 'Task#2', value: 'two'},
                    {label: 'Task#3', value: 'three'}
                  ]"
                ></q-btn-toggle>
              </q-toolbar>
            </div>
        </q-flashcard-section>
      </q-flashcard>
      <div class="text-h5 q-pt-sm">Component Demo #2</div>
    </div>

  </div>
</template>

<script>
export default {
  data () {
    return {
      model: false,
      hover: false,
      active: false
    }
  },

  computed: {
    style () {
      return {
        width: '320px',
        height: '220px',
        backgroundImage: `url('https://raw.githubusercontent.com/quasarframework/quasar-ui-qflashcard/dev/demo/src/statics/bgimg.jpg')`, // eslint-disable-line
        padding: '10px',
        border: '10px solid #fff',
        textAlign: 'center',
        boxShadow: '1px 1px 2px #e6e6e6'
      }
    }
  },

  methods: {
    getImage (index) {
      if (index % 2) {
        return 'https://raw.githubusercontent.com/quasarframework/quasar-ui-qflashcard/dev/demo/src/statics/1.jpg'
      }
      return 'https://raw.githubusercontent.com/quasarframework/quasar-ui-qflashcard/dev/demo/src/statics/2.jpg'
    }
  }
}
</script>

<style lang="sass" scoped>
.description
  padding: 10px
  background-color: black
  color: white
  box-shadow: 1px 1px 2px #e6e6e6

.my-header
  width: 100%
  top: 0
  height: 45px
  color: white
  background-color: rgba(0,0,0,0.8)
  text-transform: uppercase
  text-align: center
  font-size: 17px
  margin: 20px 0 0 0
  padding: 10px

.my-text
  width: 100%
  top: 0
  height: 80px
  color: white
  text-align: center
  font-size: 12px
  margin: 60px 0 0 0
  padding: 20px
  line-height: normal
  font-family: Georgia, serif
  font-style: italic

.my-button-container
  width: 100%

.my-button
  text-decoration: none
  text-transform: uppercase
  margin: 0 0 20px 0
  text-align: center
  padding: 7px 14px
  background-color: #000
  color: #fff
  text-transform: uppercase
  box-shadow: 0 0 1px #000
  transition-delay: 0.2s

.my-button:hover
  box-shadow: 0 0 5px #000
</style>

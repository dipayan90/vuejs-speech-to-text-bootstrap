<template>
<div>
  <b-card 
              header="Transcript" 
              bg-variant="light"
              class="text-center"
              >
              <b-card-text>
                <span v-bind:key="sentence" v-for="sentence in sentences">
                  {{sentence}}. 
                </span>
                <span>{{runtimeTranscription}}</span>
              </b-card-text>
              <div slot="footer" class="row">
                <div class="col">
                  <b-button pill @click.stop="toggle ? endSpeechRecognition() : startSpeechRecognition()">
                    <v-icon>{{toggle ? 'mic_off' : 'mic'}}</v-icon>
                  </b-button>
                </div>
              </div>
  </b-card>
</div>
  
</template>

<script>
export default {
  name: 'Stt',
   props: {
    lang: {
      type: String,
      default: 'en-US'
    },
    text: {
      type: [String, null],
      required: true
    }
  },
  data () {
    return {
      error: false,
      speaking: false,
      toggle: false,
      runtimeTranscription: '',
      sentences: []
    }
  },
  methods: {
    checkCompatibility () {
      if (!recognition) {
        this.error = 'Speech Recognition is not available on this browser. Please use Chrome or Firefox'
      }
    },
    endSpeechRecognition () {
      recognition.stop()
      this.toggle = false
      this.$emit('speechend', {
        sentences: this.sentences,
        text: this.sentences.join('. ')
      })
    },
    startSpeechRecognition () {
      if (!recognition) {
        this.error = 'Speech Recognition is not available on this browser. Please use Chrome or Firefox'
        return false
      }
      this.toggle = true
      recognition.lang = this.lang
      recognition.interimResults = true

      recognition.addEventListener('speechstart', () => {
        this.speaking = true
      })

      recognition.addEventListener('speechend', () => {
        this.speaking = false
      })

      recognition.addEventListener('result', event => {
        const text = Array.from(event.results).map(result => result[0]).map(result => result.transcript).join('')
        this.runtimeTranscription = text
      })

      recognition.addEventListener('end', () => {
        if (this.runtimeTranscription !== '') {
          this.sentences.push(this.capitalizeFirstLetter(this.runtimeTranscription))
          this.$emit('update:text', `${this.text}${this.sentences.slice(-1)[0]}. `)
        }
        this.runtimeTranscription = ''
        recognition.stop()
        if (this.toggle) {
          // keep it going.
          recognition.start()
        }
      })
      recognition.start()
    },
    capitalizeFirstLetter (string) {
      return string.charAt(0).toUpperCase() + string.slice(1)
    }
  },
  mounted () {
    this.checkCompatibility()
  }
}

let SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition
let recognition = SpeechRecognition? new SpeechRecognition() : false

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>

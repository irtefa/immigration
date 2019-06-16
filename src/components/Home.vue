<template>
  <div>
    <h1>{{ question }}</h1>
    <div v-if="isMobile()">
      <div id="wrapper"> Tap this 
      <div id="next-btn" v-on:click="next">
        Button
      </div>
      to see the next question.
      </div>
    </div>
    <div v-else>    
      <p>Press any key for the next question</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  props: {
    question: String,
  },

  data: function() {
    return {
      questions: [
        {title: 'When was the last time you entered the United States?'},
        {title: 'When was the first time you entered the United States?'},
        {title: "What's the name of your employer?"},
        {title: "What's your day to day responsibility at your job?"},
        {title: "What's your full name?"},
        {title: "What's your father's full name?"},
        {title: "What's your mother's full name?"},
        {title: "What's the last physical address where you stayed at?"},
        {title: "Are you married?"},
        {title: "When did you join your current company?"},
        {title: "Where did you live before your current physical address?"},
      ],
      counter: 0,
    }
  },

  created: function() {
    window.addEventListener('keyup', this.next)
    this.questions = this.shuffle(this.questions)
  },

  methods: {
    next: function() {
      this.question = this.questions[this.counter].title  
      this.counter += 1
      if (this.counter === this.questions.length) {
        this.counter = 0
      }
    },

    onPan: function() {
      this.next()
    },

    shuffle: function(array) {
      for (let i = array.length - 1; i > 0; i--) {
        let j = Math.floor(Math.random() * (i + 1)); // random index from 0 to i
        [array[i], array[j]] = [array[j], array[i]]; // swap elements
      }
      return array
    },
    isMobile: function() {
      if(/Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent)) {
        return true
      } else {
        return false
      }
    },
  }
}
</script>
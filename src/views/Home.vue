<template>
  <div class="progress-bars-container">
    <div id="currentBar">
      <span>{{counts.current}}</span>
    </div>
    <div id="dailyBar">
      <span>{{counts.daily}}</span>
    </div>
    <div id="weeklyBar">
      <span>{{counts.weekly}}</span>
    </div>
    <div id="wholeBar">
      <span>{{counts.whole}}</span>
    </div>
  </div>
</template>

<script>
export default{
  data(){
    return{
      counts: {current:10, daily: 80, weekly: 200, whole: 1250},

      goals: {current:20, daily: 100, weekly: 300, whole: 2500},
    }
  },
  methods:{
    progressAnimation(){
      var ProgressBar = require('progressbar.js');

      
      // ---------------------------
      var bar = new ProgressBar.SemiCircle(document.getElementById('currentBar'), {
        strokeWidth: 5.5,trailColor: '#eee',easing: 'easeInOut',svgStyle: null,text: {value: '',alignToBottom: false},
        duration: 1500,
        from: {color: '#EB6440'},
        to: {color: '#EB6440'},
        // Set default step function for all animate calls
        step: (state, bar) => {
          bar.path.setAttribute('stroke', state.color);
          var value = Math.round(bar.value() * 100);
          if (value === 0) {
            bar.setText('');
          } else {
            // bar.setText(this.counts.current);
          }
        }
      });
      bar.text.style.fontFamily = '"Raleway", Helvetica, sans-serif';
      bar.text.style.fontSize = '25px';

      bar.animate(this.progress.current);  // Number from 0.0 to 1.0

      // ---------------------------
      bar = new ProgressBar.SemiCircle(document.getElementById('dailyBar'), {
        strokeWidth: 5.5,trailColor: '#eee',easing: 'easeInOut',svgStyle: null,text: {value: '',alignToBottom: false},
        duration: 1500,
        from: {color: '#EB6440'},
        to: {color: '#EB6440'},
        // Set default step function for all animate calls
        step: (state, bar) => {
          bar.path.setAttribute('stroke', state.color);
          var value = Math.round(bar.value() * 100);
          if (value === 0) {
            bar.setText('');
          } else {
            // bar.setText(this.counts.daily);
          }
          bar.text.style.color = state.color;
        }
      });

      bar.animate(this.progress.daily);  // Number from 0.0 to 1.0

      // ---------------------------
      bar = new ProgressBar.SemiCircle(document.getElementById('weeklyBar'), {
        strokeWidth: 5.5,trailColor: '#eee',easing: 'easeInOut',svgStyle: null,text: {value: '',alignToBottom: false},
        duration: 1500,
        from: {color: '#EB6440'},
        to: {color: '#EB6440'},
        // Set default step function for all animate calls
        step: (state, bar) => {
          bar.path.setAttribute('stroke', state.color);
          var value = Math.round(bar.value() * 100);
          if (value === 0) {
            bar.setText('');
          } else {
            // bar.setText(this.counts.whole);
          }
        }
      });

      bar.animate(this.progress.weekly);  // Number from 0.0 to 1.0

      // ---------------------------
      bar = new ProgressBar.SemiCircle(document.getElementById('wholeBar'), {
        strokeWidth: 5.5,trailColor: '#eee',easing: 'easeInOut',svgStyle: null,text: {value: '',alignToBottom: false},
        duration: 1500,
        from: {color: '#EB6440'},
        to: {color: '#EB6440'},
        // Set default step function for all animate calls
        step: (state, bar) => {
          bar.path.setAttribute('stroke', state.color);
          var value = Math.round(bar.value() * 100);
          if (value === 0) {
            bar.setText('');
          } else {
            // bar.setText(this.counts.whole);
          }
          bar.text.style.color = state.color;
        }
      });
      
      // bar.text.style.transform = 'translateX(50%)';


      

      bar.animate(this.progress.whole);  // Number from 0.0 to 1.0
    },
  },
  mounted(){
    this.progressAnimation()
  },
  computed:{
    progress(){
      let obj = {
        current: this.counts.current/ this.goals.current,
        daily:  this.counts.daily/ this.goals.daily,
        weekly: this.counts.weekly/ this.goals.weekly,
        whole: this.counts.whole/ this.goals.whole,
      }

      for(let i in obj){
        if(obj[i] >= 1){
          obj[i] = 1
        }
      }

      return obj
    },
  },
}
</script>

<style>

.progress-bars-container{
  margin-top: 15px;
  display: flex;
  width: 100%;
  justify-content: space-between;
  /* background-color: crimson; */
  /* font-size:10px; */
  /* height: 100px; */
}

.progress-bars-container div{
  /* margin: 20px; */
  width: 20%;
  /* margin-left: 20px; */
  height: 30px;
}

.progress-bars-container div span{
  position: absolute;
  top: 100%;
  left: 50%;
  transform: translate(-50%,-25%);
  display: inline-block;
  /* margin-bottom: 100px; */
  text-align: center;
  color:#BBE1FA;
  font-size: 20px;
}
</style>
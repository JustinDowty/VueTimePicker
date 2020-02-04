<template>
    <div class="vue-tp-wrapper" style="position: relative">
        <input type="text" v-on:click="togglePicker" id="vue-tp-time-display" v-bind="userVar" v-model="time" readonly="readonly" />
        <div v-if="showPicker" id="vue-tp-time">
            <div class="vue-tp-row">
                <div class="chevron-btn" v-on:click="incrementHours" >
                    <svg aria-hidden="true" focusable="false" data-prefix="far" data-icon="chevron-up" class="svg-inline--fa fa-chevron-up fa-w-14" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path fill="#333333" d="M6.101 359.293L25.9 379.092c4.686 4.686 12.284 4.686 16.971 0L224 198.393l181.13 180.698c4.686 4.686 12.284 4.686 16.971 0l19.799-19.799c4.686-4.686 4.686-12.284 0-16.971L232.485 132.908c-4.686-4.686-12.284-4.686-16.971 0L6.101 342.322c-4.687 4.687-4.687 12.285 0 16.971z"></path></svg>
                </div>
                <div class="chevron-btn" v-on:click="incrementMinutes">
                    <svg aria-hidden="true" focusable="false" data-prefix="far" data-icon="chevron-up" class="svg-inline--fa fa-chevron-up fa-w-14" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path fill="#333333" d="M6.101 359.293L25.9 379.092c4.686 4.686 12.284 4.686 16.971 0L224 198.393l181.13 180.698c4.686 4.686 12.284 4.686 16.971 0l19.799-19.799c4.686-4.686 4.686-12.284 0-16.971L232.485 132.908c-4.686-4.686-12.284-4.686-16.971 0L6.101 342.322c-4.687 4.687-4.687 12.285 0 16.971z"></path></svg>
                </div>
                <div class="chevron-btn"  v-on:click="amPmButton">
                    <svg aria-hidden="true" focusable="false" data-prefix="far" data-icon="chevron-up" class="svg-inline--fa fa-chevron-up fa-w-14" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path fill="#333333" d="M6.101 359.293L25.9 379.092c4.686 4.686 12.284 4.686 16.971 0L224 198.393l181.13 180.698c4.686 4.686 12.284 4.686 16.971 0l19.799-19.799c4.686-4.686 4.686-12.284 0-16.971L232.485 132.908c-4.686-4.686-12.284-4.686-16.971 0L6.101 342.322c-4.687 4.687-4.687 12.285 0 16.971z"></path></svg>
                </div>
            </div>
            <div class="vue-tp-row">
                <span class="vue-tp-input">
                    <input type="text" value="12" v-model="hours" @input="validateHours"/>
                </span>
                <span class="vue-tp-spacer">:</span>
                <span class="vue-tp-input">
                    <input type="text" value="00" v-model="minutes" @input="validateMinutes"/>
                </span>
                <span class="vue-tp-spacer">&nbsp;</span>
                <span class="vue-tp-input" style="padding: 10px 5px;">
                    <select v-model="amPm">
                        <option value="PM">PM</option>
                        <option value="AM">AM</option>
                    </select>
                </span>
            </div>
            <div class="vue-tp-row">
                <div class="chevron-btn" v-on:click="decrementHours">
                    <svg aria-hidden="true" focusable="false" data-prefix="far" data-icon="chevron-down" class="svg-inline--fa fa-chevron-down fa-w-14" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path fill="#333333" d="M441.9 167.3l-19.8-19.8c-4.7-4.7-12.3-4.7-17 0L224 328.2 42.9 147.5c-4.7-4.7-12.3-4.7-17 0L6.1 167.3c-4.7 4.7-4.7 12.3 0 17l209.4 209.4c4.7 4.7 12.3 4.7 17 0l209.4-209.4c4.7-4.7 4.7-12.3 0-17z"></path></svg>
                </div>
                <div class="chevron-btn" v-on:click="decrementMinutes">
                    <svg aria-hidden="true" focusable="false" data-prefix="far" data-icon="chevron-down" class="svg-inline--fa fa-chevron-down fa-w-14" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path fill="#333333" d="M441.9 167.3l-19.8-19.8c-4.7-4.7-12.3-4.7-17 0L224 328.2 42.9 147.5c-4.7-4.7-12.3-4.7-17 0L6.1 167.3c-4.7 4.7-4.7 12.3 0 17l209.4 209.4c4.7 4.7 12.3 4.7 17 0l209.4-209.4c4.7-4.7 4.7-12.3 0-17z"></path></svg>
                </div>
                <div class="chevron-btn"  v-on:click="amPmButton">
                    <svg aria-hidden="true" focusable="false" data-prefix="far" data-icon="chevron-down" class="svg-inline--fa fa-chevron-down fa-w-14" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path fill="#333333" d="M441.9 167.3l-19.8-19.8c-4.7-4.7-12.3-4.7-17 0L224 328.2 42.9 147.5c-4.7-4.7-12.3-4.7-17 0L6.1 167.3c-4.7 4.7-4.7 12.3 0 17l209.4 209.4c4.7 4.7 12.3 4.7 17 0l209.4-209.4c4.7-4.7 4.7-12.3 0-17z"></path></svg>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'TimePicker',
  props: ['userVar'],
  data() {
      return {
          time : "12:00PM",
          showPicker : false,
          hours : "12",
          minutes : "00",
          amPm : "PM"
      }
  },
  created() {
    document.addEventListener('click', (event) => {
      if(document.getElementById('vue-tp-time') 
        && !document.getElementById('vue-tp-time').contains(event.target)
        && !document.getElementById('vue-tp-time-display').contains(event.target)) {
          this.update();
          this.showPicker = false;
      }
    });
  },
  methods: {
      update() {
          this.hours = this.padNumber(this.hours);
          this.minutes = this.padNumber(this.minutes);
          this.time = this.hours + ":" + this.minutes + this.amPm.toLowerCase();
          let timeString = this.hours+":"+this.minutes+":"+"00 "+this.amPm;
          this.$emit("input", timeString);
      },
      togglePicker() {
          this.showPicker = !this.showPicker;
          if(!this.showPicker) {
              this.update();
          }
      },
      incrementHours() {
          let h = parseInt(this.hours);
          h = (h % 12);
          h++;
          if(h < 10) {
              this.hours = "0" + h;
          } else {
              this.hours = h;
          }
          this.update();
      },
      incrementMinutes() {
          let m = parseInt(this.minutes);
          m+=15;
          m = (m % 60);
          if(m < 10) {
              this.minutes = "0" + m;
              this.incrementHours();
          } else {
              this.minutes = m;
          }
          this.update();
      },
      decrementHours() {
          let h = parseInt(this.hours);
          h--;
          h = h==0 ? 12 : h;
          if(h < 10) {
              this.hours = "0" + h;
          } else {
              this.hours = h;
          }
          this.update();
      },
      decrementMinutes() {
          let m = parseInt(this.minutes);
          m-=15;
          if(m < 0) {
              m = 45;
          }
          if(m < 10) {
              this.minutes = "0" + m;
              this.decrementHours();
          } else {
              this.minutes = m;
          }
          this.update();
      },
      amPmButton() {
          this.amPm = this.amPm == "PM" ? "AM" : "PM";
          this.update();
      },
      padNumber(numString) {
          if(numString.length == 0) {
              numString = "00";
          }else if(numString.length < 2) {
              numString = "0" + numString;
          }
          return numString;
      },
      validateHours() {
          this.hours = this.hours.replace(/[^0-9]+/g, '');
      },
      validateMinutes() {
          this.minutes = this.minutes.replace(/[^0-9]+/g, '');
      }
  }
}
</script>

<style src="./VueTpStyle.css"></style>
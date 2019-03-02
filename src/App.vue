<template>
    <div id="master">
        <p class="woche">Kalenderwoche 31</p>
        <div id="container" @click="openModule">
            <app-weekslot class="week-slot"></app-weekslot>
            <app-timeslot v-for="slot in slots" :subjects="subjects[slot-1]"></app-timeslot>
        </div>
    </div>
</template>

<script>
  import Timeslot from './components/Timeslot';
  import Weekslot from './components/Weekslot';
  export default {
      data(){
          return {
              slots: 5,
              subjects: [
                  [
                      { name: '', type: ''},{ name: '', type: ''},{ name: '', type: ''},{ name: 'Web-Engineering', type: 'Vorlesung'},{ name: '', type: ''},
                  ],
                  [
                      { name: '', type: ''},{ name: 'Verteilte-Systeme', type: 'Vorlesung'},{ name: 'Computergrafik', type: 'Vorlesung'},{ name: 'Web-Engineering', type: 'Übung'},{ name: '', type: ''},
                  ],
                  [
                      { name: '', type: ''},{ name: 'Verteilte-Systeme', type: 'Übung'},{ name: 'Computergrafik', type: 'Übung'},{ name: 'Web-Engineering', type: 'Übung'},{ name: 'Medientechnologien', type: 'Vorlesung'},
                  ],
                  [
                      { name: '', type: ''},{ name: '', type: ''},{ name: '', type: ''},{ name: 'Software-Engineering', type: 'Vorlesung'},{ name: 'Medientechnologien', type: 'Übung'},
                  ],
                  [
                      { name: '', type: ''},{ name: '', type: ''},{ name: '', type: ''},{ name: 'Software-Engineering', type: 'Übung'},{ name: 'Medientechnologien', type: 'Übung'},
                  ],
              ],
          };
      },
      components: {
          appTimeslot: Timeslot,
          appWeekslot: Weekslot,
      },
      methods: {
        openModule(event){
            let module = event.target;
            if(module.className === 'name' || module.className === 'type'){
                module = module.parentElement;
            }
            if(module.className === 'day' || module.className === 'week' || module.id === 'container'){
                return;
            }
            let timeslot = module.parentElement;
            module.style.width = module.style.width === '100%' ? '0%' : '100%';
            timeslot.style.height = timeslot.style.height === '100%' ? '0%' : '100%';
        }
      },
  };
</script>

<style scoped>
    #master {
        margin: 4em auto;
        background-color: #f0f0f0;
        box-shadow: 0em 0em 2em #bebebe;
        width: 85em;
        height: 50em;
    }

    #container {
        display: flex;
        margin: 0 auto;
        width: 80em;
        height: 40em;
        flex-direction: column;
        flex-wrap: wrap;
    }
    .woche {
        font-family: Roboto;
        text-align: center;
        padding-top: 3em;
    }
</style>

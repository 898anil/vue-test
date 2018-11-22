<template>
  <div>
    <button v-on:click="openDialog()">Create Event</button>
    <table class="calender-table">
      <thead>
        <tr>
          <th>Time</th>
          <th>Events</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="hour in hours">
          <td>{{hour}}</td>
          <td>
            <div v-for="event in getEvents(hour)">
              {{event.name}}
            </div>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
export default {
  name: 'HelloWorld',
  data() {
    var hoursCount = 24;
    var hours = [];
    for(var i=0;i<=hoursCount;i++){
      hours.push(i)
    }
    return {
      hours:hours,
      eventsData:{}
    }
  },
  methods:{
    openDialog:function(){
      console.log("create new");
    },
    getEvents(hour){
      return this.eventsData[hour] || [{name:"abcd-"+hour}];
    }
  }
}

</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .calender-table td,.calender-table th,
  { 
    min-width: 100px;
    padding:10px;
  }
</style>

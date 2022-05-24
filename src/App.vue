<template>
  <div>{{ greet }} {{ name }}</div>
  <div v-html="channel"></div>
  <div v-html="hack"></div>
  <h2 v-bind:id="headingId">Heading</h2>
  <button v-bind:disabled="isDisabled">bind</button>
  <h2 class="underline">underline text</h2>
  <h2 v-bind:class="status">Status</h2>
  <h2 v-bind:class="isPromoted && 'promoted'">promoted movie</h2>
  <h2 v-bind:class="isSoldOut ? 'sold-out':'new'">soldout ? movie</h2>
  <h2 v-bind:class="['new','promoted']">newly promoted movie</h2>
  <h2 v-bind:class="[isPromoted && 'promoted',isSoldOut ? 'sold-out':'new']">Array conditional  movie</h2>
  <h2 v-bind:class="{
    promoted:isPromoted,
    new: !isSoldOut,
    'sold-out':isSoldOut

  }">Object con movie</h2>

  <h2 v-bind:style="{
   color: highlightColor,
   fontSize:headerSize ,
   padding:'20px'
  }">inline style</h2>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      greet: 'hello',
      name: 'Brano',
      channel: '<b>codevlotion</b>',
      hack: `<a href="#" onClick="alert('hacked')">Click</a>`,
      headingId: 'heading',
      isDisabled: false,
      status: 'danger',
      isPromoted: true,
      isSoldOut:true,
      highlightColor:'orange',
      headerSize:'50px',
      headerStyleObject:{
        color:"orange"
      }

    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.underline {
  text-decoration: underline;
}
.promoted {
  font-style: italic;
}
.new {
  color: olive;
}
.sold-out {
  color: red;
}
</style>

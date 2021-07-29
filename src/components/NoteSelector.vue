<template>
  <div class="note-selector active" v-bind:class="{active: note.id === selectedNoteId}" v-on:click="selectNote(note)">
    <p class="note-selector-title">{{ note.body }}</p>
    <p class="note-selector-timestamp">{{ note.timestamp }}</p>
    <h1>{{ selectedNoteId }}</h1>
  </div>
</template>

<script>
  export default {
    props: ["note", "selectedNoteId"],
    methods: {
      selectNote: function(note) {
        console.log(note.id);
        this.$emit("selectNote", note);
      }
    }
  }
</script>
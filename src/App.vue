<script>
import NoteToolbar from "@/components/NoteToolbar.vue";
import NoteContainer from "@/components/NoteContainer.vue";

export default {
  components: {
    NoteToolbar,
    NoteContainer
  },
  data: function () {
    return {
      notes: [
        { id: 1, body: "This is a first test", timestamp: Date.now() },
        { id: 2, body: "This is a second test", timestamp: Date.now() },
        { id: 3, body: "This is a third test", timestamp: Date.now() },
        { id: 4, body: "This is a fourth test", timestamp: Date.now() }
      ],
      selectedNoteId: 1
    };
  },
  methods: {
    selectNote: function (note) {
      this.selectedNoteId = note.id;
    }
  }
};
</script>

<template>
  <div id="app">
    <NoteToolbar />
    <NoteContainer
      :notes="notes"
      @select-note="selectNote"
      :selectedNoteId="selectedNoteId"
    />
  </div>
</template>

<style>
/* RESET */
* {
  margin: 0;
  padding: 0;
  border: 0;
  outline: none;
  box-sizing: border-box;
}

/* LAYOUT */
#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

/* COLORS */
* {
  color: #454545;
  background-color: #fafaf8;
}

/* TYPOGRAPHY */
body {
  font-family: sans-serif;
}
</style>

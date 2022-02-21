<script>
import NoteSelectors from "@/components/NoteSelectors.vue";
import NoteEditor from "@/components/NoteEditor.vue";

export default {
  components: {
    NoteSelectors,
    NoteEditor
  },
  props: ["notes", "selectedNoteId"],
  methods: {
    selectNote: function (note) {
      this.$emit("selectNote", note);
    }
  }
};
</script>

<template>
  <div class="note-container">
    <NoteSelectors
      :notes="notes"
      @select-note="selectNote"
      :selectedNoteId="selectedNoteId"
    />
    <NoteEditor />
  </div>
</template>

<style>
.note-container {
  display: flex;
  flex: 1;
}
</style>

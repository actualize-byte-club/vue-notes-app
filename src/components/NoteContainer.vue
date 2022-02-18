<script>
import NoteSelectors from "@/components/NoteSelectors.vue";
import NoteEditor from "@/components/NoteEditor.vue";

export default {
  components: {
    NoteSelectors,
    NoteEditor
  },
  props: ["notes", "selectedNoteId"]
};
</script>

<template>
  <div class="note-container">
    <NoteSelectors
      :notes="notes"
      @select-note="$emit('selectNote', note)"
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

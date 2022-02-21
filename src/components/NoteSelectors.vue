<script>
import NoteSelector from "@/components/NoteSelector.vue";

export default {
  components: {
    NoteSelector
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
  <div class="note-selectors">
    <NoteSelector
      v-for="note in notes"
      :key="note.id"
      :note="note"
      :selectedNoteId="selectedNoteId"
      @select-note="selectNote"
    />
  </div>
</template>

<style>
.note-selectors {
  flex: 0 0 13em;
}
.note-selectors {
  border-right: 1px solid #dcdadc;
}
</style>

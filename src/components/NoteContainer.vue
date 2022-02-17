<script>
import NoteSelectors from "@/components/NoteSelectors.vue";
import NoteEditor from "@/components/NoteEditor.vue";

export default {
  components: {
    NoteSelectors,
    NoteEditor
  }
};
</script>

<template>
  <div class="note-container">
    <NoteSelectors />
    <NoteEditor />
  </div>
</template>

<style>
.note-container {
  display: flex;
  flex: 1;
}
</style>

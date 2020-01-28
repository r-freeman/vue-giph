<template>
  <b-container>
    <b-row>
      <b-col>
        <GiphyViewer />
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import GiphyViewer from "./components/GiphyViewer";

export default {
  name: 'app',
  components: {
    GiphyViewer
  }
}
</script>

<style>

</style>

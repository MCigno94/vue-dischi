<template>

    <div class="genre cols h-100">
        <select class="genre_form text-white h-100 rounded-3" id="floatingSelectGrid" aria-label="Floating label select example"
        :value= "selectOptionGenre"
        @input="$emit('input', $event.target.value)"
        @click="$emit('seleziona', selectOptionGenre)"
        >
            <option selected>Seleziona il genere musicale</option>
            <option value="rock">Rock</option>
            <option value="pop">Pop</option>
            <option value="jazz">Jazz</option>
            <option value="metal">Metal</option>
        </select>
    </div>
    <!-- /.genre -->
</template>

<script>
export default {
    name: "SelectBoxGenre",
    props: {
        selectOptionGenre: String
    }
}
</script>

<style lang="scss" scoped>
  select {
    background-color: #1E2D3B;
    padding: 0.25rem 0;
  }
</style>
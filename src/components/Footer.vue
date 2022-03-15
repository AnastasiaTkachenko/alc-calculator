    <template>
 
    <v-footer bottom fixed padless>
      <v-col
          class="text-center"
          cols="12"
      >
        {{ new Date().getFullYear() }} — <strong>Cheeers!</strong>
      </v-col>
    </v-footer>

    </template>

<script>
  
export default  {
   name:"Footer",
}
</script>
<template>
  <v-footer>
    <slot>
      <div class="px-4 text-center w-100">
        <slot>{{ new Date().getFullYear() }} - Pokédex</slot>
      </div>
    </slot>
  </v-footer>
</template>

<script setup>

</script>

<template>
  <div>
    <AlbumListItem 
      v-for="album in albums"
      :key="album.url"
      :album="album"
    />
    <template v-if="isFetching">
      <div
        class="flex mb-3 animate-pulse"
        v-for="number in 10"
        :key="number"
      >
        <div class="w-16 h-16 bg-slate-200 mr-3">
          <!-- 이미지 자리 -->
        </div>
        <div class="w-full flex flex-col justify-between">
          <p class="w-2/3 h-3 bg-slate-200"></p>
          <p class="w-1/3 h-3 bg-slate-200"></p>
        </div>
      </div>
    </template>
  </div>
</template>

<script>
import AlbumListItem from '@/components/AlbumListItem'

export default {
  name: 'AlbumList',
  components: {
    AlbumListItem,
  },
  computed: {
    albums() {
      return this.$store.state.albums
    },
    isFetching() {
      return this.$store.state.isFetching
    },
  },
}
</script>

<style scoped>

</style>
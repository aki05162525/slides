<!-- 全スライド共通の下レイヤー。右下に小さくページ番号を表示（表紙は除く） -->
<template>
  <div
    v-if="$nav.currentPage > 1"
    class="abs-br m-3 text-xs opacity-40 select-none"
  >
    {{ $nav.currentPage }} / {{ $nav.total }}
  </div>
</template>

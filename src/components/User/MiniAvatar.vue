<template>
  <v-avatar :style="`border: 2px solid ${color};`" class="avatar" :size="size">
    <v-img
      v-if="src"
      class="avatar-img"
      :src="src"
      alt="cover"
      aspect-ratio="1"
    >
      <template v-slot:placeholder>
        <div class="avatar-img-loading">
          <v-progress-circular indeterminate color="#E56D9B" />
        </div>
      </template>
    </v-img>
    <!-- Default avatar -->
    <div v-else class="avatar-icon">
    <v-icon :size="Math.round(size * 0.7)" dark>mdi-account-circle</v-icon>
    </div>
  </v-avatar>
</template>

<script>

export default {
  components: {
  },
  props: {
    src: {
      type: String,
      default: ''
    },
    size: {
      type: Number,
      default: 20
    },
    color: {
      type: String,
      default: 'white'
    }
  }
}
</script>

<style lang="less" scoped>
.avatar {
  background: #252525;
  &-img {
    width: 100% !important;
    height: 100% !important;
    background: #252525;
    &-loading {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 100%;
      height: 100%;
    }
  }
  &-icon {
    border-radius: 50%;
    width: 100%;
    height: 100%;
    i {
      color: white;
    }
  }
}
</style>

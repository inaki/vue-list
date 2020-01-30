<template>
  <div>
    <div class="grid-title">
      <span class="data-cell">id</span>
      <span class="data-cell">title</span>
      <span class="data-cell">filename</span>
      <span class="data-cell">redacted at</span>
      <span class="data-cell">state</span>
      <span class="data-cell">req-id</span>
      <span class="data-cell">count</span>
    </div>
    <div v-for="item in documents" class="grid-data">
      <span class="data-cell">{{ item.id }}</span>
      <span class="data-cell">{{ item.title }}</span>
      <span class="data-cell">{{ item.filename }}</span>
      <span class="data-cell">{{ item.redacted_at }}</span>
      <span class="data-cell">{{ item.state }}</span>
      <span class="data-cell">{{ item.request_id }}</span>
      <span class="data-cell">{{ item.redaction_layer_count }}</span>
    </div>
  </div>
</template>

<script>
export default {
  props: ["documents"]
};
</script>

<style lang="scss" scoped>
.grid {
  &-title,
  &-data {
    display: grid;
    grid-template-columns: 10% 25% 25% 20% 10% 7% 3%;
    height: 19px;
    padding: 12px;
  }

  &-title {
    border-bottom: 2px solid #0f1c70;
    margin-bottom: 25px;
  }

  &-data {
    height: 32px;
    &:nth-child(even) {
      background: #f6f6f6;
    }
    .data-cell {
      padding: 5px 10px;
    }
  }
}
</style>

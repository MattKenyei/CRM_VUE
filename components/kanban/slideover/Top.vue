<script setup lang="ts">
import dayjs from "dayjs";

const store = useDealSlideStore();
</script>

<template>
  <div class="border-border bg-black/20 rounded p-3">
    <div class="uppercase bold text-xl mb-4">About deal</div>
    <KanbanSlideoverLabel label-text="Naming">
      <h2>{{ store.card?.name }}</h2>
    </KanbanSlideoverLabel>
    <KanbanSlideoverLabel label-text="Summary">
      {{ convertCurrency(store.card?.price || 0) }}
    </KanbanSlideoverLabel>
    <KanbanSlideoverLabel label-text="Status">
      <UiBadge variant="outline">
        {{ store.card?.status }}
      </UiBadge>
    </KanbanSlideoverLabel>
    <KanbanSlideoverLabel label-text="Client">
      {{ store.card?.companyName }}
    </KanbanSlideoverLabel>
    <KanbanSlideoverLabel label-text="Date">
      {{ dayjs(store.card?.$createdAt).format("DD MM YYYY") }}
    </KanbanSlideoverLabel>
  </div>
</template>

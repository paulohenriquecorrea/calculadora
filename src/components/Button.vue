<template>
  <div
    class="button"
    @click="$emit('onClick', label)"
    :class="{ double, triple, operation }"
  >
    {{ label }}
  </div>
</template>

<script>
export default {
  name: "ButtonDefault",
  props: {
    label: {},
    operation: { type: Boolean },
    double: { type: Boolean },
    triple: { type: Boolean },
  },
};
</script>

<style scope>
:root {
  --bg-button: #f0f0f0;
  --border-button: solid 1px #888;
}
.button {
  font-size: 1.4em;
  background-color: var(--bg-button);
  border: none;
  border-right: var(--border-button);
  border-bottom: var(--border-button);
  outline: none;
  color: black;

  display: flex;
  justify-content: center;
  align-items: center;
}

.button:active {
  background-color: #ccc;
}

.button.double {
  grid-column: span 2;
}

.button.triple {
  grid-column: span 3;
}

.button.operation {
  background-color: #fa8231;
  color: #fff;
}

.button.operation:active {
  background-color: #fa8231cc;
}
</style>
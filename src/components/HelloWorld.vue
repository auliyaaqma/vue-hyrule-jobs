<script lang="ts">
import { ref } from "vue";

export default {
  setup() {
    const title = ref("Hello, Vue 3!");

    setTimeout(() => {
      title.value = "New Title";
    }, 5000);

    return { title };
  }
};
</script>

<script lang="ts">
import { reactive } from "vue";

export default {
  setup() {
    const data = reactive({
      title: "Hello, Vue 3"
    });

    setTimeout(() => {
      data.title = "New Title";
    }, 5000);

    return { data };
  }
};
</script>
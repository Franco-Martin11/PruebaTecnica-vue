
<script>
import { ref } from 'vue'
export function dataFetch() {
    const datos = ref('')
    fetch("https://pokeapi.co/api/v2/pokemon")
        .then((res) => res.json())
        .then((data) => (datos.value = data));
    return { datos }
}
</script>

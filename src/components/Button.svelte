<script>
    let { text, fn } = $props();
</script>

<button
    onclick = {fn}
    class="transition-all duration-200 m-1 bg-white text-black rounded border px-1 py-1 hover:bg-black hover:cursor-pointer hover:text-white active:scale-125"
    >{text}</button>
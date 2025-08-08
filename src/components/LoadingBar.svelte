<script>
    let { current, max, color } = $props();
</script>

<div class="w-48 h-6 border">
    <div style="width: {(current / max) * 100}%" class="h-full transition-all duration-250 {color}"></div>
</div>
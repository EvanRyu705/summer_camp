<script>
    let { emote, position, color, animation } = $props();
</script>

<div class="flex h-10 items-center bg-orange-900">
    <div style="width: {position}%" class="h-full shrink-0 transition-all duration-1000 {color}"></div>
    <div class="animal {animation}">{emote}</div>
</div>

<style>
    .animal {
        font-size: 50px;
    }
    
    .bounce {
        animation: bounce 0.5s infinite;
    }

    .spin {
        animation: spin 0.5s linear infinite;
    }
    
    .pulse {
        animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;	
    }
</style>
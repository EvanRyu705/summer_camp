<script>
    import Horse from "./Horse.svelte";
    import Button from "../../components/Button.svelte";

    //array of horses
    let horses = $state([
        {
            emote: '🏇',
            position: 0,
            color: 'bg-blue-400',
            animation: 'bounce'
        },
        {
            emote: '🏇',
            position: 0,
            color: 'bg-blue-400',
            animation: 'bounce'
        },
        {
            emote: '🏇',
            position: 0,
            color: 'bg-blue-400',
            animation: 'bounce'
        },
        {
            emote: '🏇',
            position: 0,
            color: 'bg-blue-400',
            animation: 'bounce'
        },
        {
            emote: '🏇',
            position: 0,
            color: 'bg-blue-400',
            animation: 'bounce'
        },
        {
            emote: '🏇',
            position: 0,
            color: 'bg-blue-400',
            animation: 'bounce'
        },
        {
            emote: '🏇',
            position: 0,
            color: 'bg-blue',
            animation: 'bounce'
        },
        {
            emote: '🏇',
            position: 0,
            color: 'bg-blue',
            animation: 'bounce'
        }
    ]);

    function progress() {
        let maxHorse = horses[0];
        for(let horse of horses) {
            horse.animation = 'bounce';
            let r = parseInt(Math.random() * 20);
            horse.position += r;
            if (horse.position > 100) {
                horse.position = 100;
            }

            if(horse.position > maxHorse.position) {
                maxHorse = horse;
            }
        }

        for (let horse of horses) {
            if (horse.position == maxHorse.position) {
                horse.animation = 'spin';
                horse.color = 'bg-gradient-to-r from-cyan-500 via-cyan-300 to-cyan-200';
            } else {
                horse.animation = 'bounce';
                horse.color = 'bg-blue-400'
            }
        }
    }

    function reset() {
        for(let horse of horses) {
            horse.position = 0;
            horse.animation = 'bounce';
        }
    }
</script>

<div style="height: 600px;" class="bg-green-400">
    <div class="text-2xl font-bold text-center py-5">HORSE RACING GAME</div>
    <Button text={'Progress'} fn={progress} />
    <Button text={'Reset'} fn={reset} />
    <div class="pr-10 py-10">
        {#each horses as horse}
            <Horse
                emote={horse.emote}
                color={horse.color}
                animation={horse.animation}
                position={horse.position}    
            />
        {/each}
    </div>
</div>

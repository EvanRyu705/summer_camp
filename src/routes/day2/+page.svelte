<script>
    import Button from "../../components/Button.svelte";
    import LoadingBar from "../../components/LoadingBar.svelte";
    import HorseRace from "./HorseRace.svelte";
    let progress = $state(10);

    function increment() {
            progress += 10;
        if(progress > 100) {
            progress = 100
        }
    }
    function decrement() {
        progress -= 10;
        if(progress < 0) {
            progress = 0
        }
    }
    function reset() {
        progress = 0;
    }
</script>

<HorseRace />

<Button text={'Increment'} fn={increment} />
<Button text={'Decrement'} fn={decrement} />
<Button text={'Reset'} fn={reset} />

<div class="hover:bg-blue-500 text-center transition-all duration-1000 bg-red-400">
    https://tinyurl.com/btcasc
</div>

<LoadingBar color={'bg-blue-400'} current={progress} max={100}/>

<div class="hover:scale-135 hover:shadow-xl text-center m-2 h-10 w-15 border transition-all duration-1000">Box 1</div>
<div class="hover:bg-black hover:text-white text-center m-2 h-10 w-15 border transition-all duration-1000">Box 2</div>
<div class="hover:rotate-720 text-center m-2 h-10 w-15 border transition-all duration-1000">Box 3</div>
<div class="hover:opacity-0 text-center m-2 h-10 w-15 border transition-all duration-1000">Box 4</div>




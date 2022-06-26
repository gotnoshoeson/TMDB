
<!--Declare state object globally to be expected from componenet instance-->
<!--Import MovieCard componenet-->
<script>
    export let popular;
    import MovieCard from './MovieCard.svelte';
</script>

<!--App page component architecture-->
<h1>Popular Movies</h1>
<div class="popular-movies">
    {#each popular as movie}
        <MovieCard {movie}/>
    {/each}
</div>
<style>
    h1{
        padding: 0 1rem;
    }
    .popular-movies{
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
        grid-column-gap: 1rem;
        grid-row-gap: 2rem;
    }
</style>

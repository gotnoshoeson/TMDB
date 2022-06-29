<!--TheMovieDB API call, Popular, asynchronous-->
<script context="module">
    export async function load({ fetch }) {
        const res = await fetch(`https://api.themoviedb.org/3/movie/popular?api_key=${API_KEY}`
        );
        const data = await res.json();
        if(res.ok){
            return{
                props:{ popular: data.results }
            };
        }
    }
</script>
<!--Import Popular and Search components, set VITE_API in a .env file in the root of the directory 
-->
<script>
    import PopularMovies from '../components/PopularMovies.svelte';
    import SearchMovies from '../components/SearchMovies.svelte';
    export let popular;
    import { fly } from 'svelte/transition';
    import { API_KEY } from '../Env';
</script>
<!--
    Use components in main app and pass data object to the component, state is updated auto-magically!
-->
<section in:fly={{y: 80, duration: 500, delay: 500 }} out:fly={{ duration: 500 }}>
    <SearchMovies />
    <PopularMovies {popular}/>
</section>






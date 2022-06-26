<!--Make the movie object globally available so that it can be called
     in the component instance in the main app-->
<script>
    export let movie;
</script>

<!--Build the movie card component architecture with HTML elements,
    use movie object properties that are returned from API call from index-->
<div class="movie-card">
    <a sveltekit:prefetch sveltekit:noscroll href={'/movie/' + movie.id}>
        <img src={'https://image.tmdb.org/t/p/w500' + movie.poster_path} alt={movie.title} />
    </a>
    <div class="description">
        <h3>{movie.title}</h3>
        <p>{movie.release_date}</p>
    </div>
</div>

<style>
    img{
        width: 100%;
        height: 35vh;
        object-fit: cover;
        border-radius: 1rem;
        margin-bottom: 1rem;
    }
    h3 {
        font-size: 1rem;
    }
    .description {
        height: 5vh;
    }
    p{
        font-size: 0.7rem;
    }
    .movie-card {
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        padding: .7rem;
    }
</style>

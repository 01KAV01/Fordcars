<svelte:head>
<title>Автомобили</title>
</svelte:head>
<div class='container'>
    <h1>Автомобили</h1>
    <div class='blogposts'>
        {#each routes as page}
            <div class='post'>
                <h2>{page.title}</h2>
                <p class:body-offset={page.id === 2}>{page.body}</p>
                {#if page.id === 3}
                <p class="body-offset2"></p> 
            {/if}
                <p class='readmore'>
                    <img src={page.image} alt="Blog Post Image" />
                    <a class='link' href={`/attractions/posts/${page.id}`}>
                         Читать далее
                    </a>
                </p>
            </div>
        {/each}
        
    </div>
</div>

<script>
    import {routes} from './routes'
</script>

    <style>

:root {
    --primary-color: #3498db;
    --secondary-color: #2ecc71;
    --text-color: #333;
    --background-color: #f5f5f5;
    --border-color: #e7e7e7;
}
img{
    width: 300px;
    height: 300px;
}

.blogposts {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-gap: 20px;
}

.post {
    border: 1px solid var(--border-color);
    padding: 20px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    background-color: var(--background-color);
    border-radius: 5px;
    transition: box-shadow 0.3s ease;
}

.post:hover {
    box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
}

.link {
    color: var(--primary-color);
    text-decoration: none;
    transition: color 0.3s ease;
}

.link:hover {
    color: var(--secondary-color);
}

h1, h2 {
    color: var(--primary-color);
}

p {
    margin-bottom: 10px;
}

.body-offset {
        margin-top: 45px; 
    }

.body-offset2 {
        margin-top: 36px; 
    }
 
    </style>
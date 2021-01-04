<script>
    let ranks = ["Founder", "Chairman", "Vice Chairman", "Organising Secretary", "Treasurer", "Head Of IT"]
    let name = "Founder";
</script>

<div class="tab-elements">
    {#each ranks as rank, i}
    <button class="rank" on:click="{()=> name = rank}" class:active="{name === rank}">{rank}</button>
    {/each}
</div>

<div class="container">
    <div class="person">
        
        <div class="name">
            <div class="faded-text">
                {name}
            </div>
            <h1>{name}</h1>
        </div>
        <div class="description">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Sequi, delectus sint! Quam odit ut accusamus voluptates reiciendis ab maiores, similique nesciunt vel est voluptatem dolor excepturi dolorum doloribus nisi sunt.
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Ipsa unde maiores quo vero libero dignissimos error debitis, odio numquam perspiciatis quis natus fugit enim inventore! Quis ab dolor reprehenderit deleniti.
        </div>
    </div>
    <div class="image">
        <img src="https://source.unsplash.com/featured?98" alt="">
    </div>
</div>

<style>
    .container {
        display: flex;
        min-height: 80vh;
        height: 100%;
        margin: 0 20px;
    }
    .container > * {
        /* margin: 0 30px; */
        margin-top: 15px;
        padding: 40px;
    }
    .person {
        width: 50%;
        display: flex;
        justify-content: center;
        flex-direction: column;
    }
    h1 {
        font-size: 6rem;
        text-transform: uppercase;
    }
    .image img{
        height: 100%;
        width: 100%;
    }

    .faded-text {
        font-size: 10rem;
        color: rgba(0, 255, 21, 0.13);
        margin-bottom: -120px;
        text-transform: uppercase;
        overflow: hidden;
    }
    .tab-elements {
        width: 100%;
        display: flex;
        justify-content: stretch;
        justify-items: stretch;
        
    }
    .tab-elements > .rank {
        flex: 1;
    }
    .rank {
        border: 1px solid #fff;
        padding: 15px 25px;
        background: none;
        color:#fff;
        text-transform: uppercase;
    }

    .rank:hover {
        background: #fff;
        color: #000;
    }
    .rank.active {
        background: #fff;
        color: #000;
    }

    @media screen and (max-width: 750px) {
        h1 {
            font-size: 3rem;
        }
        .faded-text {
            font-size: 5rem;
            margin-bottom: -60px;
        }
        .tab-elements {
            flex-direction: column;
        }
        .container > * {
            padding: 0;
        }

        .image {
            height: 100%;
        }
        
    }

    @media screen and (max-width: 1200px) {
        .container {
            flex-direction: column;
        }
        .person {
            width: 100%;
        }
    }

</style>
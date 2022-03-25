<template>
    <div>
        <nav class="navbar">
            <div>
                <img src="https://iconape.com/wp-content/png_logo_vector/pharmacie-logo.png" alt="">
            </div>
            <div>
                <ul>
                   <a href="#"><li>home</li></a>
                   <a href="#"> <li>contact</li></a>
                    <a href="#"> <li>login</li></a>
                </ul>
            </div>
        
        </nav>
 
    </div>
</template>

<script>
export default {
    name: 'Nav',
}

</script>

<style>
    .navbar{
        background-color: lightblue;
        border: 1px dotted azure;
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    img{
        width: 55px;
        height: 55px;
        padding: 10px;
    }
    ul{
        display: flex;
        list-style: none;
    }
    li{
        font: 400;
        font-size: medium;
        font-family: 'Times New Roman', Times, serif;
        margin-right: 15px;
        text-decoration: none;
        color: black;
    }
    a{
        text-decoration: none;
    }

</style>
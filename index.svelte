<script>
  import axios from 'axios';
    let url=''
    let send=false;
    let shorturl='http://trim-url.vercel.app/'
    async function sendReq () {
         send=true;
        const response = await axios.post('https://url-shortener-manitej66.azurewebsites.net/api/shorten?code=USDsXCIeE0UKKJTi9pMWHTyQOFWIu2zAOmWmzcAW7PorrkqDeOcnHQ==',
        {
        "url": url
        }
        )
    shorturl = shorturl + response.data.shortUrl
    }

</script>
<div class="inside">
<img height="50" src="https://cdn.tutsplus.com/mac/uploads/2013/09/vanityURL-preview-retina.png" alt="logo.png"/>
<h1> url shortener 🤏</h1>
<p>This website helps you to shorten your links </p>
<div class="box">
    <input bind:value={url} type="text" placeholder="Type or Paste your link">
    <button class ="button" on:click={sendReq}>SHORTEN</button>
</div>
{#if send==true}
<h3>{shorturl}</h3>
{/if}
</div>
<style>
h1 {
    text-align: center;
    margin-top:30px;
}
p{
    text-align: center;
}
input {
    padding:20px;
    width:45%;
    align-items: center;
    margin-right: 2%;
    border-radius: 10px;
}
button{
    padding:20px;
    border:none;
    background-color: rgb(91, 180, 158);
    border-radius: 10px;
}
.box {
    display: flex;
    flex-direction: row;
    align-items: center;
    margin-left: 30%;
    margin-top: 5%;
    margin-bottom: 7%;
}
.inside img{
    margin-left:20px;
}
.inside{
    border: 2px white solid;
    margin: 70px;
    padding-bottom: 60px;
    background-color:white;
    height: 400px ;
}
h3{
    text-align: center;
}
</style>
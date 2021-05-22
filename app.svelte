<script>
  let jokes = [];
  async function get() {
    const data = await fetch("https://official-joke-api.appspot.com/jokes/ten");
    const d = await data.json();
    //console.log(d);
    jokes = d;
  }
</script>
    
    <div>

   <button on:click={get}><span>get jokes</span></button>
   {#each jokes as joke}
     <div style="border:10px solid blue; border-radius: 12px;margin:100px; padding:10px">
       <h3 style="font-family:Arial Black; color:black">{joke.setup}</h3>
       <h4 style="font-family:Lucida Handwriting;color:red">{joke.punchline}</h4>
    </div>
  {/each}
</div>

<style>
  div {
    height: 100%;
    margin: 0;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    background-attachment: fixed;
    background-image: url("https://library.kissclipart.com/20180831/xq/kissclipart-clowns-png-clipart-joker-clown-clip-art-557ea07ee373e81c.jpg");
  }
  button {
    border: none;
    cursor: pointer;
    border-radius: 12px;
    color: black;
    margin: 100px;
    margin-top: 30px;
    display: inline-block;
    margin-left: 200px;
    padding: 15px 32px;
    text-align: center;
    font-size: 30px;
    background-color: gold;
  }
  button:hover {
    background-color: aquamarine;
    color: red;
  }
  button span {
    cursor: pointer;
    display: inline-block;
    position: relative;
  }

  button span:after {
    content: "\00bb";
    position: absolute;
    opacity: 0;
    top: 0;
    right: -20px;
  }

  button:hover span {
    padding-right: 25px;
  }
  button:hover span:after {
    opacity: 1;
    right: 0;
  }
  button:active {
    background-color: #3e8e41;
    box-shadow: 0 5px burlywood;
    transform: translateY(4px);
  }
</style>

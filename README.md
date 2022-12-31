<!DOCTYPE html>
<script>
    function getbooks(){
        document.getElementById('output').innerHTML="";
        fetch("http://openlibrary.org/search.json?q="+document.getElementById("input").value).then(a=>a.json()).then(response=>{
            for(var i=0; i<response.docs.length; i++){
            document.getElementById( "output").innerHTML+="<h2>"+response.docs[i].title+"</h2>"+"first edition:"+response.docs[i].first_publish_year+"<br>Author:"+response.docs[i].author_name[0]+"<br><img src='http://covers.openlibrary.org/b/isbn/ "+response.docs[i].isbn[0]+"-M.jpg'><br>"+"<hr>";
            
        }
            });
            
            }
</script>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Book Search</title>
    <style>
        .h{
    margin-top: 2rem;
  font-size: 2.5rem;
  font-weight:bolder;
  text-align: center;

}
#input{
    width: var(--ha-screen-reader-width, 20rem);
  height: var(--ha-screen-reader-height, 3rem);
  padding: var(--ha-screen-reader-padding, 0);
  margin: auto;
  margin-top: 3rem;
  display: block;
  
}
#input:focus {
    outline: none;
    border-color:#6f9ee8;
    box-shadow: 0 0 10px #6f9ee8;
  }
  body {
    background: url('https://static.vecteezy.com/system/resources/thumbnails/004/709/149/small/grey-white-abstract-background-geometry-shine-and-layer-element-for-presentation-design-suit-for-business-corporate-institution-party-festive-seminar-and-talks-vector.jpg') no-repeat center center fixed;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    background-size: cover;
    -o-background-size: cover;
  }
  hr{
    position: relative;
    margin-left: 15em;
    margin-right: 15em;
  }
    
    &.center-ball{
      background: $aqua;
      
      &:before{
        content: "";
        width: 6px;
        height: 6px;
        background: $aqua;
        display: inline-block;
        border: 2px solid $aqua;
        @include border-radius(50%);
        position: absolute;
        top: -4px;
        left: 50%;
        margin: 0 0 0 -3px;
      }
    }
#image{
    width:100%;
    display:block;
    padding-top:10rem; 
    
  }
  
/* CSS */
.butt{
  align-items: center;
  appearance: none;
  background-image: radial-gradient(100% 100% at 100% 0, #5adaff 0, #5468ff 100%);
  border: 0;
  border-radius: 6px;
  box-shadow: rgba(45, 35, 66, .4) 0 2px 4px,rgba(45, 35, 66, .3) 0 7px 13px -3px,rgba(58, 65, 111, .5) 0 -3px 0 inset;
  box-sizing: border-box;
  color: #fff;
  cursor: pointer;
  display: inline-flex;
  font-family: "JetBrains Mono",monospace;
  height: 48px;
  justify-content: center;
  line-height: 1;
  list-style: none;
  margin-left: 44rem;
  margin-top: 2rem;
  overflow: hidden;
  padding-left: 16px;
  padding-right: 16px;
  position: relative;
  text-align: left;
  text-decoration: none;
  transition: box-shadow .15s,transform .15s;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  white-space: nowrap;
  will-change: box-shadow,transform;
  font-size: 18px;
}

.butt:focus {
  box-shadow: #3c4fe0 0 0 0 1.5px inset, rgba(45, 35, 66, .4) 0 2px 4px, rgba(45, 35, 66, .3) 0 7px 13px -3px, #3c4fe0 0 -3px 0 inset;
}

.butt:hover {
  box-shadow: rgba(45, 35, 66, .4) 0 4px 8px, rgba(45, 35, 66, .3) 0 7px 13px -3px, #3c4fe0 0 -3px 0 inset;
  transform: translateY(-2px);
}

.butt:active {
  box-shadow: #3c4fe0 0 3px 7px inset;
  transform: translateY(2px);
}


    </style>
    <script src="https://kit.fontawesome.com/2745e261bc.js"></script>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-rbsA2VBKQhggwzxH7pPCaAqO46MgnOM80zW1RWuH61DGLwZJEdK2Kadq2F9CUG65" crossorigin="anonymous">
  </head>
  <body>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-kenU1KFdBIe4zVF0s0G1M5b4hcpxyD9F7jL+jjXkk+Q2h455rYXK/7HAuoJl+0I4" crossorigin="anonymous"></script>
    <p class="h">Book Search</p>
   <input id="input" placeholder="enter book name">
   
    <button class="butt" onclick="getbooks()">get books</button><br>
    <div id="output"></div>  
    
    <script src="script.js"></script>
</body>

</html>
 

# sites
website
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>recepie</title>
    <script src="jquery-3.2.1.js"></script>
    <script src="bootstrap.js"></script>
    <link rel="stylesheet" href="index.css">
    <link rel="stylesheet" href="bootstrap.css"> </head>
    

<script>
   $(document).ready(function(){
    function action(){
            $('#result').show();
        $('#result').html('');
        var searchField = $('#search').val();
        var searchField1 = $('#search').val().trim().toUpperCase();
        var expression = new RegExp(searchField,"i");
        $.getJSON('index.json', function (data) {
            $.each(data, function (key, value){
                
                if(searchField1==value.name){
                    $('#fname').html(value.name);
                    $('#benefits').html(value.pre);
                    $('#ing').html(value.ingredients);
                    $('#method').html(value.method);
                    $('#img').html('<img width="100%" src=" '+value.img+' " >')
//                    $('#img').attr("src",value.img);
                }
                
                
               if(value.name.search(expression) != -1){
              $('#result').append('<li class="list-group-item" > '+value.name+'<li>');
               
              }
                  
            });
        });
    }
       
       
    $('#search').keyup(function (){
        action();
    });

       
       
       $('#result').mouseleave(function(){
         $('#result').hide();
       });
       
       $('#result').click(function(e){
           var value=$(e.target).text();
           $('#search').val(value);
           action();
           
       });
       
       
      $('.liya').hide();
       $('.cat').click(function(){
         $('.liya').toggle(500);              
                       
  });
       $('aside>div>a>ul>li').click(function(e){
           var input=$(e.target).text();
          $('#search').val(input);
          
           action();
            $('#result').hide();
           
       })
       
       
       
        $('aside>div>a>ul>li').hide();
       $('aside>div>a>ul').click(function(e){
           $(e.target.children).toggle();
//           $('aside>div>ul>li').toggle();
       });
          
       
   });
    
    
    </script>
    
    

<body id="bdy">
    <nav>
        <ul>
            <li> <a href="ind.html">Home</a> </li>
            <li class="cat" > Category
                <ul class="liya">
                    <li> <a href="#1">Local Dish</a> </li>
                    <li> <a href="#2">Contenental Dish</a> </li>
                </ul>
            </li>
            <li> <a href="#">Contact Us</a> </li>
        </ul>
        <div id="myCarousel" class="carousel slide">
            <!-- Carousel indicators -->
            <ol class="carousel-indicators">
                <li data-target="#myCarousel" data-slide-to="0" class="active"></li>
                <li data-target="#myCarousel" data-slide-to="1"></li>
                <li data-target="#myCarousel" data-slide-to="2"></li>
            </ol>
            <!-- Carousel items -->
            <div class="carousel-inner">
                <div class="item active"> <img width="100%" src="p6.png" alt="First slide"> </div>
                <div class="item"> <img width="100%" src="p7.png" alt="Second slide"> </div>
                <div class="item"> <img width="100%" src="p9.png" alt="Third slide"> </div>
            </div>
            <!-- Carousel nav --><a class="carousel-control left" href="#myCarousel" data-slide="prev">&lsaquo;</a> <a class="carousel-control right" href="#myCarousel" data-slide="next">&rsaquo;</a> </div>
    </nav>
    <form id="form">
        <input type="text" name="search" id="search" placeholder="search"  class="form-control" >
        
         <ul class="list-group" id="result" >  </ul>
         
          </form>
          
        
    <div id="part" >
    
     <aside>
       <div>
         
         <a name="1">
          <ul name="1" >Local Dish <span class="glyphicon glyphicon-chevron-down" ></span>
          <li>BANKU AND OKRO STEW</li>
          <li>TUO ZAAFI</li>
          <li>FANTE KENKEY AND HOT PEPPER WITH FRIED FISH</li>
          <li>KOKONTE AND PALM NOT SOUP</li>
          <li>FUFU AND GOAT LIGHT SOUP</li>
          <li>AMPESI</li>
          <li>YAM WITH KONTOBIRE STEW</li>
          <li>BOILED GARI WITH OKRO STEW</li>
          <li>RED RED</li>
          <li>FUFU AND GROUNDNUT SOUP WITH FRESH FISH</li>
          <li>KELEWELE</li>
        
          
          </ul>
           </a>
          
          <a  name="2">
           <ul>Continetal Dish <span class="glyphicon glyphicon-chevron-down" ></span>
       
        <li>CREAMY PASTA</li>
        <li>LAMB SALAD</li>
        <li>SWEET CHILE-LIME GRILLED CHICKEN</li>
        <li>RETATOUILLE</li>
        <li>CHICKEN CHEESE SALAD</li>
        <li>ROESTI AND SALAD</li>
        <li>PANEER-STEAK</li>
        <li>BAKED MUSHROOM AND CAPSICUM</li>
        <li>BAKED VEGETABLES</li>
        <li>BAKED MUSHROOM SPINACH</li>
        <li>CONTINENTAL APPLE CAKE</li>
        <li>ROSEMARY CHICKEN</li>
        <li>BAKED SPINACH</li>
        <li>FISH WITH CHEESE SAUCE</li>
            
                
                    
                
            
        </ul>
        </a>
          
       </div>
           
        
     </aside>
      
      <section>
      
      <h2  id="fname" ></h2>
      <div id="img"> <img src="p6.png" alt="">  </div>
     <div id="write" > <p id="benefits"></p>
      <p id="ing"></p>
      <p id="method"></p>
      </div>
      
      </section>
        </div>
</body>

</html>

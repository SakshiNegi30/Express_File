<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta charset="UTF-8">
<title>Admin Dashboard</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<style>
  body {
    font-family: Arial, Helvetica, sans-serif;
  }
  
  .flip-card {
    background-color: transparent;
    width: 300px;
    height: 300px;
    perspective: 1000px;
  }

  .flip-card-inner {
    position: relative;
    width: 100%;
    height: 100%;
    text-align: center;
    transition: transform 0.6s;
    transform-style: preserve-3d;
    box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  }

  .flip-card:hover .flip-card-inner {
    transform: rotateY(180deg);
  }

  .flip-card-front, .flip-card-back {
    position: absolute;
    width: 100%;
    height: 100%;
    -webkit-backface-visibility: hidden;
    backface-visibility: hidden;
  }

  .flip-card-front {
    background-color: #bbb;
    color: black;
  }

  .flip-card-back {
    background-color: #2980b9;
    color: white;
    transform: rotateY(180deg);
  }
  .navbar{
    display:flex;
    align-items: center;
    padding:20ps;

  }
  body{
    font-family: 'Poppins', sans-serif;
  }
  nav{
    flex:1;
    text-align:right;
  }
  nav ul{
    display:inline-block;
    list-style-type: none;
  }
  nav ul li{
    display:inline-block;
    margin-right:20px;
  }
  a{
    text-decoration:none;
    color:#555;

  }
  p{
    color:#555;
  }
  .container{
    max-width:1300px;
    margin:auto;
    padding-left: 25px;
    padding-right:25px;
  }
  .row{
    display:flex;
    align-items:center;
    flex-wrap:wrap;
    justify-content: space-around;
  }
  .col{
    flex-basis:50%;
    min-width:300px;
  }
  .col img{
    max-width:100%;
    padding:50px 0;
  }
  .col-2 h1{
    font-size:50px;
    background:blue;
    color:white;
    line-height:60px;
    margin:25 px 0;
  }
  .header{
    background:radial-gradient(#fff,#ffd6d6);
  }
  
</style>
</head>
<body>
  <div class="header">
  <div class="container">
    <div class="navbar">
      <div class="logo">
        <img src="data:image/jpeg;base64,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" width="125px">
  
      </div>
      <nav>
        <ul>
          <li><a href="">Home</a></li>
          <li><a href="">Products</a></li>
          <li><a href="">Dashboard</a></li>
          <li><a href="">Contact</a></li>
        </ul>
      </nav>

    </div>
    <div class="row">
      <div class="col-2">
        <h1>Products Market<br>Aquamart!</h1>
        <p>Helping the farmers.</p>
      </div>
      <div class="col-2">
        <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcQnLut9vJjs4SigAWJzTmGS4b_Vf1Qhihm8KA&usqp=CAU">
      </div>
    </div>
  </div>
<!---featured categories----------->
<div class="categories">
  >
</div>



<!----------------------search bar---------------------------------------------->
  <p id="space"></p>
      <center></span><input class="form-control" oninput="searchProduct(this);" id="search-product"
       style=" width: 900px;border-style:solid;border-color:rgb(40, 104, 187);border-width: 2px;height:55px" type="text"
        placeholder="Search Products here... "/>
     <ul class="list-group" id="results-display" style="width:380px"></ul></center>
<!------------filter--------------------------------------------------------------------->
<div class="row">
  <div style="width:25%">
 
        <button type="button" class="btn btn-primary" id="filter" style="width:330px;">FILTER</button>
        <ul class="list-group" id="filt_list" style="width:330px">
        <form method="GET" action="/filter">
 
        <br>



<% products.forEach(product => { %>

  <h1><%= product.name %></h1>
  <h3><%= product.vendorname %></h3>
  <div class="flip-card">
    <div class="flip-card-inner">
      <div class="flip-card-front">
        <img src="<%= product.imgurl %>" alt="Product" style="width:300px;height:300px;">
      </div>
      <div class="flip-card-back">
        <p><%= product.description %></p>
        <p> <%= product.price %> </p>
        <p> <%= product.category %> </p>
        <p> <%= product.vendorlocation %> </p>
        <button class="delete-product" data-id="<%= product._id %>">Delete</button>
        <button class="authorize-product" data-id="<%= product._id %>">Authorize</button>
      </div>
    </div>
  </div>

<% }) %>
<script>
  $(document).ready(function(){
    $('.delete-product').on('click', function(e){
      $target = $(e.target);
      const id = $target.attr('data-id');
      $.ajax({
        type: 'DELETE',
        url: '/products/'+id,
        success: function(response){
          alert('Product Deleted');
          window.location.href='/admindashboard';
        },
        error: function(err){
          console.log(err);
        }
      });
    });
  });
</script>
<script>
    $(document).ready(function(){
        $('.authorize-product').on('click', function(e){
          $target = $(e.target);
          const id = $target.attr('data-id');
          $.ajax({
            type: 'POST',
            url: '/admin/update/'+id,
            success: function(response){
              alert('Product Authorised');
              window.location.href='/admindashboard';
            },
            error: function(err){
              console.log(err);
            }
          });
        });
      });
</script>
</div>
</body>
</html>

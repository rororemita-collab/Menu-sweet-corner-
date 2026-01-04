<?php include "config.php"; ?>
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>sweet</title>
<link rel="stylesheet" href="style.css">
</head>
<body>

<header>
<nav class="navbar">
    <a href="#" class="nav-logo">
        <h2 class="logo-text">🧇The Sweet Corner</h2>
    </a>

    <ul class="nav-menu">
        <li class="nav-item"><a href="index.php" class="nav-link">Home</a></li>
        <li class="nav-item"><a href="aboutus.php" class="nav-link">About Us</a></li>
        <li class="nav-item"><a href="menu.php" class="nav-link">Menu</a></li>
        <li class="nav-item"><a href="Reviews.php" class="nav-link">Reviews</a></li>
        <li class="nav-item"><a href="contactus.php" class="nav-link">Contact us</a></li>
    </ul>
</nav>
</header>

<h2 class="TEXT2">Our Menu</h2>

<?php
$categories = ["Iced Coffee","Crêpes","Donuts"];

foreach($categories as $cat){
    echo "<h2 class='category'>$cat</h2>";
    echo "<div class='products'>";

    $res = mysqli_query($conn,"SELECT * FROM products WHERE category='$cat'");

    while($p = mysqli_fetch_assoc($res)){
?>
    <div class="product">
        <img src="images/<?= $p['image'] ?>" alt="<?= $p['name'] ?>">
        <h3><?= $p['name'] ?></h3>
        <p>$<?= $p['price'] ?></p>

      
        <form method="POST" action="buy.php">
            <input type="hidden" name="product" value="<?= $p['name'] ?>">
            <input type="hidden" name="price" value="<?= $p['price'] ?>">

            <label>Qty:
                <input type="number" name="qty" min="1" value="1" class="qty">
            </label><br>

            <label>Loct:
                <input type="text" name="location" required>
            </label><br>

            <label>Phone:
                <input type="text" name="phone" required>
            </label><br>

            <button class="buy-btn" type="submit" name="buy">Buy</button>
        </form>
    </div>
<?php
    }
    echo "</div>";
}
?>

<footer class="footer">
  <div class="footer-box">
    <h3>The Sweet Corner</h3>
    <ul>
      <li>Home</li>
      <li>About Us</li>
      <li>Menu</li>
      <li>Reviews</li>
      <li>Contact Us</li>
    </ul>
  </div>

  <div class="footer-box">
    <h3>Contact</h3>
    <p>Email: thesweetcorner21@gmail.com</p>
    <p>Phone: 05 xx xx xx xx</p>
    <p>Address: Rue 21 xxx, Skikda</p>
  </div>

  <div class="footer-box">
    <h3>Suivez-nous</h3>
    <ul>
      <li>Facebook</li>
      <li>Instagram</li>
    </ul>
  </div>
</footer>

<div class="footer-bottom">
    <p><b>© 2026 My Shop. The Sweet Corner.</b></p>
</div>






/* Categories */
.category {
    margin-top: 40px;
    font-size: 40px;
    color: black;
    text-align: center;
}

/* Products */
.products {
    display: flex;
    flex-wrap: wrap;
    gap: 80px;
    margin-top: 15px;
    justify-content: center;
   
  
}

.product {
    background: white;
       padding:  7px;
      width: 220px;
    border-radius: 30px;
    box-shadow: 0 0 8px rgba(0,0,0,0.15);
    text-align: center; 
    margin: 50px ;
    }

.product img {
    width: 80%;
    height: 210px;
    object-fit: cover;
    border-radius: 25px;
}

.product button {
    background:  rgb(116, 39, 39);
    color: white;
    border: none;
    padding: 8px;
    cursor: pointer;
    border-radius: 5px;
    margin-top: 5px;
}

.product button:hover {
    background:  rgb(116, 39, 39);
}

.product input.qty {
    width: 50px;
    margin-top: 5px;
}

</body>
</html>

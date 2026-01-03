# Index-sweet-corner 
<?php
include "config.php";

if(isset($_POST['send'])){
    $name = $_POST['name'];
    $email = $_POST['email'];
    $message = $_POST['message'];

    $sql = "INSERT INTO contacts(name,email,message) 
            VALUES('$name','$email','$message')";
    if(mysqli_query($conn,$sql)){
        echo "<script>alert('Message sent successfully!');</script>";
    }else{
        echo "Error: ".mysqli_error($conn);
    }
}
?>
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
            <a href="#"class="nav-logo">
        <h2 class="logo-text">🧇The Sweet Corner</h2>
    
    
           </a>
           <ul class="nav-menu">

        <li class="nav-item">
            <a href="index.php"class="nav-link">Home</a>

        </li>
        <li class="nav-item">
            <a href="aboutus.php"class="nav-link">About Us</a>

        </li>
        <li class="nav-item">
            <a href="menu.php"class="nav-link">Menu</a>

        </li>
        <li class="nav-item">
            <a href="Reviews.php"class="nav-link">Reviews</a>

        </li>
        <li class="nav-item">
            <a href="contactus.php"class="nav-link">contact us
</a>

        </li>
    

         </ul>   
        
 

    </nav>
   </header>




<section class="contact-container">

    <!-- Contact Information -->
   
    <div class="contact-info">
        <h2>Contact Information</h2>
        <p><strong>📍 Address:</strong> Rue 21 xxx, Skikda</p>
        <p><strong>📞 Phone:</strong> 05 xx xx xx xx</p>
        <p><strong>📧 Email:</strong> thesweetcorner21@email.com</p>

        <h3>🕒 Working Hours</h3>
        <ul>
            <li>Saturday – Thursday: <span>08:00 AM – 10:00 PM</span></li>
            <li>Friday: <span>02:00 PM – 10:00 PM</span></li>
        </ul>
    </div>

    <!-- Contact Form -->
    <!-- Form -->
<form action="" method="POST" class="contact-form">
<label><b>Name:</b></label>
<input type="text" name="name" required><br><br>
<label><b>Email:</b></label>
<input type="email" name="email" required><br><br>
<label><b>Message:</b></label>
<textarea name="message" required></textarea><br><br>
<button type="submit" name="send">Send</button>
</form>

</section>

<!-- Map Section -->
<section class="map-section">
    <h2>📍 Find Us</h2>
    <div class="map-container">
       <iframe
  src="https://www.google.com/maps?q=Skikda,+Algeria&output=embed"
  loading="lazy"
  allowfullscreen>
</iframe>
    </div>
</section>

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
    <p><b>© 2026 My Shop. The Sweet Corner.</b></p> </div>

    
</body>
</html>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400..900;1,400..900&display=swap');

.playfair-display {
  font-family: "Playfair Display", serif;
  font-optical-sizing: auto;
 
  font-style: normal;
}



* {
    padding: 0;
    margin: 0;
    font-family:  "Playfair Display", serif;
}

body{

    margin-top: 80px;
    background-color: rgb(116, 39, 39) ;
}
ul{
    list-style: none;
}
a{
    text-decoration: none;
}
button{
    cursor: pointer;
    border: none;
    background: none;
}
img{
    width: 100%;

}
.section-content{
    margin:  0 auto;
    padding: 0 20px;
  
}

    header {
        background-color:  rgb(116, 39, 39);
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
 
z-index: 1000;
}


header .navbar{
    display: flex;
    padding: 20px;
    align-items: center;
    justify-content:space-between ;
}
.navbar .nav-logo .logo-text{
    color: black;
   
  font-size: 28px;  
  font-style: oblique; 
  


}
.navbar .nav-menu{;
   
    display:flex;
    gap: 10px;
}

.navbar .nav-menu .nav-link{
   padding: 5px 40px;
  color: rgb(12, 12, 12);
  background-color: hsl(340, 100%, 99%);
  border-radius: 20px;
  transition: 0.3s ease;

}






.navbar .nav-menu .buy-btn:hover{
   color: rgb(6, 6, 6);
    background-color:rgb(176, 165, 166);
}
main{
        background-image: url(images/photo_2025-12-27_12-26-45.jpg);

 background-position: center;
 background-repeat: no-repeat;
 background-size: cover;
 height: 550px;
}
.hero-section .hero-details .title{
       color: black;
   
  font-size: 25px;   
  font-style: italic; 
  

}
.hero-section .hero-details .subtitle{
          color: rgb(60, 0, 0);
   
  font-size: 25px;   
  font-style: italic;

}
.hero-section .hero-details .descrption{
     color: black;
     
  font-style: oblique;
  font-size: 20px;
  line-height: 1.8;
 
  letter-spacing: 0.5px;


}
.hero-section .hero-details .button{
    
  margin-right: 30px;
  padding:2px 40px;
 border:  2px solid white;
   background:  rgb(116, 39, 39);
  color: black;
  text-decoration: none;
  border-radius: 15px;
  transition: 0.3s ease;
}
.hero-section .hero-details .button:hover{
      background-color:rgb(176, 165, 166);
}
.hero-section .hero-details .contactus{ 
    background: transparent;
  margin-right: 30px;
  padding:2px 40px;
  border-radius: 15px;
  border:  2px solid white;
  color:white;
  text-decoration: none;

}
.hero-section .hero-details .contactus:hover{
      background-color:rgb(176, 165, 166);
}
.footer {
  background-color:   rgb(116, 39, 39);
  color: #fff;
  display: flex;
  justify-content: space-around; /* يفرّقهم */
  align-items: flex-start;
  padding: 60px 80px;
  gap: 60px; /* مسافة بين البوكسات */
}

.footer-box {
  width: 25%;
}

.footer-box h3 {
  margin-bottom: 20px;
  color: black;
}

.footer-box ul {
  list-style: none;
  padding: 0;
}

.footer-box ul li {
  margin-bottom: 10px;
}

.footer-box p {
  margin-bottom: 10px;
}
.footer-bottom{
  text-align: center;
  margin-top: 10px;
  font-size: 20px;
  color:black;
}

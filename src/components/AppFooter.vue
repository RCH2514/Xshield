<template>
  <footer class="footer">
    <div class="container">
      <div class="row">
        <div class="col-md-4">
          <img
            src="@/assets/images/logo.png"
            alt="XShield Logo"
            class="logo"
          />
          <p>Experience the peace of mind that comes with unyielding protection.</p>
        </div>
        <div class="col-md-4">
          <h4 class="footer-title">Contact Us</h4>
          <ul>
            <li>
            
              Xshield ,EL Ghazela
            </li>
            <li>
          
              99 888 777
            </li>
            <li>
            
              Xshield@gmail.com
            </li>
          </ul>
        </div>
        <div class="col-md-4">
          <h4 class="footer-title">Follow Us</h4>
          <ul class="social-icons">
            <li>
              <a href="https://www.facebook.com/yourcompany" aria-label="Facebook">
                
              </a>
            </li>
            <li>
              <a href="https://www.twitter.com/yourcompany" aria-label="Twitter">
           
              </a>
            </li>
            <li>
              <a href="https://www.instagram.com/yourcompany" aria-label="Instagram">
             
              </a>
            </li>
          </ul>
        </div>
      </div>
      <div class="row">
        <div class="col-md-12">
          <p class="footer-copyright">
            &copy; {{ new Date().getFullYear() }} XSHIELD. All rights reserved.
          </p>
        </div>
      </div>
    </div>
  </footer>
</template>


<style scoped>
.footer {
  background-color: #000;
  color: #fff;
  padding: 50px 0;
}

.footer-title {
  color: #fff;
  font-weight: bold;
}

.social-icons {
  list-style: none;
  padding: 0;
}

.social-icons li {
  display: inline-block;
  margin-right: 10px;
}

.social-icons a {
  color: #fff;
  font-size: 20px;
}

.footer-copyright {
  text-align: center;
}
.logo {
  height: 50px; /* Adjust the height of the logo image */
  width: auto;  /* Maintain aspect ratio */
  max-height: 100%; /* Ensure it doesn't exceed the height of the app bar */
}
.social-icons {
  list-style: none;
  padding: 0;
}

.social-icons li {
  display: inline-block;
  margin-right: 10px;
}

.social-icons a {
  color: #fff;
  font-size: 20px;
  text-decoration: none;
}

.social-icons a:hover {
  color: #ddd; /* Optional: lighter color on hover */
}

</style>

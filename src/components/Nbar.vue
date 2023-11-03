<template>
    <div id="navbar">
      <ul>
        <div class="nav-item">
          <img src="https://i.postimg.cc/qRJ1X1kc/github-removebg-preview.png" alt="">
          <span class="nav-description">LinkedIN</span>
        </div>
        <div class="nav-item">
          <img src="https://i.postimg.cc/NMdpNRM3/linkedin-removebg-preview.png" alt="">
          <span class="nav-description">Github</span>
        </div>
        <!-- <li class="nav-item">
          <img src="" alt="">
        </li> -->
      </ul>
    </div>
  </template>
  <script>
    window.addEventListener('scroll', function() {
      const navbar = document.getElementById('navbar');
      const navImages = document.querySelectorAll('.nav-item img');
  
  
      if (window.scrollY > 0) {
        navbar.classList.add('onScroll');
  
        navImages.forEach(function(image) {
          image.style.boxShadow = '0 0 10px rgba(217, 7, 84, 0.5)';
        });
      } else {
        navbar.classList.remove('onScroll');
  
        navImages.forEach(function(image) {
          image.style.boxShadow = 'none';
        });
      }
    });
  </script>
  
  <style scoped>
  * {
  text-align: center;
  font-family: 'Irish Grover';
    color: #bfc0c6;
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }
  
  img {
    width: 1.3rem;
    background-blend-mode: normal;
  }
  
  .nav-item {
    position: relative;
    margin-left: 1rem;
  }
  
  .nav-item img {
    width: 1.3rem;
    transition: transform 1s, box-shadow 1s;
  }
  
  .nav-item img:hover {
    transform: scale(1.2);
  }
  
  .nav-description {
    position: absolute;
    bottom: -2rem;
    left: 10%; 
    transform: translateX(-50%);
    background: #0D0D0D;
    color: #D90754;
    padding: 0.2rem 0.5rem;
    font-size: 12px;
    border-radius: 5px;
    opacity: 0;
    transition: opacity 0.3s;
  }
  
  .nav-item:hover .nav-description {
    opacity: 1;
  }
  
  .nav-link {
    margin: 0.4rem;
  }
  
  #navbar {
    position: fixed;
    width: 100%;
    background-color: transparent;
    transition: all 0.2s ease-in-out;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
    padding: 5px;
    z-index: 2;
    padding-inline: 2rem;
  }
  #navbar.onScroll {
    background-color: #0D0D0D;
  }
  
  #navbar {
    background-color: transparent;
  }
  
  .nav-item img {
    border-radius: 10%;
  }
  ul {
    display: flex;
    flex-direction: row-reverse;
  }
  
  
  @media screen and (max-width: 768px) {
    #navbar {
      padding: 10px;
    }
  
    ul {
      margin-right: 0;
    }
  
    .icon {
      font-size: 16px;
    }
  }
  </style>
    
# Javascript30
24) Sticky Nav: 

Using JS, it is possible to stick navigation bar across web page when scrolling window from top to bottom. 

We have to utilize the function that fixed nav through setting up offset height in pixel on top/edge of nav when window scroll down.

Example:

          const nav = document.querySelector('#main');
          let topOfNav = nav.offsetTop;

          function fixNav() {
            if (window.scrollY >= topOfNav) {
              document.body.style.paddingTop = nav.offsetHeight + 'px';
              document.body.classList.add('fixed-nav');
            } else {
              document.body.classList.remove('fixed-nav');
              document.body.style.paddingTop = 0;
            }
          }

          window.addEventListener('scroll', fixNav);

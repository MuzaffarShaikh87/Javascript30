# Javascript30
27) Click and Drag to Scroll: 

Over here, when we click anywhere and scroll left and/or right on our web page, our contents on the window will slide/move accordingly. 

This feature is helpful when user need to access data on the screen horizontally.

Example:

          const slider = document.querySelector('.items');
            let isDown = false;
            let startX;
            let scrollLeft;
          
          //Event when mouse down
            slider.addEventListener('mousedown', (e) => {
              isDown = true;
              slider.classList.add('active');
              startX = e.pageX - slider.offsetLeft;
              scrollLeft = slider.scrollLeft;
            });
          
          //Event when mouse leave 
            slider.addEventListener('mouseleave', () => {
              isDown = false;
              slider.classList.remove('active');
            });

          //Event when mouse up
            slider.addEventListener('mouseup', () => {
              isDown = false;
              slider.classList.remove('active');
            });

          //Event mouse is about to move or moving
            slider.addEventListener('mousemove', (e) => {
              if (!isDown) return;  // stop the fn from running
              e.preventDefault();
              const x = e.pageX - slider.offsetLeft;
              const walk = (x - startX) * 3;
              slider.scrollLeft = scrollLeft - walk;
            });

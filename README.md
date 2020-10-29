# Javascript30
16) Text Shadow Mouse Move Effect: 

We can make mouse movement effect to be appear with colorful display text and shadow on web browser across all over the page. 

Shadow function will set the height and width with event target.

Example:

          const hero = document.querySelector('.hero');
          const text = hero.querySelector('h1');
          const walk = 500; // 500px

          function shadow(e) {
            const { offsetWidth: width, offsetHeight: height } = hero;
            let { offsetX: x, offsetY: y } = e;

            if (this !== e.target) {
              x = x + e.target.offsetLeft;
              y = y + e.target.offsetTop;
            }


Walk value need to be set to have consistent width and height of each text and display in different rgb colors.


            const xWalk = Math.round((x / width * walk) - (walk / 2));
            const yWalk = Math.round((y / height * walk) - (walk / 2));

            text.style.textShadow = `
              ${xWalk}px ${yWalk}px 0 rgba(255,0,255,0.7),
              ${xWalk * -1}px ${yWalk}px 0 rgba(0,255,255,0.7),
              ${yWalk}px ${xWalk * -1}px 0 rgba(0,255,0,0.7),
              ${yWalk * -1}px ${xWalk}px 0 rgba(0,0,255,0.7)
            `;

          }

          hero.addEventListener('mousemove', shadow);

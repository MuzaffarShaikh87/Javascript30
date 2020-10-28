# Javascript30
8) HTML5 Canvas: 

In this lesson, I have learned new concept of HTML Canvas about how to perform drawing using different width of lines and their directions. 

Also, I experienced  the hsl where user can change the colour with separation, lightness and spectrum while drawing.

Example:

          const canvas = document.querySelector('#draw');
          const ctx = canvas.getContext('2d');
          canvas.width = window.innerWidth;
          canvas.height = window.innerHeight;
          ctx.strokeStyle = '#BADA55';
          ctx.lineJoin = 'round';
          ctx.lineCap = 'round';
          ctx.lineWidth = 100;
          // ctx.globalCompositeOperation = 'multiply';

          let isDrawing = false;
          let lastX = 0;
          let lastY = 0;
          let hue = 0;
          let direction = true;

          function draw(e) {
            if (!isDrawing) return; // stop the fn from running when they are not moused down
            console.log(e);
            ctx.strokeStyle = `hsl(${hue}, 100%, 50%)`;
            ctx.beginPath();
            // start from
            ctx.moveTo(lastX, lastY);
            // go to
            ctx.lineTo(e.offsetX, e.offsetY);
            ctx.stroke();
            [lastX, lastY] = [e.offsetX, e.offsetY];

            hue++;
            if (hue >= 360) {
              hue = 0;
            }
            if (ctx.lineWidth >= 100 || ctx.lineWidth <= 1) {
              direction = !direction;
            }

            if(direction) {
              ctx.lineWidth++;
            } else {
              ctx.lineWidth--;
            }

          }
         
         
I got the knowledge to set mouse movement action like mouseup, mousedown and mouseout with respec to starting and ending point when drawing.

Example:

          canvas.addEventListener('mousedown', (e) => {
          isDrawing = true;
          [lastX, lastY] = [e.offsetX, e.offsetY];
        });

        canvas.addEventListener('mousemove', draw);
        canvas.addEventListener('mouseup', () => isDrawing = false);
        canvas.addEventListener('mouseout', () => isDrawing = false);

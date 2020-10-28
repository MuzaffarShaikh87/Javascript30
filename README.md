# Javascript30
12) Key Sequence Detection: 

I learned that it is possible to pushed any key in an array when we press it from keyboard and then we can convert/join it as a string to make a single word.

This will allow to detect secret code what we we are looking for and make use of cornify_add() function to display any random image on web browser.

Example:
          
          
          const pressed = [];
          const secretCode = 'wesbos';

          window.addEventListener('keyup', (e) => {
            console.log(e.key);
            pressed.push(e.key);
            pressed.splice(-secretCode.length - 1, pressed.length - secretCode.length);
            if (pressed.join('').includes(secretCode)) {
              console.log('Got it!');
              cornify_add();
            }
            console.log(pressed);
          });

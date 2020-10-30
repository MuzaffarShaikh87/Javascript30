# Javascript30
25) Event Capture, Propagation, Bubbling and Once: 

All these properties are a part of Event Listener. 

Bubbling  means that when we click on the innermost element div on web browser, all the parent elements (divs) will also be triggered and click up at the same time. 

In order to overcome or to stop from this situation, we will use stopPropagation() i.e.stop bubbling. Capture events will be function towards down (i.e. outside div to inside div) 

whereas  Once event will be triggered just one time when any operation set up.

Example:

           const divs = document.querySelectorAll('div');
            const button = document.querySelector('button');

            function logText(e) {
              console.log(this.classList.value);
              // e.stopPropagation(); // stop bubbling!
              // console.log(this);
            }

            divs.forEach(div => div.addEventListener('click', logText, {
              capture: false,
              once: true
            }));

            button.addEventListener('click', () => {
              console.log('Click!!!');
            }, {
              once: true
            });

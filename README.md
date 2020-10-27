# Javascript30\
5) Flex Panel Gallery: 

Using CSS, I came to across some important properties which is flex that is used in individual panel of images. 

  Example:  
      
      
       .panel {
            background: #6B0F9C;
            box-shadow: inset 0 0 0 5px rgba(255,255,255,0.1);
            color: white;
            text-align: center;
            align-items: center;
            /* Safari transitionend event.propertyName === flex */
            /* Chrome + FF transitionend event.propertyName === flex-grow */
            transition: font-size 0.7s cubic-bezier(0.61,-0.19, 0.7,-0.11), flex 0.7s cubic-bezier(0.61,-0.19, 0.7,-0.11), background 0.2s;
            font-size: 20px;
            background-size: cover;
            background-position: center;
            flex: 1;
            justify-content: center;
            display: flex;
            flex-direction: column;
        }
        
        
      /* Flex Items */
        .panel > * {
            margin: 0;
            width: 100%;
            transition: transform 0.5s;
            flex: 1 0 auto;
            display: flex;
            justify-content: center;
            align-items: center;
        }

            .panel > *:first-child {
                transform: translateY(-100%);
            }

        .panel.open-active > *:first-child {
            transform: translateY(0);
        }

        .panel > *:last-child {
            transform: translateY(100%);
        }

        .panel.open-active > *:last-child {
            transform: translateY(0);
        }

        .panel p {
            text-transform: uppercase;
            font-family: 'Amatic SC', cursive;
            text-shadow: 0 0 4px rgba(0, 0, 0, 0.72), 0 0 14px rgba(0, 0, 0, 0.45);
            font-size: 2em;
        }

            .panel p:nth-child(2) {
                font-size: 4em;
            }

        .panel.open {
            flex: 5;
            font-size: 40px;
        }

I also know interesting concept about transition open and end when toggle function triggered in each panel on clicking.

  Example:
  
            function toggleOpen() {
                console.log('Hello');
                this.classList.toggle('open');
              }

              function toggleActive(e) {
                console.log(e.propertyName);
                if (e.propertyName.includes('flex')) {
                  this.classList.toggle('open-active');
                }
              }

              panels.forEach(panel => panel.addEventListener('click', toggleOpen));
              panels.forEach(panel => panel.addEventListener('transitionend', toggleActive));

# Javascript30
22) Follow Along Link Highlighter: 

This tutorial teach us to follow and highlight the links with respect to coordinates which we have sets up their width, height, top and left in pixels when mouse mover those texts/links.

These link Coords are bounded to highlight Link function and event will be trigger when mouse hover over those links.

Example:

           const triggers = document.querySelectorAll('a');
            const highlight = document.createElement('span');
            highlight.classList.add('highlight');
            document.body.appendChild(highlight);

            function highlightLink() {
              const linkCoords = this.getBoundingClientRect();
              console.log(linkCoords);
              const coords = {
                width: linkCoords.width,
                height: linkCoords.height,
                top: linkCoords.top + window.scrollY,
                left: linkCoords.left + window.scrollX
              };

              highlight.style.width = `${coords.width}px`;
              highlight.style.height = `${coords.height}px`;
              highlight.style.transform = `translate(${coords.left}px, ${coords.top}px)`;

            }

            triggers.forEach(a => a.addEventListener('mouseenter', highlightLink));

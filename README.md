# Javascript30
17)  Sorting Name Without Article:

I got the idea of sorting the name in the array and strip unwanted words(A, An, The)to display with appropriate title .

We can then map these individual name into list and join it as a string to sort out on web page.

Example: 

          const bands = ['The Plot in You', 'The Devil Wears Prada', 'Pierce the Veil', 'Norma Jean', 'The Bled', 'Say Anything', 'The Midway State', 'We Came as Romans', 'Counterparts', 'Oh, Sleeper', 'A Skylit Drive', 'Anywhere But Here', 'An Old Dog'];

          function strip(bandName) {
            return bandName.replace(/^(a |the |an )/i, '').trim();
          }

          const sortedBands = bands.sort((a, b) => strip(a) > strip(b) ? 1 : -1);

          document.querySelector('#bands').innerHTML =
            sortedBands
              .map(band => `<li>${band}</li>`)
              .join('');

          console.log(sortedBands);

# Javascript30
6) Ajax Type Ahead: 

In this tutorial, I learned how to find matched data with name when enter in search bar. This data is fetched from API using any resources of url as an endpoint.

Also, I learned the use of Regex pattern when user place any kind of text field that matched accordingly.

Function to display correct match of data which is mapped with specific city or state in order to return from the list of array.

In addition, keyup will filter the data to be exact match when user enter more words of text in search bar.

Example: 

          const endpoint = 'https://gist.githubusercontent.com/Miserlou/c5cd8364bf9b2420bb29/raw/2bf258763cdddd704f8ffd3ea9a3e81d25e2c6f6/cities.json';

              const cities = [];
              fetch(endpoint)
                .then(blob => blob.json())
                .then(data => cities.push(...data));//...implies to get all list of data's as an array that is to be pushed

              function findMatches(wordToMatch, cities) {
                return cities.filter(place => {
                  // here we need to figure out if the city or state matches what was searched
                  const regex = new RegExp(wordToMatch, 'gi');
                  return place.city.match(regex) || place.state.match(regex)
                });
              }

              function numberWithCommas(x) {
                return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',');
              }

              function displayMatches() {
                const matchArray = findMatches(this.value, cities);
                const html = matchArray.map(place => {
                  const regex = new RegExp(this.value, 'gi');
                  const cityName = place.city.replace(regex, `<span class="hl">${this.value}</span>`);
                  const stateName = place.state.replace(regex, `<span class="hl">${this.value}</span>`);
                  return `
                    <li>
                      <span class="name">${cityName}, ${stateName}</span>
                      <span class="population">${numberWithCommas(place.population)}</span>
                    </li>
                  `;
                }).join('');
                suggestions.innerHTML = html;
              }

              const searchInput = document.querySelector('.search');
              const suggestions = document.querySelector('.suggestions');

              searchInput.addEventListener('change', displayMatches);
              searchInput.addEventListener('keyup', displayMatches);

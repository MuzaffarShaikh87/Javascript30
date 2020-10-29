# Javascript30
15) Local Storage and Event Delegation: 

I have learned we can create a list using populateList, then we can also store these list items in local storage using localStorage.setitem(). 

We can then toggle these items to perform Event delegation that will occur on clicking those items in the list.

Example:

            const addItems = document.querySelector('.add-items');
            const itemsList = document.querySelector('.plates');
            const items = JSON.parse(localStorage.getItem('items')) || [];
            
            //Add item in the list
            function addItem(e) {
            // prevent to refresh the page by default
              e.preventDefault();
              const text = (this.querySelector('[name=item]')).value;
              const item = {
                text,
                done: false
              };
              
              //push the items in the list and store it in the local storage
              items.push(item);
              populateList(items, itemsList);
              localStorage.setItem('items', JSON.stringify(items));
              this.reset();
            }

            function populateList(plates = [], platesList) {
            //loop through every single item in an array and map the data
              platesList.innerHTML = plates.map((plate, i) => {
                return `
                  <li>
                    <input type="checkbox" data-index=${i} id="item${i}" ${plate.done ? 'checked' : ''} />
                    <label for="item${i}">${plate.text}</label>
                  </li>
                `;
              }).join('');
            }
            
            //Toggle event on clicking the items available in the added list
            function toggleDone(e) {
              if (!e.target.matches('input')) return; // skip this unless it's an input
              const el = e.target;
              const index = el.dataset.index;
              items[index].done = !items[index].done;
              localStorage.setItem('items', JSON.stringify(items));
              populateList(items, itemsList);
            }

            addItems.addEventListener('submit', addItem);
            itemsList.addEventListener('click', toggleDone);

            populateList(items, itemsList);

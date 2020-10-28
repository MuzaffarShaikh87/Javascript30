# Javascript30
10) Hold Shift to Check Multiple Checkboxes: 

After watching this tutorial and practicing, 
I understand the concept about holding  the shift key and select multiple checkboxes in between the list or all the list at once from top to bottom and/or vice versa.

Example:

          const checkboxes = document.querySelectorAll('.inbox input[type="checkbox"]');

          let lastChecked;

          function handleCheck(e) {
            // Check if they had the shift key down
            // AND check that they are checking it
            let inBetween = false;
            if (e.shiftKey && this.checked) {
              // go ahead and do what we please
              // loop over every single checkbox
              checkboxes.forEach(checkbox => {
                console.log(checkbox);
                if (checkbox === this || checkbox === lastChecked) {
                  inBetween = !inBetween;
                  console.log('Starting to check them in between!');
                }

                if (inBetween) {
                  checkbox.checked = true;
                }
              });
            }
            lastChecked = this;
          }

          checkboxes.forEach(checkbox => checkbox.addEventListener('click', handleCheck));

# Javascript30
4) Array Cardio 1:  

I learned the important concept of array with object using different functions such as filter, map, sort and reduce. 

Also, I am aware about how to display list of table using console.table 

Example: 

          Array.prototype.filter()
          1. Filter the list of inventors for those who were born in the 1500's
             const fifteen = inventors.filter(inventor => (inventor.year >= 1500 && inventor.year < 1600));
             console.table(fifteen);


          Array.prototype.map()
          2. Give us an array of the inventor first and last names
             const fullNames = inventors.map(inventor => `${inventor.first} ${inventor.last}`);
             console.log(fullNames);
             
          Array.prototype.sort()
          3. Sort the inventors by birthdate, oldest to youngest
             const ordered = inventors.sort((a, b) => a.year > b.year ? 1 : -1);
             console.table(ordered);

          Array.prototype.reduce()
          4. How many years did all the inventors live?
             const totalYears = inventors.reduce((total, inventor) => {
             return total + (inventor.passed - inventor.year);
             }, 0);
             console.log(totalYears);
             
          5. Sort Exercise
             Sort the people alphabetically by last name
             const alpha = people.sort((lastOne, nextOne) => {
             const [aLast, aFirst] = lastOne.split(', ');
             const [bLast, bFirst] = nextOne.split(', ');
             return aLast > bLast ? 1 : -1;
             });
             console.log(alpha);

          6. Reduce Exercise
             Sum up the instances of each of these
             const data = ['car', 'car', 'truck', 'truck', 'bike', 'walk', 'car', 'van', 'bike', 'walk', 'car', 'van', 'car', 'truck', 'pogostick'];

              const transportation = data.reduce(function(obj, item) {
                if (!obj[item]) {
                  obj[item] = 0;
                }
                obj[item]++;
                return obj;
              }, {});
              console.log(transportation);



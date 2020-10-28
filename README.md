# Javascript30
9) Dev Tool Tricks/Console Tricks: 

In this lesson, I came to know some important quick tricks to remember while using console command and is are as follows.

 // Interpolated
 We can add string in console.
          console.log('Hello I am a %s string!', '💩');
          
//Styled
We can add css style in console.log().  

          console.log('%c I am some great text', 'font-size:50px; background:red; text-shadow: 10px 10px 0 blue')
    
//Warning!
We can use console.warn() for Warning.

          console.warn('OH NOOO');
          
// Error
We can use console.error() to display Error.

          console.error('Error occur!');
          
 // Info
 We can use console.info() to provide any Information.
 
          console.info('Crocodiles eat 3-4 people per year');
          
 // Testing
  We can use console.assert() for Testing.
  
          const p = document.querySelector('p');

          console.assert(p.classList.contains('ouch'), 'That is wrong!');
          
 // clearing
  We can Clear data in console using console.clear().
  
          console.clear();
          
  
 // Grouping together
 We can use console.groupCollapsed() for grouping together all properties of object.
 
           dogs.forEach(dog => {
              console.groupCollapsed(`${dog.name}`);
              console.log(`This is ${dog.name}`);
              console.log(`${dog.name} is ${dog.age} years old`);
              console.log(`${dog.name} is ${dog.age * 7} dog years old`);
              console.groupEnd(`${dog.name}`);
            });
             console.table(dogs);
             

// timing
We can use console.timing() to see time of fetching data.

              console.time('fetching data');
              fetch('https://api.github.com/users/wesbos')
                .then(data => data.json())
                .then(data => {
                  console.timeEnd('fetching data');
                  console.log(data);
                });

   










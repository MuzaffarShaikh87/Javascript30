# Javascript30
7) Array Cardio 2:

I came to know some more interesting functions of arrays such as some, every, find and findIndex from the respective defined arrays.

Example: 

           Array.prototype.some() // is at least one person 19?
           const isAdult = people.some(person => ((new Date()).getFullYear()) - person.year >= 19);
           console.log({isAdult});
           
           Array.prototype.every() // is everyone 19?
           const allAdults = people.every(person => ((new Date()).getFullYear()) - person.year >= 19);
           console.log({allAdults});
           
           Array.prototype.find()
           // Find is like filter, but instead returns just the one you are looking for
           // find the comment with the ID of 823423
           const comment = comments.find(comment => comment.id === 823423);
           console.log(comment);

          Array.prototype.findIndex()
          // Find the comment with this ID
          // delete the comment with the ID of 823423
          const index = comments.findIndex(comment => comment.id === 823423);
          console.log(index);
          
          // comments.splice(index, 1);
             const newComments = [
             ...comments.slice(0, index),
             ...comments.slice(index + 1)

# Javascript30
18) Adding Up Times With Reduce: 

We can sum up all each videos duration/time together into total number of seconds using array and mapping them into one string. 

After that, using mathematical operations, we can convert this total number of seconds of all videos into total number of hours, minutes and seconds all videos runs.

Example:

          const timeNodes = Array.from(document.querySelectorAll('[data-time]'));

          const seconds = timeNodes
            .map(node => node.dataset.time)
            .map(timeCode => {
              const [mins, secs] = timeCode.split(':').map(parseFloat);
              return (mins * 60) + secs;
            })
            .reduce((total, vidSeconds) => total + vidSeconds);

            let secondsLeft = seconds;
            const hours = Math.floor(secondsLeft / 3600);
            secondsLeft = secondsLeft % 3600;

            const mins = Math.floor(secondsLeft / 60);
            secondsLeft = secondsLeft % 60;

            console.log(hours, mins, secondsLeft);

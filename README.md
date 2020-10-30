# Javascript30
28) Video Speed Controller: 

This is cool feature that I have seen and learned how speed controller take place. 

I have learned that with the different events that we can add the playback rate that controls the speed of video and audio as well. 

We can make our video speed from minimum to maximum where user can adjust easily.

Example: 

            const speed = document.querySelector('.speed');
              const bar = speed.querySelector('.speed-bar');
              const video = document.querySelector('.flex');

              function handleMove(e) {
                  const y = e.pageY - this.offsetTop;
                  const percent = y / this.offsetHeight;
                  const min = 0.4;
                  const max = 4;
                  const height = Math.round(percent * 100) + '%';
                  const playbackRate = percent * (max - min) + min;
                  bar.style.height = height;
                  bar.textContent = playbackRate.toFixed(2) + '×';
                  video.playbackRate = playbackRate;
                }

              speed.addEventListener('mousemove', handleMove);

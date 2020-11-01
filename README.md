# Javascript30
29) Countdown Clock: 

Countdown clock is an interesting feature to look in and to create our clock. 

We can able to see that how much time do we have left over to complete any task. 

This will show all the time that is been past, going on and remain. 

Date.Now() function in this will be static that shows current time for the ongoing task.

Example:

          let countdown;
          const timerDisplay = document.querySelector('.display__time-left');
          const endTime = document.querySelector('.display__end-time');
          const buttons = document.querySelectorAll('[data-time]');

          function timer(seconds) {
              // clear any existing timers
              clearInterval(countdown);

              const now = Date.now();
              const then = now + seconds * 1000;
              displayTimeLeft(seconds);
              displayEndTime(then);

              countdown = setInterval(() => {
                  const secondsLeft = Math.round((then - Date.now()) / 1000);
                  // check if we should stop it!
                  if (secondsLeft < 0) {
                      clearInterval(countdown);
                      return;
                  }
                  // display it
                  displayTimeLeft(secondsLeft);
              }, 1000);
          }

          function displayTimeLeft(seconds) {
              const minutes = Math.floor(seconds / 60);
              const remainderSeconds = seconds % 60;
              const display = `${minutes}:${remainderSeconds < 10 ? '0' : ''}${remainderSeconds}`;
              document.title = display;
              timerDisplay.textContent = display;
          }

          function displayEndTime(timestamp) {
              const end = new Date(timestamp);
              const hour = end.getHours();
              const adjustedHour = hour > 12 ? hour - 12 : hour;
              const minutes = end.getMinutes();
              endTime.textContent = `Be Back At ${adjustedHour}:${minutes < 10 ? '0' : ''}${minutes}`;
          }

          function startTimer() {
              const seconds = parseInt(this.dataset.time);
              timer(seconds);
          }

          buttons.forEach(button => button.addEventListener('click', startTimer));
          document.customForm.addEventListener('submit', function (e) {
              e.preventDefault();
              const mins = this.minutes.value;
              console.log(mins);
              timer(mins * 60);
              this.reset();
          });

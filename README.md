# Javascript30
Learning Points from Each Javascript Tutorials:

1) Javascript Drum Kit: 

Functions that Playsound using different types of audio and keycode which assigns to each individually key. 

  Example:   function playSound(e) {
              const audio = document.querySelector(`audio[data-key="${e.keyCode}"]`);
              const key = document.querySelector(`div[data-key="${e.keyCode}"]`);
              if (!audio) return;
              
Also, learned remove Transition function that takes place when event occurred after pressing the specific key one after another.

  Example:  function removeTransition(e) {
              if (e.propertyName !== 'transform') return;
              e.target.classList.remove('playing');
            }
            
             const keys = Array.from(document.querySelectorAll('.key'));
             keys.forEach(key => key.addEventListener('transitionend', removeTransition));
             indow.addEventListener('keydown', playSound);

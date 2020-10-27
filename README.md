# Javascript30
Learning Points for this tuotrial:

2)CSS + JS Clock: 

Using CSS, learn to know how transform and transition takes place in JS clock through degree and origin aspects. 

Example:   

.hand {
            width: 50%;
            height: 6px;
            background: black;
            position: absolute;
            top: 50%;
            transform-origin: 100%;
            transform: rotate(90deg);
            transition: all 0.05s;
            transition-timing-function: cubic-bezier(0.1, 2.7, 0.58, 1);
        }

In addition, I got to know how to set up seconds, minutes and hours using javascript with some mathematical operations.

Example:

  function setDate() {
    const now = new Date();

    const seconds = now.getSeconds();
    const secondsDegrees = ((seconds / 60) * 360) + 90;
    secondHand.style.transform = `rotate(${secondsDegrees}deg)`;

    const mins = now.getMinutes();
    const minsDegrees = ((mins / 60) * 360) + ((seconds/60)*6) + 90;
    minsHand.style.transform = `rotate(${minsDegrees}deg)`;

    const hour = now.getHours();
    const hourDegrees = ((hour / 12) * 360) + ((mins/60)*30) + 90;
    hourHand.style.transform = `rotate(${hourDegrees}deg)`;
  }

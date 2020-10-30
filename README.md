# Javascript30
23) Speech Synthesis: 

Here, I have experienced new concept using Javascript. 

We can set up voice and access it using  speak button whenever user enter/type any words/sentence in the text area. 

Also, we can stop speaking voice at any instant through stop button.

More features can also be added like increase/decrease rate of speech and can also adjust pitch sound/voice.  

Example: 

           const msg = new SpeechSynthesisUtterance();
            let voices = [];
            const voicesDropdown = document.querySelector('[name="voice"]');
            const options = document.querySelectorAll('[type="range"], [name="text"]');
            const speakButton = document.querySelector('#speak');
            const stopButton = document.querySelector('#stop');
            msg.text = document.querySelector('[name="text"]').value;
            
            //Populate all the voice in languages
            function populateVoices() {
                voices = this.getVoices();
                voicesDropdown.innerHTML = voices
                    .filter(voice => voice.lang.includes('en'))
                    .map(voice => `<option value="${voice.name}">${voice.name} (${voice.lang})</option>`)
                    .join('');
            }
            
            //Search and Set up specific voice
            function setVoice() {
                msg.voice = voices.find(voice => voice.name === this.value);
                toggle();
            }

            //Speech start over again once change to different voice
            function toggle(startOver = true) {
                speechSynthesis.cancel();
                if (startOver) {
                    speechSynthesis.speak(msg);
                }
            }

            //Set up option to select particular voice from the list
            function setOption() {
                console.log(this.name, this.value);
                msg[this.name] = this.value;
                toggle();
            }

            //Different Event take place once trigger 
            speechSynthesis.addEventListener('voiceschanged', populateVoices);
            voicesDropdown.addEventListener('change', setVoice);
            options.forEach(option => option.addEventListener('change', setOption));
            speakButton.addEventListener('click', toggle);
            stopButton.addEventListener('click', () => toggle(false));

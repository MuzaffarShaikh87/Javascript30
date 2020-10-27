# Javascript30
3) CSS Variable with JS: 

Learned how to set up properties of padding, background and filter to manage spacing, base and blur for image in root. 

Example: 

            :root {
                --base: #ffc600;
                --spacing: 10px;
                --blur: 10px;
            }

            img {
                padding: var(--spacing);
                background: var(--base);
                filter: blur(var(--blur));
                }



In addition, I get to know how to handle all update properties with their inputs when event takes place.

Example: 

        function handleUpdate() {
           const suffix = this.dataset.sizing || '';
           document.documentElement.style.setProperty(`--${this.name}`, this.value + suffix);
           }

        inputs.forEach(input => input.addEventListener('change', handleUpdate));
        inputs.forEach(input => input.addEventListener('mousemove', handleUpdate));

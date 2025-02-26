---
sidebar_position: 1
---

# Intro to Image Prompting

Figuring our the best prompt to create a perfect image is a particular challenge.
Research into methods to do so is not quite as developed as text prompting. This
may be due to inherent challenges in creating things which are fundamentally subjective
and often lack good accuracy metrics. However, fear not, as the image prompting 
community(@parsons2022dalleprompt) has made great discoveries about how to prompt various image models(@rombach2021highresolution)(@ramesh2022hierarchical).


## Example

Here I will go through an example of how I created the images for this course. 
I had been experimenting with low poly style for a deep reinforcement learning
neural radiance field project. I liked the low poly style, and wanted to use it 
for this course's images. 

I needed an astronaut, a rocket, and a computer for the images on the front page.

I did a bunch of research into how to create low poly images, on [r/StableDiffusion](https://www.reddit.com/r/StableDiffusion/)
and other sites, but couldn't find anything super helpful.

I decided to just start with DALLE and the prompt `Low poly white and blue rocket shooting to the moon in front of a sparse green meadow` and see what happened.

import rockets1 from '../assets/rockets_dalle_1.png';
import rockets2 from '../assets/rockets_dalle_2.png';
import computer_1 from '../assets/computer_dalle_1.png';
import astronaut_1 from '../assets/astronaut_dalle_1.png';
import astronaut_2 from '../assets/astronaut_sd_1.png';
import rocket_sd_1 from '../assets/rocket_sd_1.png';
import rocket_final from '../../static/img/rocket.png';
import laptop_sd_1 from '../assets/laptop_sd_1.png';
import gemstone_sd_1 from '../assets/gemstone_sd_1.png';
import gemstone_sd_2 from '../assets/gemstone_sd_2.png';
import gemstone_sd_3 from '../assets/gemstone_sd_3.png';
import focus_final from '../../static/img/computer.png';
import astronaut_final from '../../static/img/astronaut.png';

<div style={{textAlign: 'center'}}>
  <img src={rockets1} style={{width: "750px"}} />
</div>


<div style={{textAlign: 'center'}}>
  <img src={rockets2} style={{width: "750px"}} />
</div>

I thought these results were pretty decent for a first try; I particularly liked
the bottom left rocket.

Next, I wanted a computer in the same style: `Low poly white and blue computer sitting in a sparse green meadow`

<div style={{textAlign: 'center'}}>
  <img src={computer_1} style={{width: "750px"}} />
</div>

Finally, I needed an astronaut! `Low poly white and blue astronaut sitting in a sparse green meadow with low poly mountains in the background` seemed to to the trick.

<div style={{textAlign: 'center'}}>
  <img src={astronaut_1} style={{width: "750px"}} />
</div>

I thought the second one was decent.

Now I had an astronaut, a rocket, and a computer. I was happy with them,
so I put them on the front page. After a few days and input from my friends I
realized the style just wasn't consistent.

I did some more research on [r/StableDiffusion](https://www.reddit.com/r/StableDiffusion/) and found people using the word isometric.
I also realized that I needed to add more modifiers to my prompt
to constrain the style. I tried this prompt:
`A low poly world, with an astronaut in white suit and blue visor sitting in a sparse green meadow with low poly mountains in the background. Highly detailed, isometric, 4K`

<div style={{textAlign: 'center'}}>
  <img src={astronaut_2} style={{width: "250px"}} />
</div>

These weren't great, so I decided to start on the rocket instead

`A low poly world, with a white and blue rocket blasting off from a sparse green meadow with low poly mountains in the background. Highly detailed, isometric, 4K`

<div style={{textAlign: 'center'}}>
  <img src={rocket_sd_1} style={{width: "250px"}} />
</div>

After a bit of iterating around here, I ended up with 

<div style={{textAlign: 'center'}}>
  <img src={rocket_final} style={{width: "250px"}} />
</div>

Now I needed a better laptop

`A low poly world, with a white and blue laptop sitting in sparse green meadow with low poly mountains in the background. The screen is completely blue. Highly detailed, isometric, 4K`

<div style={{textAlign: 'center'}}>
  <img src={laptop_sd_1} style={{width: "250px"}} />
</div>

I got some inconsistent results; I like the bottom right one, but I decided to go in a different direction.

`A low poly world, with a glowing white and blue gemstone sitting in a sparse green meadow with low poly mountains in the background. Highly detailed, isometric, 4K`

<div style={{textAlign: 'center'}}>
  <img src={gemstone_sd_1} style={{width: "250px"}} />
</div>

This wasn't quite right. Let's try something magical and glowing.

`A low poly world, with a glowing white and blue gemstone magically floating in the middle of the screen above a sparse green meadow with low poly mountains in the background. Highly detailed, isometric, 4K`

<div style={{textAlign: 'center'}}>
  <img src={gemstone_sd_2} style={{width: "250px"}} />
</div>

I liked these, but wanted the stone in the middle of the screen.

`A low poly world, with a glowing blue gemstone magically floating in the middle of the screen above a sparse green meadow with low poly mountains in the background. Highly detailed, isometric, 4K`

<div style={{textAlign: 'center'}}>
  <img src={gemstone_sd_3} style={{width: "250px"}} />
</div>

Somewhere around here I used SD's ability to have a previous image provide some influence for future images.
And thus I arrived at

<div style={{textAlign: 'center'}}>
  <img src={focus_final} style={{width: "250px"}} />
</div>

Finally, I was on to the astronaut.

`A low poly world, with an astronaut in white suite and blue visor is sitting in a sparse green meadow with low poly mountains in the background. Highly detailed, isometric, 4K`

<div style={{textAlign: 'center'}}>
  <img src={astronaut_final} style={{width: "250px"}} />
</div>

At this point, I was sufficiently happy with the style consistency between my three images to use them
on the website. The main takeaways for me were that this was a very iterative, research heavy process,
and I had to modify my expectations and ideas as I experimented with different models.
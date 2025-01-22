# The Art of Listening and Generative Sound Creation

## 1. Foundations of Sound

### The Science of Sound

![Cool Image](images/Sound_Mirrors.jpg)

*During the war we were good at listening*


- Life is made of waves. Sound is a wave phenomenon that travels through air and other media.  
- The human ear converts these waves into electrical signals, allowing us to perceive sound.  
- Similar to how light waves create visuals, sound waves create auditory experiences.

### The Science of Seeing Sound
- Sound is physical and can be made visible.
- **Standing Waves Demonstration**:

  - Waves are physical and can be created [![Alt Text](images/daniel_palacio.png)](https://vimeo.com/12075151)
    *click image*.
    
    *A long piece of rope represents three dimensionally a series of waves floating in space, as well as producing sounds from the physical action of their movement: the rope which creates the volume also simultaneously creates the sound by cutting through the air, making up a single element. [... read more](www.danielpalacios.info)*
    
  - Sound waves can create visible patterns in materials like cornstarch.
  - ![Standing wave in cornstarch](images/standing_wave.jpg) 
  - **Reference**: [Standing Waves with Cornstarch](https://youtu.be/WaYvYysQvBU?si=hj87zU-DHQkleorG&t=113).  
  - **How it works**: Vibrations from sound waves cause the cornstarch mixture to form standing wave patterns.  
  - These patterns make the invisible vibrations of sound tangible and visible.  
- **Think About It**:  
  - How does seeing sound change your perception of it?  
  - How can these visual patterns inspire creative design?

## 2. The Art of Listening

How can sound add meaning to your work?

Artist/researcher Cathy Lane argues that listening tells us about what we cannot see particularly regarding people places and language and what can that tell us about social, cultural and political relationships?
- [Research - Cathy Lane](https://crisap.org/research/)

### Listening as a Skill
- Listening is more than hearing—it’s an act of attention and interpretation.
- Modes of listening:  
  - **Private Listening**: What you hear when alone.  
  - **Public Listening**: Shared sounds in a group or environment.  
  - **Selective Listening**: Focusing on one sound among many.  
  - **Partial Listening**: Being aware of sound without focusing fully.

### Key References
- **John Cage**: [*4’33”*](https://www.youtube.com/watch?v=yoAbXwr3qkg)   – Silence as a canvas for ambient sound. 
- **Alvin Lucier**: [*I Am Sitting in a Room*](https://www.youtube.com/watch?v=bhtO4DsSazc) – Transforming speech through resonance.

### Activity: Listening Exercise
1. Sit in silence for 5 minutes and focus on the sounds around you.  
2. Categorize the sounds you hear:  
   - Natural (e.g., birds, wind)  
   - Mechanical (e.g., air conditioning, traffic)  
   - Human-made (e.g., footsteps, voices)  
3. **Discuss**: How can these sounds inspire your creative work?

## 3. DIY Sound Exploration

### Making a Contact Microphone
- Contact microphones allow you to record hidden vibrations in objects.
- **What You Need**:  
  - Piezo buzzer, wires, tape, and a portable recorder or phone.

### How It Works
- **Piezoelectricity**:  
  - "It's amazing what a little disk can do ... when it's layered with piezoelectric crystals."  
  - Piezo disks are sensitive to vibrations and can be adapted to work as contact microphones.  
  - **Reference**: [Piezoelectric Contact Microphone Tutorial](https://www.youtube.com/watch?v=aOJuCYgmPPE&t=373s).

### Activity: Build and Explore
1. Build a contact microphone using the materials provided.  
2. Test it on objects around the classroom or campus (tables, doors, etc.).  
3. Record the vibrations and hidden sounds you discover.

### Discussion
- How do these hidden sounds evoke emotions or ideas?  
- Could they represent concepts like urbanization, resistance, or change?

## 4. Generative Sound Creation

### Introduction to Generative Sound
- Generative sound combines rules, randomness, and repetition to create evolving soundscapes.
- Tools we’ll explore:

  - **Strudel**: Quick and accessible generative music creation.   **OPEN IN GOGGLE CHROME ONLY** [Website here:](https://strudel.tidalcycles.org/)
  - Paste in this code and press play
 
#### Basic beat 60 cycles/sec

- bd = bass drum
- sd = snare drum
- rim = rimshot
- hh = hihat
- oh = open hihat
- lt = low tom
- mt = middle tom
- ht = high tom
- rd = ride cymbal
- cr = crash cymbal
- cp = clap

Paste these one at a time into strudl, only one sound will play at a time

1 - ``` sound("bd bd sn hh") ```

2 - ``` sound("[ ~ bd] bd bd [~ bd]")  ```

3 - ``` sound("hh*8 [sd cp]") ```

Want to know what the symbols mean? [Look Here](https://strudel.cc/workshop/first-sounds/#recap)

---

### Audio effects
[Here is a list of effects](https://strudel.tidalcycles.org/workshop/recap#audio-effects)

#### Stacking sounds
We use ```stack()``` ``` sound(), ``` notice the comma(,) after each sound. The sounds will be layered 

```
stack(
sound("[ ~ bd] bd bd [~ bd]"),
sound("hh*8 [sd cp]"),
)
```
Adding forward slashes ``` // ``` turns off individual lines; you can turn off specific sounds.
```
stack(
sound("[ ~ bd] bd bd [~ bd]"),
// sound("hh*8 [sd cp]"),
)
```
 
---
### How to get samples into strudl
[Upload samples](https://strudel.cc/learn/samples/#from-disk-via-import-sounds)

### Heres some code that will just work

```
  // Import your sounds by clicking 'Sounds->Import Sounds'
  // You import a folder with 2-3 samples
  //your_sound_folder_here is a folder and :0 is the FIRST sample 
  s("your_sound_folder_here:0")
```

A more complex sample and beats example  
Play with the numbers
```
stack(
  
s("your_audio_folder:0").begin("< 0.5 ~  0.25 ~ 0 ~ >"),
// s(" ~ cp"),
// s("hh*8").every(2, slow(2)),
//   s("bd bd bd bd ").every(2, slow(2)),
//   note("<c3 [eb3,g3] g2 [g3,bb3]>*8")
)
```

---
### Using remote files with strudl
Reference to samples [Here](https://strudel.tidalcycles.org/learn/samples#fit)

Upload your samples here: [CLICKME](https://forms.gle/fn3Mq7vYUfEuCJxx6)


You must alter the final part of the link url to bring in your sample ``` audio_things/certainsoundmono_01.mp3 ```
```
 certainSound: 'github:cuvner/gen-av/main/audio_things/certainsoundmono_01.mp3
```
```
await samples({
  bang: 'https://raw.githubusercontent.com/cuvner/gen-av/main/audio_things/certainsoundmono_01.mp3',
  daf: 'https://raw.githubusercontent.com/cuvner/gen-av/main/audio_things/daf.mp3'
});

s("daf")
  .splice(8, "0 1 [2 3 0]@2 3 0@2 7")
  .hurry(0.65);

```
```
await samples({
  bang: 'https://raw.githubusercontent.com/cuvner/gen-av/main/audio_things/certainsoundmono_01.mp3',
  daf: 'https://raw.githubusercontent.com/cuvner/gen-av/main/audio_things/daf.mp3'
});

s("daf")
  .splice(8, "0 1 [2 3 0]@2 3 0@2 7")
  .hurry(0.65);

```
```
samples({
  bang: 'https://raw.githubusercontent.com/cuvner/gen-av/main/audio_things/daf.mp3',
  bd: 'https://raw.githubusercontent.com/cuvner/gen-av/main/audio_things/certainsoundmono_01.mp3' // Example drum sound
});

stack(
  // Play the sample looped at 4 cycles
  //s("bang").loopAt(4),

  // Play the same sample looped at 2 cycles
 // s("bang").loopAt(2).hurry(1.5),

  // Add a beat with a drum sample
  //s("bd") // Simple 4-on-the-floor beat
);

```

---
    
  - **Sonic Pi**: Live coding platform for sound loops and manipulation. Requires downloading [Here:](https://sonic-pi.net/) 
  - **Python**: Online python coding with [Tune Pad](https://tunepad.com/interlude/pop-beat ).  
  - **p5.js**: The online p5js environment for creative coding see tutorials [here](https://www.youtube.com/watch?v=Bk8rLzzSink).
    try this for an example [Synth](https://editor.p5js.org/tom.smith/sketches/N16chLovz) or [this](https://editor.p5js.org/ivymeadows/sketches/B1FidNdqQ) 

### Activity Part 1: Editing Recorded Sounds
1. Use Audacity to edit your recordings:  
   - Loop, layer, and trim sounds to create patterns.  
2. Combine these edited sounds into generative systems using:  
   - **Strudel or Sonic Pi** for live coding.  
   - **Python or p5.js** for integration of visuals and sound.

### Activity Part 2: Group Collaboration
1. In teams, create a multi-layered generative soundscape.  
2. Suggested themes:  
   - "Hidden Vibrations"  
   - "Urban Resonance"  
3. Share your soundscapes with the group and discuss:  
   - How do generative processes tell a story or evoke emotion?

## 5. Reflection and Wrap-Up

### Discussion
- How can sound elevate visual design and storytelling?  
- What role does listening play in understanding and creating?

### Closing Exercise
- Write one sentence summarizing your experience or a key insight you gained.  
- Share your reflections with the group.

## Resources for Further Exploration

### Sound and Listening
- **John Cage**: [*4’33”*](https://www.youtube.com/watch?v=yoAbXwr3qkg)  
- **Alvin Lucier**: [*I Am Sitting in a Room*](https://vimeo.com/14617936)

### DIY Sound Tools
- John Grzinich: [Building Contact Microphones](https://maaheli.ee/main/building-contact-microphones/)  
- Piezoelectric Contact Mics: [Video Demonstration](https://www.youtube.com/watch?v=aOJuCYgmPPE&t=373s).

### Seeing Sound
- Cornstarch Standing Waves: [Demonstration Video](https://youtu.be/WaYvYysQvBU?si=hj87zU-DHQkleorG&t=113).

### Generative Sound Tools
- **Strudel**: [https://strudel.app](https://strudel.app)  
- **Sonic Pi**: [https://sonic-pi.net](https://sonic-pi.net)  
- **p5.sound library**: [https://p5js.org/reference/#/libraries/p5.sound](https://p5js.org/reference/#/libraries/p5.sound)

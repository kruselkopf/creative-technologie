# Project documentation Creative Technologie

![Visualisierung](https://github.com/user-attachments/assets/3c4625e9-369b-432f-8ca5-38f633e326de)


A project by Nick Steinmann

My project for the "Creative Technologies" module in the 5th semester of the MMP program. A creative exploration of an exhibition on the theme of "courage".

# An Interactive Installation
### (Video, Sound and Real-time processing)


Courage is an interactive installation created for a fictional exhibition. The project explores courage, self-expression, and the act of using one’s own voice in public.

A participant stands in front of a camera and holds a microphone. Their live image is projected onto a wall, visible to both the participant and the audience.

## Interaction

The participant is invited to shout into the microphone. The system reacts in real time:

- The **louder** the person shouts, the **higher a blue bar rises** in the background of the projection.
- When the person becomes quiet, the blue bar slowly sinks back down to a minimum.

The blue bar is directly connected to the voice. It reacts live and continuously to the sound level.

## Concept

The installation focuses on **courage as an action**.

Speaking loudly in public can feel uncomfortable, embarrassing, or risky. The participant is fully visible and observed while deciding how far they want to go.

The rising blue bar becomes a visual symbol for:

- speaking up  
- taking space  
- holding one’s ground  

The longer and louder the shout, the higher the bar remains.


## Why This Work Is Effective

Courage is simple and intuitive. No instructions are needed — the interaction is understood immediately. The work creates a mix of:

- playfulness  
- social pressure  
- emotional tension  

Each participant reacts differently. Some shout loudly, some hesitate, and others stop quickly.

## Usage
- download TD Document "260115_TD_Courage.12"
- open TD and follow the four comments in the document in order to set up the installation

In case the Media Pipe in TD does not work. Please replace the media pipe node with this file and relink the "image_segmentation".
https://fhgraubuenden-my.sharepoint.com/:f:/g/personal/steinmannick_fhgr_ch/IgAyRq-wak9MTaXyMjtPuyZcATu_JWoUWc4-ncJtu8Vd1zo?e=pXCoeC

## Communication diagram
<img width="1536" height="1024" alt="communication diagram" src="https://github.com/user-attachments/assets/2a862a75-c924-4ddf-b65d-4af1977c8cea" />

The microphone signal is processed through an Audio Device In CHOP, then analyzed using an Analyze CHOP to extract amplitude (RMS/peak). A Lag CHOP smooths rapid changes, and a Math CHOP normalizes and scales the signal.

Two Slider CHOPs and additional Math CHOPs control build-up and decay behavior of the signal. This mapped value drives the vertical scale of a Rectangle TOP, which forms the blue bar. Noise and displacement operators can be applied for visual modulation.

The camera feed enters via a Video Device In TOP and is passed into MediaPipe, which outputs segmentation masks. These masks split the image into person and background layers.
The person layer is masked and composited over the animated blue bar background using a Composite TOP. The final image is sent to a Video Out TOP for projection.

## Screeenshots and Pictures
<img width="1378" height="826" alt="Bildschirmfoto 2026-01-15 um 17 13 42" src="https://github.com/user-attachments/assets/66ae41b1-4312-4187-a19c-a58d305d24be" />
<img width="2512" height="1390" alt="Bildschirmfoto 2026-01-15 um 18 55 02" src="https://github.com/user-attachments/assets/b842ae33-0f50-4a58-ba42-93ae0435b594" />
<img width="2507" height="1388" alt="Bildschirmfoto 2026-01-15 um 18 54 51" src="https://github.com/user-attachments/assets/2234c600-11c9-46b6-8fe9-5de430dfb266" />
![IMG_3656 2](https://github.com/user-attachments/assets/f7c559d9-99c4-4e4d-8783-5836321b9a87)

## The "Making process"
I really enjoyed developing this project and learned a lot about TouchDesigner in the process. I especially liked that I was able to realise my own idea exactly the way I had imagined it. TouchDesigner offers an incredible range of possibilities, which is both inspiring and challenging. Because it was a new software for me, I had to learn many things from scratch, which sometimes made the process more difficult and exhausting.

It took me quite some time to find a working solution for the mask. I first found MediaPipe online, but the version I downloaded was far too large and complex for what I needed. It took several attempts before I fully. understood how to use it properly.

Setting up the lag for the movement of the bars was also challenging. I had to experiment for a long time before I found values that felt right and created a smooth but responsive motion. In addition, TouchDesigner kept crashing because MediaPipe was using too much memory. I solved this by disabling all unnecessary detection modules so that only the image segmentation remained active.

One very helpful input from my lecturer was the idea of using sliders to adjust the installation on site. This makes setting up the installation much easier and more flexible. It is a very simple idea, but extremely effective.

For future projects, I will take away that it is important to think about the installation already during the planning and production phase, not only about the concept and the visuals.

## Video
Here you can see the prototype in action: https://youtu.be/ikxfG56IXjg



   

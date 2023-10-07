Certainly! Below is a comparison table between the two configurations for rendering and enhanced portrait rendering:

| Parameter / Settings             | Configuration for Rendering VID1                | Configuration for Rendering VID2       |
|----------------------------------|---------------------------------------------|------------------------------------------------------|
| **General Settings**             |                                             |                                                      |
| Prompt                           | Close up Portrait photo...                  | Close-up portrait photo...                           |
| Seed                             | 3065812852                                  | 3065812852                                           |
| Run Options                      | Run All, Run 1st Key Frame, ...             | Run All, Run 1st Key Frame, ...                      |
| **1st Frame Translation Options**|                                             |                                                      |
| Frame Resolution                 | 512                                         | 512                                                  |
| ControlNet Strength              | 0.8                                         | 1.65                                                 |
| Denoising Strength               | 1 (0: fully recover, 1.05: fully rerender)  | 0.65 (0: Fully recover, 1.05: Fully rerender)        |
| Preserve Color                   | Yes                                         | Yes                                                  |
| Crop Length                      | Left 0, Right 0, Top 0, Bottom 0            | Left 0, Right 0, Top 0, Bottom 0                     |
| Control Type                     | Canny (50, 100)                             | Canny (100, 200)                                     |
| Steps                            | 25                                          | 40                                                   |
| CFG Scale                        | 4.5                                         | 4.5                                                  |
| Base Model                       | icbinpICantBelieveIts_seco                  | icbinpICantBelieveIts_seco                           |
| Added Prompt                     | best quality, ...                           | Best quality, ...                                    |
| Negative Prompt                  | bald, forehead, ...                         | Bald, forehead, ...                                  |
| FreeU 1st-stage Backbone Factor  | 1                                           | 1                                                    |
| FreeU 2nd-stage Backbone Factor  | 1                                           | 1                                                    |
| FreeU 1st-stage Skip Factor      | 1                                           | 1                                                    |
| FreeU 2nd-stage Skip Factor      | 1                                           | 1                                                    |
| **Key Frame Translation Options**|                                             |                                                      |
| Key Frame Frequency (K)          | 2                                           | 3                                                    |
| Number of Key Frames             | 59                                          | 39                                                   |
| Cross-frame Constraints          | shape-aware fusion, ...                     | Shape-aware fusion, ...                              |
| Cross-frame Attention            | Start 0, End 1, Update every 5 frames       | Start 0, End 1, Update every 1 frames               |
| Loose Cross-frame Attention      | Yes                                         | Yes                                                  |
| Shape-Aware Fusion               | Start 0, End 0.1                            | Start 0, End 0.1                                     |
| Pixel-Aware Fusion               | Start 0.5, End 0.8, Strength 0.5, ...       | Start 0.5, End 0.8, Strength 0.5, ...                |
| Color-Aware AdaIN                | Start 1, End 1                              | Start 1, End 1                                       |
| Smooth Fusion Boundary           | Yes                                         | Yes                                                  |
| **Full Video Translation Options**|                                            |                                                      |
| Gradient Blending                | Yes                                         | Yes                                                  |
| Number of Parallel Processes     | 5                                           | 4                                                    |
| Est. Render Time     |                                            | 1.7 hrs                                             |

---

# Prompt
Close up Portrait photo of a happy smiling beautiful 30 year old woman in a worn mech suit, ((light bokeh)), intricate, (steel metal [rust]), elegant, sharp focus, photo by Greg Rutkowski, soft lighting, vibrant colors, masterpiece, ((streets)), detailed face

# Seed
3065812852

# Run All
- Run 1st Key Frame
- Run Key Frames
- Run Propagation

# Advanced options for the 1st frame translation
- Frame resolution: 512
- ControlNet strength: 1.65
- Denoising strength: 0.75
- Preserve color: true
- Left crop length: 0
- Right crop length: 0
- Top crop length: 0
- Bottom crop length: 0
- Control type: canny
  - Canny low threshold: 100
  - Canny high threshold: 200
- Steps: 20
- CFG scale: 4.5
- Base model: icbinpICantBelieveIts_seco
- Added prompt: best quality, extremely detailed, full thick hair
- Negative prompt: bald, forehead, nude, cross-eyed, inside, 3d, cartoon, anime, sketches, (worst quality:2), (low quality:2), (normal quality:2), lowres, normal quality, ((monochrome)), ((grayscale)), skin spots, acnes, skin blemishes, bad anatomy, red eyes
- FreeU first-stage backbone factor: 1
- FreeU second-stage backbone factor: 1
- FreeU first-stage skip factor: 1
- FreeU second-stage skip factor: 1

# Advanced options for the key frame translation
- Key frame frequency (K): 1
- Number of key frames: 74
- Select the cross-frame constraints to be used:
  - shape-aware fusion: true
  - pixel-aware fusion: true
  - color-aware AdaIN: true
- Cross-frame attention start: 0
- Cross-frame attention end: 1
- Cross-frame attention update frequency: 1
- Loose Cross-frame attention: true
- Shape-aware fusion start: 0
- Shape-aware fusion end: 0.1
- Pixel-aware fusion start: 0.5
- Pixel-aware fusion end: 0.8
- Color-aware AdaIN start: 1
- Color-aware AdaIN end: 1
- Pixel-aware fusion strength: 0.5
- Pixel-aware fusion detail level: 0.5
- Smooth fusion boundary: true

# Advanced options for the full video translation
- Gradient blending: true
- Number of parallel processes: 4

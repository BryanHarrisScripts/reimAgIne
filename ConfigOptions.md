- High ControlNet strength
- Low Denoising strength
- Low Key frame frequency for video with quick motions
- Activate loose-cross-frame-attention:
- https://github.com/williamyang1991/Rerender_A_Video#loose-cross-frame-attention

Title: Estimating Rendering Time Based on Specific Configuration Settings

---

In this post, we aim to provide a simplified method to estimate the rendering time based on specific configuration settings. It's important to note that this method involves a lot of assumptions and may not provide exact results but should serve as a reasonable ballpark estimate.

### Configuration Settings Utilized for Estimation:
- ControlNet strength: 0.8
- Denoising strength: 1 (0: fully recover the input, 1.05: fully rerender the input)
- Steps: 25
- CFG scale: 4.5
- Key frame frequency (K): 2
- Number of key frames: 59
- Update frequency every N key frames: 5
- Loose Cross-frame attention: Yes
- Number of parallel processes: 5 (This will always be set to 5)

### Pre-requisites for Estimation:
- Understanding of Key Frame Frequency and Number of Key Frames: The "Key Frame Frequency (K)" implies a key frame will be generated every K frames, and "Number of Key Frames" implies the total number of key frames to be generated. Therefore, the total number of frames to be processed would be \(K \times \text{Number of Key Frames}\). In this example, it is \(2 \times 59 = 118\).
  
- Time taken to process each frame: Based on the data provided, the time taken to process each frame ranged from 32 to 34 seconds per run, with each frame having two runs. This totals to an average of 33 seconds per frame.

### Estimation Steps:

1. **Calculate the Total Rendering Time in Seconds:**
   \[ \text{Total Rendering Time (Seconds)} = \text{Total Number of Frames} \times \text{Average Time per Frame (Seconds)} \]
   \[ \text{Total Rendering Time (Seconds)} = 118 \times 33 = 3,894 \]

2. **Convert the Total Rendering Time to Hours:**
   \[ \text{Total Rendering Time (Hours)} = \frac{\text{Total Rendering Time (Seconds)}}{3600} \]
   \[ \text{Total Rendering Time (Hours)} ≈ \frac{3,894}{3600} ≈ 1.08 \]

### Conclusion:
With the updated configuration settings and the new average time per frame, the estimated total rendering time is approximately 1.08 hours or about 65 minutes. This estimation assumes that the time to process each frame remains consistent throughout the rendering process.

---

This method is simplified and does not take into account potential variations in frame processing time, system performance, or other factors that may affect rendering time. It's advised to monitor actual rendering times and adjust estimates accordingly for future projects.

---

Here's a comparative analysis between the configuration provided above and the previously suggested configuration for a 2-hour rendering target:

**Title: Comparative Analysis for 2-hour Rendering Target**

---

**Advanced options for the 1st frame translation:**

| Parameter                       | Original Configuration | Suggested Configuration for 2-hour Render |
|---------------------------------|------------------------|-------------------------------------------|
| Frame resolution                | 512                    | 512                                       |
| ControlNet strength             | 0.8                    | 0.65                                      |
| Denoising strength              | 1                      | 1                                         |
| Steps                           | 25                     | 37                                        |
| CFG scale                       | 4.5                    | 4.5                                       |
| Control type                    | Canny                  | Canny                                     |
| Preserve color                  | Yes                    | Not Provided                              |
| Crop Length                     | 0, 0, 0, 0             | Not Provided                              |
| Base model                      | icbinpICantBelieveIts_seco | Not Provided                         |
| Added prompt                    | Best quality, extremely detailed, full thick hair | Not Provided |
| Negative prompt                 | Various                | Not Provided                              |
| FreeU first-stage backbone factor | 1                    | Not Provided                              |
| FreeU second-stage backbone factor | 1                    | Not Provided                              |
| FreeU first-stage skip factor   | 1                      | Not Provided                              |
| FreeU second-stage skip factor  | 1                      | Not Provided                              |

**Advanced options for the key frame translation:**

| Parameter                       | Original Configuration | Suggested Configuration for 2-hour Render |
|---------------------------------|------------------------|-------------------------------------------|
| Key frame frequency (K)         | 2                      | 2.5                                       |
| Number of key frames            | 59                     | 49                                        |
| Cross-frame constraints         | Various                | Not Provided                              |
| Cross-frame attention           | 0, 1, 5               | 0, 1, 7.5                                 |
| Loose Cross-frame attention     | Yes                    | Not Provided                              |
| Shape-aware fusion              | 0, 0.1                 | 0, 0.1                                    |
| Pixel-aware fusion              | 0.5, 0.8, 0.5, 0.9     | 0.5, 0.8, 0.5, 0.9                         |
| Color-aware AdaIN               | 1, 1                   | 1, 1                                      |
| Smooth fusion boundary          | Yes                    | Not Provided                              |

**Advanced options for the full video translation:**

| Parameter                       | Original Configuration | Suggested Configuration for 2-hour Render |
|---------------------------------|------------------------|-------------------------------------------|
| Gradient blending               | Yes                    | Not Provided                              |
| Number of parallel processes    | 5                      | 4.5                                       |

---

In summary, the suggested configuration for a 2-hour rendering target primarily modifies the ControlNet strength, Steps, Key frame frequency (K), Number of key frames, and Cross-frame attention update frequency to try and balance rendering time with quality. Some parameters from the original configuration were not provided in the suggested settings, like Preserve color, Base model, Added/Negative prompts, FreeU factors, and Gradient blending. The effectiveness of these changes would need to be tested in the actual rendering software to determine the impact on rendering time and quality.

---

Certainly! Here are your updated configuration options:

**Title: Configuration for Rendering**

---

**General Settings:**
- Prompt: Close up Portrait photo of a happy smiling beautiful woman in a worn mech suit, ((light bokeh)), intricate, (steel metal [rust]), elegant, sharp focus, photo by Greg Rutkowski, soft lighting, vibrant colors, masterpiece, ((streets)), detailed face
- Seed: 3065812852
- Run Options: Run All, Run 1st Key Frame, Run Key Frames, Run Propagation

---

**Advanced options for the 1st frame translation:**
- Frame resolution: 512
- ControlNet strength: 0.8
- Denoising strength: 1 (0: fully recover the input, 1.05: fully rerender the input)
- Preserve color: Yes
- Crop Length: Left 0, Right 0, Top 0, Bottom 0
- Control type: Canny (Low threshold: 50, High threshold: 100)
- Steps: 25
- CFG scale: 4.5
- Base model: icbinpICantBelieveIts_seco
- Added prompt: best quality, extremely detailed, full thick hair
- Negative prompt: bald, forehead, nude, cross-eyed, inside, 3d, cartoon, anime, sketches, (worst quality:2), (low quality:2), (normal quality:2), lowres, normal quality, ((monochrome)), ((grayscale)), skin spots, acnes, skin blemishes, bad anatomy, red eyes
- FreeU first-stage backbone factor: 1
- FreeU second-stage backbone factor: 1
- FreeU first-stage skip factor: 1
- FreeU second-stage skip factor: 1

---

**Advanced options for the key frame translation:**
- Key frame frequency (K): 2
- Number of key frames: 59
- Cross-frame constraints: shape-aware fusion, pixel-aware fusion, color-aware AdaIN
- Cross-frame attention: Start 0, End 1, Update frequency every N key frames: 5
- Loose Cross-frame attention: Yes
- Shape-aware fusion: Start 0, End 0.1
- Pixel-aware fusion: Start 0.5, End 0.8, Strength 0.5, Detail level 0.9 (Use a low value to prevent artifacts)
- Color-aware AdaIN: Start 1, End 1
- Smooth fusion boundary: Yes

---

**Advanced options for the full video translation:**
- Gradient blending: Yes
- Number of parallel processes: 5

---

These configurations are aimed at achieving a rendering of a close-up portrait as described in the prompt, with specific parameters set to ensure quality and manage the rendering process across different stages of the translation.

Title: Configuration for Enhanced Portrait Rendering

- **Prompt**: Close-up portrait photo of a joyful, beautiful woman donned in a rustic mech suit, accompanied by light bokeh, intricate steel metal rust, elegant aesthetics, precise focus, captured by Greg Rutkowski, soft lighting, vibrant colors, a masterpiece backdrop of streets, and a finely detailed face.
- **Seed**: 3065812852
- **Run Options**: Run All, Run 1st Key Frame, Run Key Frames, Run Propagation

**Advanced Options for the 1st Frame Translation**:
- Frame Resolution: 512
- ControlNet Strength: 1.65
- Denoising Strength: 0.65 (0: Fully recover the input, 1.05: Fully rerender the input)
- Preserve Color: Yes
- Crop Length: Left 0, Right 0, Top 0, Bottom 0
- Control Type: Canny (Low Threshold: 100, High Threshold: 200)
- Steps: 40
- CFG Scale: 4.5
- Base Model: icbinpICantBelieveIts_seco
- Added Prompt: Best quality, extremely detailed, full thick hair
- Negative Prompt: Bald, forehead, nude, cross-eyed, inside, 3D, cartoon, anime, sketches, (worst quality:2), (low quality:2), (normal quality:2), lowres, normal quality, (monochrome), (grayscale), skin spots, acne, skin blemishes, bad anatomy, red eyes
- FreeU First-Stage Backbone Factor: 1
- FreeU Second-Stage Backbone Factor: 1
- FreeU First-Stage Skip Factor: 1
- FreeU Second-Stage Skip Factor: 1

**Advanced Options for the Key Frame Translation**:
- Key Frame Frequency (K): 3
- Number of Key Frames: 39
- Selected Cross-Frame Constraints: Shape-aware fusion, Pixel-aware fusion, Color-aware AdaIN
- Cross-Frame Attention: Start 0, End 1, Update Frequency every N Key Frames: 1
- Loose Cross-Frame Attention: Yes
- Shape-Aware Fusion: Start 0, End 0.1
- Pixel-Aware Fusion: Start 0.5, End 0.8, Strength 0.5, Detail Level 0.9 (Use a low value to prevent artifacts)
- Color-Aware AdaIN: Start 1, End 1
- Smooth Fusion Boundary: Yes

**Advanced Options for the Full Video Translation**:
- Gradient Blending: Yes
- Number of Parallel Processes: 4

The outlined configuration is tailored for rendering a portrait with enhanced details and aesthetics, utilizing specified network models and processing parameters.

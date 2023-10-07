| Parameter / Settings             | Configuration for Rendering VID1           | Configuration for Rendering VID2      | New Configuration                      |
|----------------------------------|---------------------------------------------|---------------------------------------|----------------------------------------|
| **General Settings**             |                                             |                                       |                                        |
| Prompt                           | Close up Portrait photo...                  | Close-up portrait photo...            | Close up Portrait photo of a happy...  |
| Seed                             | 3065812852                                  | 3065812852                            | 3065812852                             |
| Run Options                      | Run All, Run 1st Key Frame, ...             | Run All, Run 1st Key Frame, ...       | Run All, Run 1st Key Frame, ...        |
| **1st Frame Translation Options**|                                             |                                       |                                        |
| Frame Resolution                 | 512                                         | 512                                   | 512                                    |
| ControlNet Strength              | 0.8                                         | 1.65                                  | 1.65                                   |
| Denoising Strength               | 1 (0: fully recover, 1.05: fully rerender)  | 0.65 (0: Fully recover, 1.05: Fully rerender) | 0.75                             |
| Preserve Color                   | Yes                                         | Yes                                   | True                                   |
| Crop Length                      | Left 0, Right 0, Top 0, Bottom 0            | Left 0, Right 0, Top 0, Bottom 0      | Left 0, Right 0, Top 0, Bottom 0       |
| Control Type                     | Canny (50, 100)                             | Canny (100, 200)                      | Canny (100, 200)                       |
| Steps                            | 25                                          | 40                                    | 20                                     |
| CFG Scale                        | 4.5                                         | 4.5                                   | 4.5                                    |
| Base Model                       | icbinpICantBelieveIts_seco                  | icbinpICantBelieveIts_seco            | icbinpICantBelieveIts_seco             |
| Added Prompt                     | best quality, ...                           | Best quality, ...                     | Best quality, extremely detailed, ...  |
| Negative Prompt                  | bald, forehead, ...                         | Bald, forehead, ...                   | Bald, forehead, nude, ...              |
| FreeU 1st-stage Backbone Factor  | 1                                           | 1                                     | 1                                      |
| FreeU 2nd-stage Backbone Factor  | 1                                           | 1                                     | 1                                      |
| FreeU 1st-stage Skip Factor      | 1                                           | 1                                     | 1                                      |
| FreeU 2nd-stage Skip Factor      | 1                                           | 1                                     | 1                                      |
| **Key Frame Translation Options**|                                             |                                       |                                        |
| Key Frame Frequency (K)          | 2                                           | 3                                     | 1                                      |
| Number of Key Frames             | 59                                          | 39                                    | 74                                     |
| Cross-frame Constraints          | shape-aware fusion, ...                     | Shape-aware fusion, ...               | Shape-aware fusion, pixel-aware fusion, ... |
| Cross-frame Attention            | Start 0, End 1, Update every 5 frames       | Start 0, End 1, Update every 1 frames | Start 0, End 1, Update every 1 frames  |
| Loose Cross-frame Attention      | Yes                                         | Yes                                   | True                                   |
| Shape-Aware Fusion               | Start 0, End 0.1                            | Start 0, End 0.1                      | Start 0, End 0.1                       |
| Pixel-Aware Fusion               | Start 0.5, End 0.8, Strength 0.5, 0.9       | Start 0.5, End 0.8, Strength 0.5, 0.9 | Start 0.5, End 0.8, Strength 0.5, 0.5   |
| Color-Aware AdaIN                | Start 1, End 1                              | Start 1, End 1                        | Start 1, End 1                         |
| Smooth Fusion Boundary           | Yes                                         | Yes                                   | True                                   |
| **Full Video Translation Options**|                                            |                                       |                                        |
| Gradient Blending                | Yes                                         | Yes                                   | True                                   |
| Number of Parallel Processes     | 5                                           | 4                                     | 4                                      |
| Est. Render Time                 |                                             | 1.7 hrs                                |                                        |


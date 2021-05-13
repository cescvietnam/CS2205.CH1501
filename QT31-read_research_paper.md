## HSA-RNN: Hierarchical Structure-Adaptive RNN for Video Summarization

### Problem/motivation
- Video summarization: input long video, output short video with important portions kept.
- Video summarization is in the need because of huge amount of video created daily.
- Video has structure: they include several shots and each shot include several frame.
- Current techniques don't exploit this structure or don't do it properly (e.g., fixed length shot)
![alt text](https://github.com/cescvietnam/CS2205.CH1501/blob/main/images/QT31_Problem.jpg?raw=true)

### Questions
- How shots boundary can be detected properly?
- How detected shots can be chosen correctly?

### Solution
- Using sliding bidirectional LSTM in the 1st layer to detect shots boundaries.
- Using bidirectional LSTM in the 2nd layer to define the probability of that shot (detected in 1st layer) to be kept in summarized video.
- Feature extraction: shallow shallow (color histogram, SIFT and optical flow) or deep features (fc7 layer of VGGnet-16)
![alt text](https://github.com/cescvietnam/CS2205.CH1501/blob/main/images/QT31_solution.jpg?raw=true)

#### Why using bidirectional LSTM in the 1st layer to detect shots boundaries? Why can't we apply a normal LSTM and a thresh hold?
- Not only forward information information is important but frames come after a boundary are important also. So we need bidirectional LSTM
- Setting threshold is hard and also destroy differentiability (not able to use gradient descent for training)
- Sliding allow "local information only".

#### Detail information of sliding bidirectional LSTM in layer 1
- Length k=240 (experimental value in the paper).
- Stride = length of detected shot at each step

#### Training technique
- 1st layer is pre-trained to detect the boundaries correctly.
- After 1st layer is pre-trained, it's fixed and 2nd layer is trained to achieve good summarization.
- Final step is fine tuning with both layers.

### Result
- Metrics: precision (P), recall (R), F-measure (F). Note: a generated shot is correct if the reference shot share more than 50% with its duration
- Outperform previous methods
- Deep features give better result compared to shallow features.

### Limitation
- Each shot can be shot but can't be too long (limited to the setting of k, with k=240 -> shot length limitted at 10s).
- There is always a boundary in every k frames.
- Feature extraction is neccassary
- 

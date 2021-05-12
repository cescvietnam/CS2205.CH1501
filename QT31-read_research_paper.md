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
![alt text](https://github.com/cescvietnam/CS2205.CH1501/blob/main/images/QT31_solution.jpg?raw=true)

### Result
- Metrics: precision (P), recall (R), F-measure (F). Note: a generated shot is correct if the reference shot share more than 50% with its duration
- 

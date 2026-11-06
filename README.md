# Ski Feedback

## Goal
Analyzes skiing videos and checks the technique for typical mistakes, aimed especially at beginners. 7 videos are used at the beginning to build the pipeline; more videos will be added later to evaluate it.

## How it works
The skier's skeleton is tracked with a pretrained pose estimation model. The extracted keypoints are used to detect individual turns and their direction. Rules based on my ski instructor knowledge then check each turn for one mistake: leaning into the hill instead of angulating. The result is shown as feedback in the video.

## Plan
1. Pose extraction (~Nov 22): video → keypoints → annotated video + stick-figure render
2. Turn detection (~Dec 6): turns detected on the 7 videos
3. Lean rule (~Dec 20): lean metric + threshold, per-turn verdict in the video
4. Filming and labeling (Dec 24 – Jan 6): new videos from a consistent camera angle (front or behind), different skiers, every turn labeled. No snow yet 🥲
5. Evaluate and polish (~Jan 15): rule accuracy on the new videos, demo GIF, README → v1 done

## Definition of done (v1)
- One command takes a video and outputs an annotated video with the turns and a verdict per turn
- Evaluated on labeled turns from the new videos, accuracy reported
- Demo GIF (stick figure) and README finished

## Ideas for later
- Trained classifier on the skeleton data, compared to the rules
- Real-time feedback on laptop/phone
- More mistakes (leaning back, hands too low, ...)
- 3D model of the skier

## How I built this
This is my first own project. I use Claude Opus 5.5 as a mentor: it explains concepts, reviews my code and helps me keep the scope small, but I write the code myself. My goal is to understand every part of the pipeline and be able to explain it.

## Status
- [x] Project setup (uv, libraries, GitHub repo)
- [ ] Next: pose extraction
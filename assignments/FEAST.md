# COMP 6001 Neuromorphic Algorithms and Computation 
## Week 8 - Tutorial 6 – ML and Feature Extraction 
### Q1. 
Many popular ML methods used for feature extraction in neuromorphic vision data involve networks with similarities to 
Self-Organising Maps, particularly algorithms such as FEAST and HOTS. At their core, these feature extraction algorithms work to
cluster event contexts (a neighbourhood surrounding the most recent event). When an event is received, the neuron which the 
incoming event context most closely resembles ‘spikes’. In a winner-take-all style approach, the spiking neuron weight is 
updated/mixed with the event context (as a function of the learning rate) to gradually learn the common features. 
Implement a basic neuron-based feature extraction algorithm with this approach. The algorithm should: 

## Initialise 9 random 11x11 weights 

Create a time surface of the incoming event stream 
Extract the event context from the time surface (with the same dimensions as the weights) 
Check which neuron is the most similar (cosine distance) 
Update the neuron weight 

Repeat 
### Q2. 
Profile and evaluate this system, how scalable is it? What are the most costly components of the algorithm? 
### Q3. 
What alternate approaches can be used here? What update/learning calculation or similarity metric could be more beneficial? 

Example FEAST Network neurons extracting and clustering features from the EBC Plane Dropping dataset (Afshar, S., Ralph, N., Xu, Y., Tapson, J., Schaik, A.V. and Cohen, G., 2020. Event-based feature extraction using adaptive selection thresholds. Sensors, 20(6), p.1600.) 

 

 

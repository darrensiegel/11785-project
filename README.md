# Deep Learning in Elixir
## 11785 project / Fall 2024

This repository contains the code written for my 11785 course project "Deep Learning in Elixir". 

The `.livemd` files in this repository are Elixir LiveBook instances, which can be run directly
from a locally running LiveBook server using their GitHub URLs.  

### hw1pt2.livemd

This replicates 11785 HW1PT2, the phoneme classification task using simple, feedforward only networks. 
The goal here was to assess `Nx`, `Axon` and Livebook - paying particular attention to performance
issues (downloading and working with the gigabytes of MFCC data)

### transfer-learning.livemd

This implements a custom image classification model by fine tuning ResNet-50 for a three class
classification task - namely classifying images betwen "contains a screenshot of tabular information",
"contains a screenshot of source code" and "other". 

The model in this transfer learning LiveBook is fine tuned and then these weights are saved to an S3 bucket.  From there,
an experimental branch of Torus (https://github.com/Simon-Initiative/oli-torus/tree/11785) integrates
serving this model for inference purposes (by first downloading the fine tuned weights and then
serving them via `Nx.Serving`) as a first class feature of the Torus "Media Library"



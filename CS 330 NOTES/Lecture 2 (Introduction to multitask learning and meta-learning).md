### What is a task?
1. a task: data generating distribution; labels distribution conditioned on data; the loss function;
2. examples of tasks: multi-task classification; multi-label learning;

### task descriptor
1. how should we condition on task descriptor;
2. two extremes: multiplacate gating; concatenate task descriptor with input or activations;
3. an alternate view of multi-task objective: split theta into shared parameters and task-specific parameters;
4. choosing how to condition on task descriptor is equivalent to choosing how and where to share parameters;
5. conditioning, some common choices: concatenation and additive conditioning; multi-head architecture; multiplicative
conditioning (multiplicative gating);
6. conditioning, more complex choices: cross-stitch networks for multi-task learning; multi-task attention networks; 
deep relation networks; multilinear relationship networks; sluice networks;
7. unfortunately: these design decisions are like neural network architecture tuning, they are problem dependent, largely
guided by intuition or knowledge of the problem, and currently more of an art than a science;

### challenge #1: negative transfer
1. sometimes independent networks work the best: multi-task CIFAR100; 
2. why: optimization challenges (cross task interference; tasks may learn at different rates); limited representational 
capacity;

### challenge #2: overfitting
1. multitask learning is a form of regularization;

### Case study: recommending which video to watch next: a multitask ranking system
1. conflicting objectives: videos that users rate highly, will watch, and will share; 
2. implicit bias caused by feedback;
3. central topic of this paper: vido candidates ranking;
4. model outputs: engagements and satisfaction with candidate videos;
5. weighted combination of engagement and satisfacion predictions, and score weights are manually tuned;
6. architecture: multi-gate mixture-of-experts (MMoE);

### meta-learning: a probabilistic view
1. learning a new task using prior information extracted from a set of meta-training tasks and small training set to
infer mostly likely posterior parameters;
2. problem definition: maximize the log posterior distribution of theta given meta-training data and new dataset;
3. learn meta-parameters theta and task-specific parameters given testing data and theta;

### A quick example
1. two steps: meta-learning and adapatation;
2. key idea: test and train must match (from Matching Networks for One-Shot Learning);
3. the complete meta-learning optimization;
4. some meta-learning terminology;
5. closely related problem settings: multi-task learning (learn model with parameters theta that solves multiple tasks); 
hyperparameter optimization; auto-ml.

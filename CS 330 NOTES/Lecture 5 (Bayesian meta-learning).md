### Recap from last time
1. Algorithmic properties perspective: expressive power (scalability, applicability to a range of domains); consistency (reduce
reliance on meta-training tasks, good OOD task performance); uncertainty awareness;

### Let f output the parameters of a distribution over testing labels
1. examples: probability values of discrete categorical distribution; means, variances, and mixture weights of a mixture of 
Gaussians; for multidimensional testing labels, parameters of a sequence of distributions (i.e. autoregressive models);
2. pros: can combine with a variaty of methods; simple;
3. cons: can't reason about uncertainty over the underlying function (to determine how uncertainty across datapoints relate);
limited class of distributions over training labels can be expressed; tends to produce poorly-calibrated uncertainty estimates;

### The Bayesian deep learning toolbox
1. goal: represent distributions with neural networks;
2. latent variable models + variational inference;
3. Bayesian ensembles;
4. Bayesian neural networks;
5. Normalizing flows;
6. Energy-based models and GANs;

### Latent variable models + variational inference
1. amortized variational inference: ELBO; p(x|z) can be represented as a neural network, p(z) can be represented as Gaussian
distributions, q(z|x) can be represented as inference networks; reparameterzation trick;
2. Bayesian black-box meta-learning: from VAE to meta-learing, final objective; pros and cons (non-Gaussian distribution
over y; can only represent Gaussian distribution over parameters);
3. optimization-based meta-learning: Bayesian interpretation of MAML (gradient descent with early stop is MAP inference);
4. q corresponds to SGD on the mean and variance of neural network weights (q is an arbitrary function); pros and cons (
running gradient descent as test time; p phi given theta is modeled as a Gaussian); paper (amortized Bayesian meta-learning);

### Ensembles
1. Bayesian MAML;
2. Ensemble of MAMLs (won't work if ensemble MAMLs are too similar);
3. Stein variational gradient (BMAML): use stein variational gradient (SVGD) to push particles away from one another; pros 
and cons (simple, tends to work well, non-Gaussian distributions; need to maintain M model instances);

### Sample parameter vectors with a procedure like Hamitonian Monte Carlo
1. learn a prior where a random kick could put us in a different mode;
2. ancestral sampling; pros and cons (non-Gaussian posterior, simple at test time, only one model instance; more complex 
training procedure);

### How to evaluate a Bayesian meta-learner
1. standard benchmarks: metrics like accuracy don't evaluate uncertainty; tasks may not exhibit ambiguity; uncertainty may
not be useful in this dataset;
2. Qualitative evaluation on toy problems with ambiguity;
3. Evaluation on ambiguous generation tasks;
4. Accuracy, Mode Coverage, & Likelihood on Ambiguous Tasks;
5. Reliability Diagrams & Accuracy;
6. Active learning evaluation.

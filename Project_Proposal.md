		In unsupervised learning we generally want to uncover dependencies in data in order to learn its “structure.” It is
	especially nice when a model is “generative”, meaning that it attempts to learn the underlying function that generates a
	particular data. Real data is usually noisy, so finding a way to extract the meaningful factors that explain the data while
	ignoring the noise is a core task of unsupervised learning. PCA and ICA are examples of techniques that attempt to
	distinguish the “most important” factors in data. PCA does this be successfully identifying the next factor, “component”
	that maximally explains the variance in the data. intuitively, Data exists in some relatively high dimensional space, but
	the useful information is contained in a lower dimensional subspace. PCA tries to learn this subspace. One implicit
	assumption made in PCA models is that the feature vector is a multivariate gaussian distribution. A similar technique, ICA,
	“Independent Component Analysis” does not depend on this assumption. The strategy for learning underlying structure from
	ICA is similar, where in each step we seek to select “components so that the distribution of their loadings carries a
	maximum amount of independent information. It is able to recover non-Gaussian independent signals. 
	
		A novel approach to this task called “The Information Sieve” was recently proposed by Greg Ver Steeg and Aram
	Galstyan this year in a paper with the same name (https://arxiv.org/pdf/1507.02284v3.pdf).  Inspired by information theory,
	the underlying intuition is that we can incrementally decompose some data generating function, at each step capturing the
	“latent variable” that contributes most to “total correlation”. Then we can remove this signal and passes on “remainder
	information,” information in X that was not captured by y, where y is the latent factor previously uncovered. The previous
	remainder is all that is used in each step, removing redundant computation. Ideally we are left with only unexplainable
	noise. Steeg assessed several application areas in discrete valued problems such as ICA, lossy and lossless compression.
	Steeg has now also open-sourced code that extends the Information Sieve to continuous valued problems. The major appeals of
	this method are its exponentially faster runtime that ICA (although without guarantees of optimality) and the
	interpretability of results. 
	
		As a new technique with substantial promise and relative simplicity, we believe there is a good opportunity to dive
	deeper into this technique, testing applications to new problems. We also hope to find ways to make this technique more
	viable for large data sets. 





# PIMOE-Physics-informed-mixture-of-experts-for-battery-degradation-trajectory-computation
As electric vehicle batteries reach end-of-life, their residual capacity presents substantial opportunities for second-life applications. However, ensuring safe and sustainable reuse remains challenging due to the absence of historical data and the uncertainty of future operating conditions. Conventional models often rely on consistent use profiles and complete cycling histories, which are rarely available in real-world practice. This study introduces a Physics-Informed Mixture of Experts (PIMOE) framework that classifies internal degradation modes from partial, field-accessible signals, such as voltage relaxation and partial charging data, captured at random states of charge regions. Integrating assumed future use scenarios, PIMOE enables accurate, long-horizon degradation trajectory computation without prior cycling data records. Its interpretable architecture reveals latent degradation modes that correspond to external trajectory geometry, serving as initial points for iterative degradation trajectory computation in extended second-life uses. This physics-informed approach bridges data-driven modeling with domain knowledge, offering a scalable, explainable, and computationally efficient tool for second-life battery deployment. The PIMOE holds broad implications for proactive fault detection, reliability assessment, and the durable operation of critical infrastructures such as grid-scale energy storage systems and massive electric vehicles.

## Highlights
- Physics-informed mixture of experts (PIMOE) network for battery degradation trajectories computation.
- Adaptive multi-degradation prediction (AMDP) module for latent degradation trend representation.
- Future use-dependant degradation trajectories computation within a millisecond per battery.
- Interpretability, generalizability and accessibility for safe and sustainable second-life uses.


# 1. Setup
## 1.1 Enviroments
* Python (Jupyter notebook) 
## 1.2 Python requirements
* python=3.11.5
* numpy=1.26.4
* torch=2.4.1
* keras=2.15.0
* matplotlib=3.9.2
* scipy=1.13.1
* scikit-learn=1.3.1
* pandas=2.2.2

# 2. Datasets
The raw data can be accessed via the following link:
* [TPSL-Dataset](https://data.mendeley.com/datasets/kw34hhw7xg/2)
* [UL-Dataset](https://doi.org/10.5281/zenodo.6379165)

# 3. Demo
We provide a detailed demo of our code running on the TPSL dataset.
1. Run the `run.py` file to train our model. The program will generate a folder named `checkpoint` and save the results in it.
2. You can change `setattr(args,'dataset')` to select the UL or TPSL datasets. It will generate a folder in the `checkpoint` to save the results of the corresponding datasets (UL or TPSL).
4. Run the `PolynomialFeatures.ipynb` file will generate predictions of degradation trajectories under the condition that historical data is known and future operating conditions remain constant. The results will be save it in the `results` folder.

**Note: The results presented in this paper were not obtained through specific hyperparameter optimization. You may experiment with alternative hyperparameters to achieve similar or potentially improved outcomes.
Due to the inherent stochasticity of neural networks, the acquired expert weights will not remain identical across different runs. However, it is evident that significant differences exist among distinct aging stages.**

In addition, we also provide the results of our training, 
which are saved in the `checkpoint` folder.
These results correspond exactly to the data in our manuscript.

What's more, we also provide the codes corresponding to the Figures in our manuscript, 
which are saved in the `Fig 3c-Fig 5d` folder.
You can use these codes to draw the Figures in the manuscript.
## Acknowledgement
This repo is constructed based on the following repos:
- https://github.com/thuml/Time-Series-Library

# large-scale-magnetic-mapping
Here are the 4 datasets _Corridor_, _Simu1D_,  _Simu2D_,  _Simu3D_ used in our article [1] to fit and test our map model. Each row of the csv contains the 3D position $x_0,x_1,x_2$ and the magnetic field 3D observation $y_0,y_1,y_2$.

# Corridor
The _Corridor_ dataset is preprocessed such that the imperfect magnetometer readings are already calibrated and expressed in the global world frame (instead of the sensor frame). The observations have been subsampled such that there is at least 0.05 meter between two consecutive data points.

However, one preprocessing is missing from this dataset. To reproduce our experiment, you should first compute the empirical means $y_{0,\mathrm{mean}}$, $y_{1,\mathrm{mean}}$, and $y_{2,\mathrm{mean}}$ from the training dataset and subtract them from the training and the test observation. It should be done because our model has a zero mean prior. However, other GP models from the literature might not need this additional preprocessing.

# Simu1D, Simu2D, Simu3D
_Simu1D_, _Simu2D_, _Simu3D_ are simulated datasets composed of 4 files in total:
- simu1D_training.csv
- simu2D_training.csv
- simu3D_training.csv
- simu_test.csv.

The total of 3100 observations in these 4 files were all generated jointly from a zero-mean Gaussian process prior (check the article for the GP covariance kernel and hyperparameter values). No additional preprocessing is needed to use them.

# References
[1] Abdul-Raouf, I., Gay-Bellile, V., Joly, C., Bourgeois, S., & Paljic, A. "Large Scale Mapping of Indoor Magnetic Field by Local and Sparse Gaussian Processes". In CoRL 2024.

TODO check citation format

# Feature Selection Hyperparameter Tuning

| Hyper-Parameter |          Values          |                                                                                                                Description |
| --------------- | :----------------------: | -------------------------------------------------------------------------------------------------------------------------: |
| var\_threshold  | [0, 0.0001, 0.001, 0.01] |                          Threshold for minimum variance of a feature. <br /> All features below the threshold are dropped. |
| corr\_threshold |   [1, 0.99, 0.95, 0.9]   | Threshold for maximum correlation between two features. <br /> If the correlation is above this threshold, one is removed. |
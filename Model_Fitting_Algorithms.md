# Model-Fitting Approaches

This page details the fitting algorithms/processes supported by various microlensing packages.

## Overview

| Algorithm                                              | BAGLE | VBM | MM | pyLIMA | RTModel | eesunhong  |
|--------------------------------------------------------|-------|-----|----|--------|---------|------------|
| Uses Fitted Algorithm of Any Kind                      | Y     | N   | N  | Y      | Y       | Y          |
| | | | | | | |
| Binary Grid search                                     |       |     |    |        |         | Y          |
| Differential Evolution                                 |       |     |    | Y      |         |            |
| Nested Samples                                         | Y     |     |    |        |         |            |
| Levenberg–Marquardt                                    |       |     |    |        | Y       |            |
| Metropolis-Hastings                                    |       |     |    |        |         | Y          |

## Package Specific Notes

<!-- ### ### BAGLE -->



<!-- ### VBM -->



<!-- ### MulensModel -->



<!-- ### pyLIMA -->



<!-- ### RTModel -->



### eesunhong 
**eesunhong** uses Metropolis-Hastings for both optimization and sampling. During the optimization phase, the jump function is continously updated to improve the efficiency of the fitting. The binary grid seach in eesunhong is used to find initial conditions for the optimization - the $\chi^2$ for each model on the grid is calculated but fits are only launched from the best initial conditions.

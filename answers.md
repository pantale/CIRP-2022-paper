# reviewer #1

*In this manuscript, the authors try to identify an ANN-based material flow law by 3D cutting experiments, some questions need to be clarified.*

The authors do not identify an ANN-based material flow law through 3D cutting experiments. Instead, they identify the ANN parameters from data generated from an analytical model, simplifying the concept. In real life, data would be obtained from experiments on a Gleeble device or gas gun. Once the ANN is identified, it is then used for the simulation of the cutting process, and the results are compared to experiments.

1. *The authors heavily rely on reference [33], encompassing the ANN-based  material flow law and its implementation framework in Abaqus. The  innovation of this paper should be improved.* 

   In fact there were 5 publications proposed during the last two years about this approach. All five publications focus on the application of artificial neural networks (ANNs) in the field of finite element simulations, specifically in the context of thermomechanical processes and deformation behavior of medium carbon steel. The main difference lies in the specific focus of each paper. While [1] discusses the implementation of a non-linear flow law using a neural network, [2] focuses on the development and implementation of an ANN-based flow law. [3] compares the performance of analytical and ANN-based flow laws, [4] focuses on predicting critical conditions for dynamic recrystallization, and [5] compares different activation functions. This research is quite intensive and the current paper emphasizes the applicability of this ANN-based flow law to cutting simulations. In this context, the strain rate becomes a prominent factor in the simulations, contrasting with the more quasi-static approach used in previous studies [3,4].

   On the other hand, concerning numerical simulation of cutting, this paper fills the gap in the oblique cutting literature by investigating both free orthogonal and free oblique 3D cutting configurations, both experimentally and numerically.
   Free orthogonal and free oblique cutting with unpreviously seen wide range of cutting conditions (36 conditions) are considered, including 2 cutting edge inclinations to demonstrate the predictive capability of the FE model for the fundamental variables. Other free oblique cutting experiments could not be found in our literature review, those tests should therefore provide new and relevant information to the cutting community. The introduction of the material's flow law by means of a neural network has also not been carried out previously in the literature, to our knowledge.
   Another major novelty is the accurate evaluation of the fundamental variables and their trends in 3D, without the need to adjust the numerical parameters and the model characteristics when the cutting conditions and the inclination angle are changed significantly. This is what the authors are used to call a predictive model (by opposition to a model specifically developed and/or tuned to reproduce a given cutting condition and requiring modification to accommodate changes in the cutting conditions). The mere fact of changing the inclination angle from free orthogonal cutting to oblique cutting while maintaining the quality of the results has no equivalent in the current literature, especially since no studies (experimental or numerical) on free oblique cutting are available.
   These aspects of the study are mentioned at the end of the introduction and in the conclusions.

   ```
   <span style="color:blue">Tu peux peut-être détailler plus les aspects novateurs de la coupe.</span>.
   ```

   [1] Pantalé O., Tize Mha P., Tongne A. (2022). Efficient implementation of non-linear flow law using neural network into the Abaqus Explicit FEM code. Finite Elements in Analysis and Design, 198, 103647. doi.org/10.1016/j.finel.2021.103647 

   [2] Pantalé O. (2023). Development and Implementation of an ANN Based Flow Law for Numerical Simulations of Thermo-Mechanical Processes at High Temperatures in FEM Software. Algorithms, 16(1):56. doi.org/10.3390/a16010056 [3] Tize Mha P., Dhondapure P., Jahazi M., Tongne A., Pantalé O. (2023). Interpolation and Extrapolation Performance Measurement of Analytical and ANN-Based Flow Laws for Hot Deformation Behavior of Medium Carbon Steel. Metals, 13(3), 633. doi.org/10.3390/met13030633 

   [4] Tize Mha P., Dhondapure P., Jahazi M., Tongne A., Pantalé O. (2023). Artificial Neural Network-Based Critical Conditions for the Dynamic Recrystallization of Medium Carbon Steel and Application. Metals, 13(10),1746. doi.org/10.3390/met13101746 

   [5] Pantalé O. (2023). Comparing Activation Functions in Machine Learning for Finite Element Simulations in Thermomechanical Forming. Algorithms, 16(12):357. doi.org/10.3390/a16120537

2. *How many times are spent to train the ANN model.*

   As already mentioned in the text (line 213 of the previous version of the paper), the training time is around 1 hour to get the set of parameters. In the above citations, we also usually fix this learning time to the same duration for all developed models. 

3. *The chosen cutting speed and depth seem lower than practical cutting parameters.*

   The cutting speeds and the uncut chip thicknesses were chosen from the recommendations of the tool manufacturer for the standard tool geometry.
   More specifically, for the standard version of the tool, the range of recommended cutting speeds by the tool manufacturer is 27-39 m/min. The values adopted in this study correspond to a larger range, 5-40 m/min, with a significant overlap with the recommendation. For the uncut chip thickness (so, the feed per revolution in turning), the range recommended by the tool manufacturer is 50-220 µm. The values adopted in this study (40-80 µm) are in the lower part of the range, in order to mainly limit the forces on the spindle as it is used in an uncommon configuration.
   This information has been added in the text.

4. In section 4, employing the training set to examine the trained model  is unconvincing, particularly given the imperfect performance observed  in the feed force.
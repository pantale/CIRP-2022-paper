# reviewer #1

*In this manuscript, the authors try to identify an ANN-based material flow law by 3D cutting experiments, some questions need to be clarified.*

The authors do not identify an ANN-based material flow law through 3D cutting experiments. Instead, they identify the ANN parameters from data generated from an analytical model, simplifying the concept. In real life, data would be obtained from experiments on a Gleeble device or gas gun. Once the ANN is identified, it is then used for the simulation of the cutting process, and the results are compared to experiments.

1. *The authors heavily rely on reference [33], encompassing the ANN-based  material flow law and its implementation framework in Abaqus. The  innovation of this paper should be improved.* 

   In fact there were 5 publications proposed during the last two years about this approach. All five publications focus on the application of artificial neural networks (ANNs) in the field of finite element simulations, specifically in the context of thermomechanical processes and deformation behavior of medium carbon steel. The main difference lies in the specific focus of each paper. While [1] discusses the implementation of a non-linear flow law using a neural network, [2] focuses on the development and implementation of an ANN-based flow law. [3] compares the performance of analytical and ANN-based flow laws, [4] focuses on predicting critical conditions for dynamic recrystallization, and [5] compares different activation functions. This research is quite intensive and the current paper emphasizes the applicability of this ANN-based flow law to cutting simulations. In this context, the strain rate becomes a prominent factor in the simulations, contrasting with the more quasi-static approach used in previous studies [3,4].

   On the other hand, concerning numerical simulation of cutting, this paper fills the gap in the oblique cutting literature by investigating both orthogonal and free oblique 3D cutting configurations, both experimentally and numerically.

   ```
   <span style="color:blue">Tu peux peut-être détailler plus les aspects novateurs de la coupe.</span>.
   ```

   [1] Pantalé O., Tize Mha P., Tongne A. (2022). Efficient implementation of non-linear flow law using neural network into the Abaqus Explicit FEM code. Finite Elements in Analysis and Design, 198, 103647. doi.org/10.1016/j.finel.2021.103647 

   [2] Pantalé O. (2023). Development and Implementation of an ANN Based Flow Law for Numerical Simulations of Thermo-Mechanical Processes at High Temperatures in FEM Software. Algorithms, 16(1):56. doi.org/10.3390/a16010056 [3] Tize Mha P., Dhondapure P., Jahazi M., Tongne A., Pantalé O. (2023). Interpolation and Extrapolation Performance Measurement of Analytical and ANN-Based Flow Laws for Hot Deformation Behavior of Medium Carbon Steel. Metals, 13(3), 633. doi.org/10.3390/met13030633 

   [4] Tize Mha P., Dhondapure P., Jahazi M., Tongne A., Pantalé O. (2023). Artificial Neural Network-Based Critical Conditions for the Dynamic Recrystallization of Medium Carbon Steel and Application. Metals, 13(10),1746. doi.org/10.3390/met13101746 

   [5] Pantalé O. (2023). Comparing Activation Functions in Machine Learning for Finite Element Simulations in Thermomechanical Forming. Algorithms, 16(12):357. doi.org/10.3390/a16120537

2. *How many times are spent to train the ANN model.*

   As already mentioned in the text (line 213 of the previous version of the paper), the training time is around 1 hour to get the set of parameters. In the above citations, we also usually fix this learning time to the same duration for all developed models. 

3. The chosen cutting speed and depth seem lower than practical cutting parameters. 

4. In section 4, employing the training set to examine the trained model  is unconvincing, particularly given the imperfect performance observed  in the feed force.
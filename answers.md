# reviewer #1

*In this manuscript, the authors try to identify an ANN-based material flow law by 3D cutting experiments, some questions need to be clarified.*

The authors do not identify an ANN-based material flow law through 3D cutting experiments. Instead, they identify the ANN parameters from data generated from an analytical model, simplifying the concept. In real life, data would be obtained from experiments on a Gleeble device or gas gun. Once the ANN is identified, it is then used for the simulation of the cutting process, and the results are compared to experiments.

1. *The authors heavily rely on reference [33], encompassing the ANN-based  material flow law and its implementation framework in Abaqus. The  innovation of this paper should be improved.* 

   In fact there were 5 publications proposed during the last two years about this approach. All five publications focus on the application of artificial neural networks (ANNs) in the field of finite element simulations, specifically in the context of thermomechanical processes and deformation behavior of medium carbon steel. The main difference lies in the specific focus of each paper. While [1] discusses the implementation of a non-linear flow law using a neural network, [2] focuses on the development and implementation of an ANN-based flow law. [3] compares the performance of analytical and ANN-based flow laws, [4] focuses on predicting critical conditions for dynamic recrystallization, and [5] compares different activation functions. This research is quite intensive and the current paper emphasizes the applicability of this ANN-based flow law to cutting simulations. In this context, the strain rate becomes a prominent factor in the simulations, contrasting with the more quasi-static approach used in previous studies [3,4].

   On the other hand, concerning numerical simulation of cutting, this paper fills the gap in the oblique cutting literature by investigating both free orthogonal and free oblique 3D cutting configurations, both experimentally and numerically.
   Free orthogonal and free oblique cutting with unpreviously seen wide range of cutting conditions (36 conditions) are considered, including 2 cutting edge inclinations to demonstrate the predictive capability of the FE model for the fundamental variables. Other free oblique cutting experiments could not be found in our literature review, those tests should therefore provide new and relevant information to the cutting community. The introduction of the material's flow law by means of a neural network has also not been carried out previously in the literature, to our knowledge.
   Another major novelty is the accurate evaluation of the fundamental variables and their trends in 3D, without the need to adjust the numerical parameters and the model characteristics when the cutting conditions and the inclination angle are changed significantly. This is what the authors are used to call a predictive model (by opposition to a model specifically developed and/or tuned to reproduce a given cutting condition and requiring modification to accommodate changes in the cutting conditions). The mere fact of changing the inclination angle from free orthogonal cutting to oblique cutting while maintaining the quality of the results has no equivalent in the current literature, especially since no studies (experimental or numerical) on free oblique cutting are available.
   These aspects of the study are mentioned at the end of the introduction and in the conclusions.

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

4. *In section 4, employing the training set to examine the trained model  is unconvincing, particularly given the imperfect performance observed  in the feed force.*

   In addition to the information provided in the answers to the previous comments for the use of ANN, the authors would like to stress that a less well modelled feed force than the cutting force is typical of FE models of the cutting process. In addition, the difference with the experimental values in this work is similar to other studies but for a narrower range of cutting conditions (as shown for example in the results of references 27, 32, 45-48 of the original submission).
   
   The reasons for the worse performance of feed force is still a hot topic in the numerical modelling of the cutting process, with no clear answer nor solution so far. The main hypotheses include the influence of the geometry of the cutting edge (it would quickly wear so the tool would never really cut with its fresh geometry), of the friction and of the material behaviour. The authors believe the feed force is indeed at least influenced by the friction and the material behaviour, and that they should be considered together to improve the modelling of the feed force (as we did in [a]). But influence of the model of friction and of the material behaviour, as well as the identification of their parameters, are way beyond the scope of this study. Those should surely (and will!) be included in future developments.
   
   [a] Kugalur Palanisamy N, Rivière Lorphèvre E, Gobert M, Briffoteaux G, Tuyttens D, Arrazola P-J, Ducobu F. Identification of the Parameter Values of the Constitutive and Friction Models in Machining Using EGO Algorithm: Application to Ti6Al4V. Metals. 2022; 12(6):976. doi.org/10.3390/met12060976

# reviewer #2

1. *What is the difference between ALE-Eulerian and ALE (please see for example Fig-1).* 

   ALE methods are not used in this study and figure 1 describes the experimental setup (with no link with the ALE formulation)... This comment does not seem to be related to our manuscript.
   
2. *Do authors used a gap conductance at the tool-workpiece interface in their numerical simulations?* 

   No gap conductance has been used in the models (but we would have liked to do so), just because gap heat conductance based on the distance between 2 surfaces is not available for the CEL formulation in Abaqus.
   In combination with a following comment, the manuscript has been updated to include that information.

3. *Table 3. The convection coefficient is chosen equal to 50 W/m2. His is choice has to be justified.* 

   The reference corresponding to the motivation of the value of the convection coefficient was indeed missing in Table 3. Thank you for pointing it!
   It comes from reference 13 of the original manuscript. This reference, already cited in the manuscript, has been added in the caption of Table 3.

4. *In page 10 authors said that « In future developments, experimental tests on a Gleeble thermomechanical simulator will be used to generate this network training data ». But in Gleeble tests the maximum strain rates cannot exceed 100 (S-1) which does not represent actual strain rates in cutting.* 

   Maybe this sentence is a little bit short, and in fact we plan to use Gleeble tests to simulate lower strain rate scenarios with a wide range of temperatures and Taylor gas gun tests for higher strain rates. This will help to cover a broad spectrum of strain rates from quasi-static to those representative of cutting processes. The use of the ANN will help this integration since we can easily mix the dataset from the two experimental techniques.

5. *Figure 5 shows Temporal evolutions of experimental (E) and numerical (N) forces. The maximum time value of simulation cutting is 0.06 S. How authors programed this from experimental point of view for numerical validation?* 

   The length of the workpiece (so the length of a rib shown in figure 1) has been fixed at 10 mm (Table 1). The duration of the operation therefore depends on the cutting speed, 10 m/min for figure 5. The duration has consequently not been programmed but it is a "result" of the combination of the length of the workpiece and the cutting speed.

6. *Figure 6 shows Temperature contours (in K) of the numerical chip after 1.5 ms. Why there is no heat conduction in the tool?* 

   Temperature in the tool increases mainly by the heat generated by friction due to the hypotheses of the model (absence of heat gap generation as highlighted by a previous comment of the reviewer). Temperatures of the tool are therefore underestimated. However, temperature increases in the tool, but at a lower level than in the chip which explains why it cannot be seen in figure 6. The authors checked that steady-state is reached at 1.5 ms (for the cutting conditions of figure 6) with a maximal temperature under 400 K (so all temperatures in the tools are in the blue colours, knowing that the maximal temperature is in the middle of the tool and the tool is wider than the workpiece).
   Following the reviewer's comment, the authors assumed that this aspect of the model had to be more detailed. The manuscript has therefore been updated in the presentation of the model and in the results.

7. *Cutting speed is chosen between 5 and 40 for Ti6Al4V but this is low values. Please justify if these are is industrial cutting speed values?* 

   The cutting speeds were chosen from the recommendations of the tool manufacturer for the standard tool geometry.
   The range of recommended cutting speeds is 27-39 m/min. The values adopted in this study correspond to a larger range, 5-40 m/min, with a significant overlap with the recommendation.
   This information has been added in the text.

8. *From fih6 to 9, I think that all results are presented for q time of cutting corresponding to 1.5ms. But this do not represent industrial case in relationship with cutting force and temperature distribution?* 

   For the cutting conditions of these figures, steady-state state is reached at 1.5 ms: temperatures and forces are nearly constant. The authors fully agree that, in general, a cutting time of 1.5 ms is not relevant from an industrial perspective. However, reaching steady-state makes this cutting time industrially significant, and allows to use these results to estimate the cutting forces, the chip morphology, compare with experimental values, etc. as long as tool wear is not studied (then, longer cutting times should be considered).

9. *For CEL description do authors use an equation of state for Ti6Al4V ? if yes please specify it in your text.* 

   We do not use an equation of state for Ti6Al4V in the CEL formulation.

# reviewer #3

*The paper presents a good scientific contribution for machining simulation by using indirectly the flow stress of the workmaterial.*

1. *It seems that the chip formation is not stabilized in simulations*

   The authors assumed that the chip formation "not stabilized" is to be related to steady-state that would not be reached during the simulation. As answered to question 6 from reviewer #2, we double-checked and confirmed that steady-state is reached from 1.5 ms for the cutting conditions of figure 6 (cutting forces in the 3 directions are nearly constant, as well as maximal temperature in the tool, etc.).

2. *Is there a comparison with simulations using directedly the JC flow stress model?*

   Yes, the results of the simulations are compared to the JC flow stress in section 3.4 and quantification is provided in Table 5. It is shown that the proposed approach increases computation time from 6%, depending on the number of neurons of the first layer of the ANN, with no significant impact on the results of the model.

3. *What about the case of chip segmentation commonly seem when machining TA6V!*

   Chip segmentation is out of the scope of this study. It is one of its perspectives as other (than Johnson-Cook) material models including damage, strain softening need to be considered.
   The cutting conditions of this work produce (mainly due to the low feeds) continuous chips, allowing to focus on the Johnson-Cook flow stress. 

4. *It is judicious to show also what predictions of the flow stress by the  ANN-based material flow law in comparison with the JC flow law for the  case of simple loading uniaxial tension or simple shear! What's the  response of the ANN model in simple solicitations?*

   Such kind of comparison is already published in [1] for example where we compare the predicted flow stress and the experimental results for compression tests on a Gleeble thermo-mechanical simulator. A complete study of the influence of the hyper-parameters on the numerical performance of the ANN has been proposed.

   [1] Pantalé O. (2023). Comparing Activation Functions in Machine Learning for Finite Element Simulations in Thermomechanical Forming. Algorithms, 16(12):357. doi.org/10.3390/a16120537
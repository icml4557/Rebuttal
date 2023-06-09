# Rebuttal
Response to the Reviewers questions

## Explanation for figure Eigenvalues_comparisons.png

The small eignevalue of $10^{-8}$ under GD decays very slowely (dashed gree line), while under overdampes solution (blue line) the convergence is fast. The large eigebnvalue of $10^{+3}$ under GD decays immediatley (dashed red line), while udner underdamped solution (orange line) it oscilates until it converges, as a result both eigenvalues $10^{-8}$ and $10^{+3}$ under momentum are learnt at the same time. 

It is worth mentioning, that there exists an extremely large discrepancy between the eigenvalues of the boundary/ initial points and the PDE points. As shown in Fig 8, the eigenvalues of PDE can be very large while the eigenvalues of the boundary/initial points can be very small. This discrepancy makes the learning via GD or any optimization that is based on a single solution insufficient where the PDE components are learned quickly while the components of the boundary/ initial condition will not be learned and as a result, the final solution is not accurate.  On the other hand, the momentum term in GDM forces an optimization based on three solutions, where large eigenvalues undergo underdamped convergence (the decay rate is slowed down, however as they correspond to larger eigenvalues the convergence is still fast), on the other hand, the smaller eigenvalues undergo overdamped convergence (the decay rate is very fast) as a result all eigenvalues from PDE and boundary/initial points are learned together and this solves the discrepancy issue. Of note, the discrepancy in the components of PINNs is known and the most common practice to tackle the issue is based on assigning adaptive weights to terms of the loss function in an attempt that initial and boundary points and the PDE points be learned simultaneously. We have already shown that our approach results in much better performance.  

## Explanation for figure Adagrad.png

In Figure 7 of the main paper, we have shown that after 20000 epochs the model trained via Adam optimizer has correctly estimated the solution. Here, as shown, after 20000 epochs the trained model via Adaboost cannot estimate the true solution. We have shown the estimation of solution based on Adaboost optimization after 40000 and 50000 epochs as well. 

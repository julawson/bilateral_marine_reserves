# Bilateral marine reserve agreements

Scripts and other files relevant to *Bilateral marine reserve agreements* (Lawson and Costello, 2025) are detailed here.

## Within 'scripts' folder the script '01_functions' loads all functions.
This script runs all functions that are necessary to run the model.

General Functions are:
* *e_i* is the patch-specific escapement function.
* *h_i* is the patch-specific harvest function.
* *growth_i* is the patch-specific growth function.
* *next_x_i* is the patch-specific size of the stock in the next time step.
* *b_i* is the patch-specific marginal profit function.

Scenario Functions are:
* *compute_e_star* returns escapement under the sole owner scenario.
* *compute_e_hat* returns escapement under the non-cooperative scenario.
* *pi_a* returns the current period profit in Patch A.
* *payoff* returns the net present value to each Patch.
* *compute_e_a_star* uses a generalized additive model to predict e_a_star.

## Within 'scripts' folder the script '02_base_params' loads parameters;

Growth parameters are:
* *k_i* is the patch-specific carrying capacity.
* *r_i* is the patch-specific growth rate.

Movement Parameters are:
* *M_ab* is the adult movement from A -> B
* *M_ba* is the adult movement from B -> A
* *M_aa* is the adults retained in A
* *M_bb* is the adults retained in B
* *D_ab* is the larval dispersal A -> B
* *D_ba* is the larval dispersal B -> A
* *D_aa* is the larvae retained in A
* *D_bb* is the larvae retained in B

Survival Parameters are:
* *mu_i* Patch-specific pre-dispersal adult survival.
* *sigma_i* Patch-specific post-dispersal larval survival.

Economic Parameters are:
* *p_i* Patch-specific price
* *c_a* Patch-specific Marginal harvest cost
* *delta* the discount factor

Other Parameters:
* *timesteps* the number of timesteps in the scenario.
* *size_x_i* is the patch-specific grid size for the dynammic programming grid.
* *T* is the time horizon for backwards induction.
* *small* sets the smallest unit on the patch-specific grid.

All of '01_functions', and '02_base_params' should be run prior to running the 'Base Params for Dynamic Programming Grid' 

## Within 'scripts' folder the script '03_base_model' 

This script runs all three scenarios (non-cooperative, sole owner, and bilateral marine reserve) using a set of parameters as specified in *02_base_params*

## Within the 'scripts' folder the script '04_full_model'

This script runs all three scenarios (non-cooperative, sole owner, and bilateral marine reserve) while varying adult (*M_ba*, *M_ab*) and larval (*D_ba*, *D_ba*) movement parameters from 0 to 1 in 0.1 increments. 

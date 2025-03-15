# Bilateral marine reserve agreements

Scripts and other files relevant to *Bilateral marine reserve agreements* (Lawson and Costello, 2025) are detailed here.

## Within 'scripts' folder the script '01_functions' loads all functions.
This script runs all functions that are necessary to run the model.

General Functions are:
* e_i are the escapement function.
* h_i is the harvest function.
* growth_i is the patch-specific growth function.
* next_x_i is the size of the stock in the next time step.
* b_i is the marginal profit function.

Scenario Functions are:
* compute_e_star returns escapement under the sole owner scenario.
* compute_e_hat returns escapement under the non-cooperative scenario.
* pi_a returns the current period profit in Patch A.
* payoff returns the net present value to each Patch.
* compute_e_a_star uses a generalized additive model to predict e_a_star.

'0_1 functions' contains the functions used for the base and full model.
'0_2 base parameters' sets basic model parameters
  k_a is the carrying capacity of Patch A
  k_b is the carrying capacity of Patch B
  r_a is the growth rate in Patch A
  r_b is the growth rate in Patch B
  M_ab is the adult movement from A -> B 
  M_ba is the adult movement from B -> A 
  M_aa is the adults retained in A
  M_bb is the adults retained in B
  D_ab is the larval dispersal A -> B 
  D_ba is the larval dispersal B -> A
  D_aa is the larvae retained in A
  D_bb is the larvae retained in B

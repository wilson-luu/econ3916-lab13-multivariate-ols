# Multivariate OLS — What "Controlling For" Actually Does

**Objective:** This project demonstrates how adding control variables in a multivariate OLS regression changes the interpretation of a coefficient to a partial effect, and uses simulated data to quantify omitted variable bias, Frisch-Waugh-Lovell partialling out, and the danger of collider bias.

**Methodology:**
* Simulated wages with an unobserved ability term. Leaving ability out gave a return to education of 5,126 against a true 2,500; putting it in gave 2,546.
* Checked the omitted-variable-bias formula: it predicted a bias of 2,629, and the actual bias was 2,626.
* Showed Frisch-Waugh-Lovell: regressing the part of wages that ability does not explain on the part of education that ability does not explain gave the same coefficient as the full regression.
* Showed a collider control turning a true effect of zero into an estimate of -0.596, with a p-value that printed as 0.000.
* Separated what multicollinearity damages (standard errors, about 12.3 times larger) from what it does not (the estimates).
* Fitted an interaction: a year of experience was worth 900 to non-union workers and 500 to union members.
* Asked an AI to write a specification-table function, revised my prompt once, and checked its coefficients against my own regressions.

**Key Findings:**
Leaving unobserved confounders (ability) out of a regression caused severe omitted variable bias (return to education inflated to 5,126 from a true 2,500), but blindly adding controls (colliders) invented highly significant, entirely spurious effects (-0.596 effect when truth was 0, p < 0.001).

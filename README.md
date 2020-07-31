# megameta

### Processing pipeline for Neural Correlates of Message Effectiveness: A Mega-Analysis


We used NiPype (https://nipype.readthedocs.io/en/latest/) to implement the first- and second-level models described above in a neuroimaging pipeline, predominantly using tools from SPM12, that can be used to apply identical, reproducible analysis scripts for first-level models across all studies and sub-analyses. 

First-level models. For each of the three main analyses (predicting self-relevance, behavior change, and population-level message effectiveness), we designed one common model that we fit to the data of all eligible study participants and fMRI tasks. The models  are flexible enough to be applied in an identical manner to all studies within each sub-analysis. Per study, individual trial screens  are simply categorized appropriately into each main regressor of interest. Across sub-analyses, (e.g. across population-level message effectiveness and self-relevance), this same model can be applied. The difference lies in the modulator (i.e. a parametric modulator). We include modulators for both the pure and impure message regressors to examine how neural correlates of message exposure are affected by our variables of interest (i.e. population-level message effectiveness, message self-relevance, etc.), and with this flexible pipeline can interrogate secondary questions later on about the extent to which motivated processing (e.g., effects from “pure” vs. “impure” trials) matters. 

Whole-brain analysis. To identify the neural correlates of message self-relevance and population-level message effectiveness, we investigated the pure and impure message regressors each modulated by the parametric modulators of self-relevance and population-level message effectiveness, respectively, with a view to identifying how robust prediction models are to variation in the fMRI task. To identify neural correlates of behavior change, we conducted a multiple regression analysis in SPM12, regressing brain activity associated with the contrasts of pure and impure message exposure compared to rest against an individual difference measure of behavior after message exposure, controlling for pre-message behavior. 

Regions of Interest. Region of interest analyses examine the average activity exhibited during some task condition within a specific cluster of voxels in the brain. To examine hypotheses about specific brain regions of interest, we extracted activity representing the extent to which self-relevance ratings, population-level message effectiveness and behavior change, respectively, were correlated with neural activity during “pure message” exposure in the first-level models described above. Our review highlighted ventromedial prefrontal cortex (vmpfc) for its central role as a predictor of diverse message effectiveness indicators across studies, given it’s goal in value-based decision-making. Consequently, we focused our initial analyses on average activity within a vmpfc cluster that is meta-analytically associated with subjective valuation according to a large meta-analysis of over 200 studies (Bartra, McGuire, & Kable, 2013). 

Whole Brain Patterns. In addition to this region of interest approach which only utilizes a small amount of the available neural data, we also examined whole brain patterns of interest which take into account distributed activity across the entire brain. The terms “reward”, “self”, “mentalizing”, and “emotion” were selected as a-priori predictors for their previously defined roles in tracking stimulus driven behavior change and common use in the field. Value and reward related regions (Bartra et al., 2013) integrate relevant inputs from diverse brain regions into a common currency value calculation, which further predicts a final evaluation of a stimulus related choice or behavior. Two important inputs, self-referential processing regarding the perceived relevance of a stimulus and emotional responses during message exposure feed into the summary value signal which more directly predicts individual- and population-level message effects (Doré et al., 2018; Falk & Scholz, 2018). 
  We used these whole brain patterns derived from independent meta-analyses conducted through neurosynth, as a reference to estimate the expression of each pattern for every person and every message (i.e., the similarity of a given observation of whole-brain activity during message exposure to this reference pattern), yielding a single scalar value that could be used to predict indicators of message-effectiveness.
  In addition to these theory-driven whole brain patterns, we also developed data driven patterns representing whole-brain activity associated with self-relevance, population-level message effectiveness and behavior change in our mega-analysis. These whole-brain maps represent unthresholded maps that result from the second-level models described above (which aggregate across the target studies of our mega-analysis to map whole brain, multivariate signatures related to each outcome).

Estimating model predictive accuracies using cross-validation. After a model has been fit, it is useful to try to understand how well the model generalizes to unseen data by estimating its out-of-sample predictive accuracy (Box, 1976; Gelman, Hwang, & Vehtari, 2013). 
Cross-validation strategies are described in the relevant study sections.


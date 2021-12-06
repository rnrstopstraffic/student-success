# student-success
## Background

Due to recent statewide legislative changes, American River College needed to identify segments of the student population who were more likely and less likely to succeed in certain transfer-level classes. Decision tree classifiers were chosen as the best option as they provide clear rules for determining which students are likely to be successful or not in a given class and are easy to operationalize should we choose to formalize a placement model.

## Implementation

The raw data is contained in the artificial_student_success_data.csv file contained in the [data folder](./data). The [select_clean_by_course.ipynb](./python_scripts/select_clean_by_course.ipynb) script is then run to create a slice for the particular course of interest and save that slice as a cleaned up PKL file in the [data folder](./data). For this specific example, we are working with STAT300. The [Stat300_clf_model.ipynb](./python_scripts/Stat300_clf_model.ipynb) then imports said PKL file and creates two decision tree models. The first is based exclusively on High School GPA (HSGPA); the second is based on HSGPA and self-reported household income levels. The classifier saves images of each decision tree in the [image_outputs folder](./image_outputs) as well as prints the accuracy of each model

## Notes
1) For the purposes of avoiding FERPA violations, as well as to keep with best practices for institutional data, this dataset was artificially created using parameters from the original dataset.

2) In a fully completed study, the accuracy would need to be analyzed in light of sensitivity, specificity, and precision.

3) The data is imbalanced toward "success," so "class_weight = 'balanced'" was used to help prevent a scenario where accuracy was not simply a result of a lack of specificity. 

4) It would be, of course, highly undesirable to place students based on their household incomes. That model was created to observe if there was, in fact, a significant impact which household income played in first course success. The accuracy of the model was only nominally impacted by the inclusion of this feature, so this particular study does not provide evidence that household income is a practically significant factor in first course success.


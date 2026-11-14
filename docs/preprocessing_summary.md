# Feature Engineering and Preprocessing Summary

## Features Created
- FamilySize: siblings/spouses + parents/children + 1
- IsAlone: 1 if the passenger travelled alone
- FarePerPerson: Fare divided by FamilySize
- Title: extracted from the passenger's name (Mr, Mrs, Miss, Master, Rare)
- AgeGroup: Age grouped into Child, Teen, Adult, Senior

## Preprocessing Steps
- Encoding: Sex and AgeGroup were label-encoded; Embarked and Title were one-hot encoded.
- Scaling: Age and FarePerPerson were standardized; Fare and FamilySize were min-max scaled.
- Feature selection: correlation and the ANOVA F-test were used to rank features. The top 10 were Pclass, Sex, Fare, IsAlone, FarePerPerson, AgeGroup, Embarked_S, Title_Miss, Title_Mr, and Title_Mrs.

## Why Preprocessing Was Required
- Machine learning models only understand numbers, so text columns such as Sex, Embarked, and Name had to be converted or turned into numeric features.
- Columns use very different ranges (Age up to 80, Fare up to 66). Scaling stops large-valued columns from dominating the model.
- Raw columns hide useful patterns. New features such as Title and FamilySize give the model clearer signals about who survived.
- Feature selection removes columns that add little information, which makes the data simpler and easier to explain.

## Result
The dataset grew from 11 columns to 17, with no text columns and no missing values, so it is ready for modelling. The final file is updated_dataset.csv.

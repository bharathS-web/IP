# AdaBoost Classifier Selection and Calculation

## Step 1: Accuracy Calculation
| Actual | Model 1 | Model 2 | Model 3 | Model 4 |
|--------|---------|---------|---------|---------|
| B      | A       | A       | A       | A       |
| B      | B       | A       | A       | A       |
| B      | B       | B       | B       | A       |
| B      | A       | B       | B       | A       |
| A      | B       | A       | B       | B       |

- **Model 1**: Correct predictions = 1 (Instance 2)
- **Model 2**: Correct predictions = 1 (Instance 1)
- **Model 3**: Correct predictions = 1 (Instance 1)
- **Model 4**: Correct predictions = 0 (None)

## Step 2: Evaluating Weakness of Models
- **Model 1**: 1 correct prediction (weak, but better than random)
- **Model 2**: 1 correct prediction (weak, but better than random)
- **Model 3**: 1 correct prediction (weak, but better than random)
- **Model 4**: 0 correct predictions (weak, excluded from ensemble)

## Step 3: Classifier Selection for AdaBoost
- **Select**: Models 1, 2, 3 (weak but better than random)
- **Exclude**: Model 4 (no correct predictions)

## Step 4: AdaBoost Algorithm
- Assign higher weights to Models 1, 2, and 3.
- Combine Models 1, 2, and 3 into a stronger classifier using AdaBoost.

## Step 5: AdaBoost Weight Calculation
- Initial weights for each model are equal (1/3 for each model).
- After each iteration, models with fewer errors receive higher weights.

## Step 6: Final Classifier Decision
- The final ensemble model combines the weighted predictions from Models 1, 2, and 3.
- The model with the highest weight will influence the final prediction the most.

## Step 7: Final Prediction
- The combined prediction from the weighted models (Models 1, 2, and 3) will give the final output after applying AdaBoost.

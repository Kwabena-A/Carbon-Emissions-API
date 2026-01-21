# MyCarbon Prediction API

Python API for predicting carbon emissions based on user lifestyle and consumption data.

## Live Deployment

Hosted on Render:  `carbon-emissions-api.onrender.com`

## API Endpoint

### GET `/make-prediction/`

Predicts carbon emissions from query parameters.

**Request:**
```
GET /make-prediction/?args=overweight&args=male&args=vegan&args=3&args=coal&args=private&args=none&args=never&args=450&args=never&args=7&args=medium&args=55&args=9&args=50&args=0&args=Yes&args=[Plastic]&args=[Airfryer,%20Microwave,%20Grill,%20Oven,%20Stove]
```

**Parameters (in order):**

1. **Body Type**:  `overweight` | `obese` | `underweight` | `normal`
2. **Sex**: `female` | `male`
3. **Diet**: `pescatarian` | `vegetarian` | `omnivore` | `vegan`
4. **How Often Shower**: `daily` | `less frequently` | `more frequently` | `twice a day`
5. **Heating Energy Source**: `coal` | `natural gas` | `wood` | `electricity`
6. **Transport**: `public` | `walk/bicycle` | `private`
7. **Vehicle Type**: `none` | `petrol` | `diesel` | `hybrid` | `lpg` | `electric`
8. **Social Activity**: `often` | `never` | `sometimes`
9. **Monthly Grocery Bill** (numeric)
10. **Frequency of Traveling by Air**:  `frequently` | `rarely` | `never` | `very frequently`
11. **Vehicle Monthly Distance (km)** (numeric)
12. **Waste Bag Size**:  `large` | `extra large` | `small` | `medium`
13. **Waste Bag Weekly Count** (numeric)
14. **TV/PC Hours per Day** (numeric)
15. **New Clothes Monthly** (numeric)
16. **Internet Hours per Day** (numeric)
17. **Energy Efficiency**: `No` | `Sometimes` | `Yes`
18. **Recycling** (array): e.g., `[Plastic]`
19. **Cooking With** (array): e.g., `[Airfryer, Microwave, Grill, Oven, Stove]`

**Response:**
```json
{
  "Features" : list[String],
  "prediction": float,

}
```

## Model

ML model trained on carbon footprint datasets. Predicts emissions based on 19 lifestyle factors.

## Tech Stack

- Python
- FastAPI
- scikit-learn/TensorFlow
- Deployed on Render
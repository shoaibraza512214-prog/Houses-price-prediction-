# Houses-price-predicimport pandas as pd
import matplotlib.pyplot as plt
from sklearn.linear_model import LinearRegression

# Data (simple example)
data = {
    'area': [500, 1000, 1500, 2000, 2500],
    'price': [50, 100, 150, 200, 250]
}

df = pd.DataFrame(data)

# Model
X = df[['area']]
y = df['price']

model = LinearRegression()
model.fit(X, y)

# Prediction
y_pred = model.predict(X)

# New house prediction
new_area = [[1800]]
new_price = model.predict(new_area)

print("Predicted price for 1800 sq ft:", new_price)

# Graph
plt.scatter(df['area'], df['price'])   # points
plt.plot(df['area'], y_pred)           # line

plt.xlabel("Area")
plt.ylabel("Price")
plt.title("House Price Prediction")

plt.show()tion-

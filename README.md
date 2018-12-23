# crude-oil-price-prediction

> Predicting a crude oil price using **Recurrental Nueral Networks** and **Long Short-term Memmory** models based on a 10-day window size developed on **[Keras](https://keras.io/)**.

## Dataset
> dataset from: https://fred.stlouisfed.org/series/DCOILBRENTEU

This dataset contains daily Brent crude oil prices starting from 20th May ,1987.
* Units: Dollars per Barrel
* Source: [U.S. Energy Information Administration](https://www.eia.gov/)

## Preprocess

When you import the .csv file there are some days that there isn't data available for the pricing so it's filled with '.' so
I omitted those days by runnig this line of code.
```
a = a[a.DCOILBRENTEU != '.']
```
then I specified the hyperparameters:
* Batch Size
* Time Steps
* epochs

My goal was to predict the 21st day pricing based on the 20-day window before that and also seprate my test set. In order to make this happen I firstly calculated highest possible length so that it's dividable by batch size and then I normalized the data on the scale of (0,1) and then created my windows with 20-day time steps to feed them to a sequence model.

## Deep Sequence Model

### Long Short-term Memory (LSTM)
I've used LSTM cell as my RNN cells. LSTM was created to solve vanishing gradient in normal RNN cells by adding a short-term memory to cells. You can learn more on this subject [here](https://towardsdatascience.com/illustrated-guide-to-lstms-and-gru-s-a-step-by-step-explanation-44e9eb85bf21)

<img src="https://cdn-images-1.medium.com/max/1600/1*Niu_c_FhGtLuHjrStkB_4Q.png" alt="LSTM cell" width="350" height="350">

### Deep Model

Visualization will be added soon using [Tensorboard](https://www.tensorflow.org/guide/summaries_and_tensorboard).

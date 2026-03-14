# Physics-Informed Neural Networks (PINNs) for Tumor Cell Growth Modeling

This repository implements the methodology described in the paper **"Using Physics-Informed Neural Networks (PINNs) for Tumor Cell Growth Modeling"** by José Alberto Rodrigues. It utilizes PINNs to solve inverse problems by estimating biological parameters from experimental data of Chinese hamster V79 fibroblast tumor cells.

## 📌 Overview

The project explores the application of **Physics-Informed Neural Networks (PINNs)** to accurately predict the growth behavior of multicellular tumor spheroids. Unlike traditional neural networks, PINNs integrate physical laws directly into the loss function, allowing the model to adhere to biological growth mechanisms even when dealing with noisy experimental data.

## 🧬 Mathematical Model (Montroll Growth Model) 

Governed by the differential equation:

$$\frac{dp}{dt}(t)=kp(t)\left(1-\left(\frac{p(t)}{C}\right)^{\theta}\right)$$

**$k$**: Intrinsic growth rate.
**$C$**: Carrying capacity. 
**$\theta$**: A parameter indicating the position of the inflection point of the growth curve. 

## 🧠 PINN Architecture & Loss Function

The implementation uses a feedforward neural network architecture:

**Input**: Time ($t$).
**Hidden Layers**: Multiple layers with activation functions ($\sigma$) such as `tanh` or `ReLU`.
**Output**: Predicted population size $p(t)$.

### Optimization

The model minimizes a composite loss function:

$$\mathcal{L}_{PINN} = \mathcal{L}_{data} + \lambda\mathcal{L}_{physics}$$

**$\mathcal{L}_{data}$**: Mean squared error between predicted and observed experimental data.
**$\mathcal{L}_{physics}$**: Residual term ensuring the solution satisfies the governing growth equations.
**$\lambda$**: Regularization parameter crucial for achieving convergence.

## 📊 Dataset



## 📈 Key Findings

According to the research:

* Both models accurately predict the asymptotic saturation behavior of tumor growth.

* The **Montroll model** provides a better fit to the experimental data and a more accurate prediction of the inflection point due to the flexibility of the $\theta$ parameter.

* The final predicted parameters for the Montroll model are approximately $k \approx 0.831$, $C \approx 7.333$, and $\theta \approx 0.169$.

## 🛠️ Usage

This methodology can be adopted for any biological phenomenon intended to be modeled based on experimental data. To run the implementation, ensure you have an environment capable of running standard deep learning libraries (like TensorFlow/ADAM optimizer).

## 📜 Citation

The original paper:
> Rodrigues, J.A. Using Physics-Informed Neural Networks (PINNS) for Tumor Cell Growth Modeling. *Mathematics* 2024, 12, 1195. 

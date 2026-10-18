# Region I directly written! WT-TimeMixer: Highly innovative photovoltaic power prediction network based on wavelet frequency-scale collaboration and bidirectional multiscale hybrid.

\tPreface
In time-series prediction tasks such as photovoltaic power generation, wind power generation, electrical load, and industrial processes, the raw sequences often simultaneously contain dynamic patterns at multiple time scales.
\tTaking photovoltaic power as an example, the actual observation sequence usually simultaneously contains:
Slowly changing low frequency operating trend;
Daily cyclical changes;
Meteorological disturbances at different time scales;
1. Cloud cover-induced rapid power fluctuations;
Short-term climbing and sudden drops, among other high-frequency non-stationary components.
Therefore, predictive models on a single timescale often struggle to simultaneously describe: long-term trends, medium-scale cycles, and short-term random fluctuations. Traditional decomposition prediction methods typically adopt the following steps: VM -> DWT/STL -> GRU/LSTM/Transformer -> simple summation. Although this framework can alleviate non-stationarity, it often encounters a problem: the different scale components after decomposition are independent in their predictions, lacking explicit cross-scale information interaction. To address this issue, we propose a Wavelet-guided TimeMixer based on wavelet frequency-scale coordination and directional multiscale hybrid time series prediction network (Wavelet-guided TimeMixer).
\t  
\tWT-TimeMixer no longer simply performs wavelet decomposition as a preprocessing step for the network. Instead, it constructs multiscale representations with clear frequency hierarchies using multiple layers of discrete wavelet transforms. It also designs cross-scale information propagation mechanisms that oppose each other in direction, followed by final prediction through scale-independent intra-scale gating, Temporal–Feature Mixer, and adaptive multi-predictor fusion.
We also provide detailed materials, instructional documents, and video tutorials, including how to replace your own dataset, parameter tuning tutorials, etc. The code is commented line by line, with detailed introductions of parameters:
● Dataset: A dataset of power generation from a photovoltaic power station (applicable to multi-feature datasets), wind power dataset from a wind farm, wind speed dataset, etc.
● Environment Framework: Python 3.11, PyTorch 2.1 and above can be run.
● Model score: 0.93 on test set
● Usage Object: Paper requirements, graduation design requirements.
● Code Guarantee: The code comments are detailed and ready to run.
1. Introduction to the innovative model
1.1 Overall Process of the Model
\tThe overall prediction process of WT-TimeMixer is as follows:
Original multivariate time series
\t→ Data preprocessing and normalization
\t→ Multi-level Discrete Wavelet Decomposition (DWT)
\t→ Low frequency approximation level + High frequency detail level
\t→ Low frequency trend + High frequency fluctuations
\t→ Same scale A/D adaptive gate-controlled fusion
\t→ Temporal Mixing + Feature Mixing  
\t→ Multi-scale Independent Future Predictor
\t  
The model first constructs a hierarchical representation of the low-frequency approximation and high-frequency details using multilayer discrete wavelet transform. It then designs coarse to fine trend mixture and fine to coarse fluctuation mixture for two types of frequency components, achieving cross-scale information propagation with clear directional constraints. On this basis, the model further learns the internal dynamics within scales through low-frequency-to-high-frequency gating fusion and Temporal–Feature Mixer, and utilizes multiple scale-specific predictors to generate future sequences. Finally, it achieves multi-predictor fusion through sample-adaptive scale weights, enabling the model to dynamically select the most predictive time scale based on different operational states.
1.2 Model innovation points
1. Innovation Point 1: Wavelet-driven frequency-scale synergy representation
WT-TimeMixer obtains: \tA\t=\t{\tA\t1\t,\tA\t2\t,\...,\tA\tJ\t} and \tD\t=\t{\tD\t1\t,\tD\t2\t,\...,\tD\tJ\t}, where WT-TimeMixer establishes a joint representation of the Frequency Band × Temporal Scale. For photovoltaic power, it can be interpreted as: \tA\tJ\t→\ta slower, more macro-scale operational mode; and \tD\t1\t→\ta more localized and rapid change pattern. The model does not presuppose that a specific wavelet layer corresponds to a certain meteorological factor; instead, it utilizes these different scale representations for subsequent data-driven learning.
2. Innovation Point: Bidirectional Orientation Scale Mixing
(1) For low-frequency approximation levels: WT-TimeMixer employs a coarse-to-fine trend mixing approach, which starts from the coarsest scale and propagates towards finer scales. This helps maintain the overall evolutionary direction while preserving local variations at the finer scales. Model implementation: Information transmission from Global Trend to Local Trend.
(2) For high-frequency detail components, adopting completely opposite propagation directions, the model first extracts perturbation information from fine-grained details and then gradually propagates to coarser scales: Local Fluctuation → Multi-scale Fluctuation Context.
3. Innovation Point: Temporal-Feature Mixer in the Domain of Both Scales
After completing cross-scale information transmission, it is still necessary to model the temporal dependencies and multivariate relationships within each scale. The current WT-TimeMixer does not use complex Transformers but employs a lightweight Mixer, composed of Temporal Mixing + Feature Mixing.
2. Photovoltaic Power Generation Data Set Introduction
As an important component of renewable energy, the accurate prediction of photovoltaic power generation is crucial for the dispatch optimization of power systems and the efficient utilization of renewable energy.
2.1 Importing Data
The photovoltaic power generation dataset consists of 2053 samples with 8 features, as visualized below:

2.2 Data Collection and Preprocessing
For detailed instructions, please refer to the provided documentation!
3. High-Innovative Prediction Model Based on WT-TimeMixer
3.1 Definition of WT-TimeMixer Prediction Network Model
3.2 Setting parameters and training the model
Trained for 50 epochs, with MSE of 0.00721, the WT-TimeMixer prediction effect is significant. This model, by drawing inspiration from TimeMixer's multi-scale decomposition mixing idea, reconstructs the frequency-scale space through multi-layer wavelet decomposition, further introduces frequency-aware directional cross-scale propagation, low-frequency-high-frequency gate control fusion, and sample adaptive multi-predictor fusion, thereby achieving more precise, stable, and interpretable photovoltaic power generation prediction.
4. Results Visualization and Model Evaluation
4.1 Prediction Results Visualization
4.2 Model Evaluation
1. WT-TimeMixer establishes explicit frequency-scale hierarchies through wavelet decomposition, utilizing a bidirectional directional mixing mechanism of "low frequency coarse to fine, high frequency fine to coarse" to facilitate the interaction of historical multi-scale information. It then completes future predictions through adaptive multi-predictor fusion, providing a predictive framework that balances frequency priors, multi-scale modeling, and dynamic scale selection for strong non-stationary time series such as photovoltaic power.

Click to download: Full text data, Python code

Previously outstanding content:
Informer prediction model collection: New feature importance analysis!
Fast Fourier Transform violent growth points! Highly innovative time series classification model based on time-frequency feature fusion
!STL-VMD secondary decomposition + Informer-LSTM parallel prediction model
Continued updates! Attention mechanism + Lithium Battery Remaining Life Prediction Collection
Direct writing in one area! CEEMDAN decomposition + Informer-LSTM +XGBoost combined prediction model
Continuing updates! Attention mechanism + Lithium Battery Remaining Life Prediction Collection
Comparative prediction models based on Informer-SENet for photovoltaic power generation forecasting! Six sets of comparative prediction models, directly written for graduation theses or minor papers!
!Based on ICEEMDAN+SHAP explainable analysis for Lithium Battery Remaining Life Prediction High Innovation Model!
!Based on Informer-BiGRUGATT-CrossAttention for prediction models
High innovation! Based on ICEEMDAN+MSCNN-BiGRU-Attention parallel prediction model
Air Quality PM2.5 Concentration High Innovation Forecasting Model! Based on VMD rolling decomposition + attention mechanism for parallel prediction model
End

## Images

<!-- PAYMENT_BLOCK -->

## Get this dataset

- Payment link (Stripe): [Buy now](https://buy.stripe.com/3cs8yP7sY87d0vu9AB)
- Payment QR code: ![Payment QR code](pay.png)

<!-- /PAYMENT_BLOCK -->

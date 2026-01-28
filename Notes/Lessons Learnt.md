# Cursory view of few Lessons Learned (not sorted though)


##1. It is possible to use the features available in Walmart Dataset to construct a ML model and proceed with Sales Prediction. However in this project, we are using only lag-based features &  optionally calendar features & deliberately avoiding identifiers & categorical entity features.
    
##2. Endogenous / Time derived  features mean Lagged Sales, Rolling average of sales and Differences in sales. In the Walmart dataset, true exogenous drivers for time-series forecasting are limited (mainly price and calendar effects); most other fields are entity descriptors that help segmentation but do not represent external drivers of temporal behavior. 
   
##3. When the data pattern is smooth, continuous and well-behaved,simpler linear lag models (AR-style) often outperform complex ML ones. But for volatile or irregular data, tree-based or neural models may shine — because they can capture regime changes and nonlinear effects.
    
##4. Each model in time series has its own scope – ML model works well when with tabular data, non linear relationship (sudden spikes), moderate volume (not too gigantic) & we have good features (lags, rolling average and calender flags). Linear model works well for medium size models with clear trend and seasonality.
    
##5. A general model (ARIMA and ML model) is one that can represent a wider class of data-generating processes, even if that flexibility is not needed. A simple model (Holt and Linear model) is one that imposes strong structural assumptions and has limited degrees of freedom. When the data does not contain stable structure, Simple models ignore noise, impose smoothness, extrapolate conservatively & win in situations of short series, noisy systems & weak signal environments
   
##6. Linear and controlled-capacity ML models are identical in how we practice time-series modeling; they differ only in how flexibly they can use the same injected information, not in what information they have access to
    
##7. In time-series modeling, neither single hold-out validation nor pure expanding-window evaluation provides a natural separation between validation and test data. In single hold-out validation, the final future block implicitly serves both validation and test roles, while in pure expanding-window evaluation, all future points are used as rolling one-step-ahead validation targets with no dedicated test set.
    
##8. Lags are used in train, val, and test — always. During Training period,  lags are filled with historical actuals that already exist. During Validation/Test, lags are still filled with actual past values, not predictions. Lags help training because the future already happened; they help forecasting only if history repeats locally.
    
##9. Training is good because the model learns post-event patterns, but it is never perfect because lagged history is an incomplete, ambiguous, and averaged representation of the past. If a spike has no unique fingerprint in the lag features, no model can reproduce it exactly — not even in training.
    
##10. Joint normalization means applying the same normalization transform for both Sales (target) and its lagged versions (features) and usually fitted once on the entire dataset. Joint normalization ≠ always wrong; However Joint normalization + global fitting = wrong
   
##11. MAD-based detection can be a final structure test before we accept that the system is fundamentally noisy because it is better yard stick over median. 
    
##12. “Oracle plot” is not a formal statistical term. This  can significantly reduce error on the largest spikes but substantial unexplained variability will remain. This experiment can only further prove the intrinsic unpredictability rather than describing model insufficiency.

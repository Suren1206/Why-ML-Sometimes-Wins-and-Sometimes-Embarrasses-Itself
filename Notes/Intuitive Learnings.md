#Learning through Intuitions

##It is always complained that LLMs hallucinate. I was enriched with the positive side of this aspect benefiting with cream of learning through the rich visualizations and effective intuitions that ChatGPT provided me during. As this was a fast track project for me, the examples provided not just helped me to a quick decision on next steps but also made the project journey a pleasurable one. These intuitions emerged through extended exploration and discussion during the project.
<<The last one below is mine when I was deep into the event indicators if they provide any predictability. When I mentioned this, ChatGPT validated that this is a valid analogy to explain central tendancy (median) and dispersion (standard deviation>>

Sharing few of the intuitions which were contextual but quite self explanatory
       
    • “A model’s job is not to explain everything, but to discover what cannot be explained without lying” 
    • Lags Versus Data Split : ‘Using 12 lags” like saying “I’ll always look at the last year’s worth of clues.”. Training teaches the model how much to trust each of those clues. Testing checks whether those learned weights still make sense when new months arrive.
    • More lags ≠ more memory; More lags in linear models often mean more confusion.
    • Sparse model is Like four people, each with a clear job; Dense model is Like 13 people shouting conflicting advice
    • Weekly lags chosen at [1, 4, 12, 52] represent calender memory : lag_1 → touch; lag_4 → short memory; lag_12 → rhythm & lag_52 
    • If you encode something like -2, -1, 0, +1, +2, you are telling the ML model “These regimes lie on a continuous severity scale.”  If you one-hot encode like trough, low, normal, high and peak you are telling it “These are separate worlds. Do NOT assume continuity.” T
    • Sparse lags help to diagnosing what kind of memory the system has instead of assuming entire recent history will matter.
    • This project asks: “Can ML learn anything meaningful about time behavior when structure is weak?” Entity descriptors would answer a different question:  “Which store/product usually sells more?”. That would make ML succeed without learning time dynamics at all.
    • In ARIMA, transformations exist to satisfy the model; In ML, transformations are optional tools for reframing the signal, not obligations imposed by the model.
    • Normalization leakage does not tell the model the future; it tells the model how afraid it should be of the future — and removes that fear.
    • Event indicators are not about prediction — they are about explanation. We are not trying to say:
    • “The model now predicts Black Friday spikes.”; We are trying to ask:“Is Walmart demand behavior conditional on known retail events?” In short Exogenous features are hypotheses about behavior, not knobs for accuracy
    • Weekly data is the primitive. Month-level medians test baseline shifts; month-conditioned weekly variance tests instability. Failure of the first does not invalidate the second.
    • If I want to understand how the school performs overall, I can look at class-wise averages. If I want to understand how girls are doing, I shouldn’t average the class and then zoom in — I should directly look at girls within each class.
      

# GMMA_AIforecast
Guppy Multiple Moving Average trading augmeted with AI to predict future time frames

The define_target_condition tries to predict the given number of timeframes in the future.
Each time frame, Exponential Moving Average, predicting time frame can be custom designed. 
Once trained, implementation is quite fast and multiple models can be loaded to serve as a GMMA that moves ahead of time. Indicators crossings can be used to decide when to take action.
```python
def define_target_condition(df):
 
    # price above trend multiple days later
#    df['target_cls'] = np.where(df['close'].shift(-34) > df.EMA150.shift(-34), 1, 0)
#    df['target_cls'] = np.where(df['close'].shift(-15) > df.EMA150.shift(-15), 1, 0)
#    df['target_cls'] = np.where(df['close'].shift(-5) > df.EMA150.shift(-5), 1, 0)
#    df['target_cls'] = np.where(df['close'].shift(-5) > df.EMA5.shift(-5), 1, 0)
#    df['target_cls'] = np.where(df['close'].shift(-5) > df.EMA15.shift(-5), 1, 0)

    df['target_cls'] = np.where(df['close'].shift(-5) > df['resistance'].shift(-5), 1, 0)
#   df['close'].shift(-5) > df['-' + str(sigma) + 'σ'].shift(-5)
#    df['target_cls'] = np.where( (df['STC_INDICATOR'].shift(-5)  >  df['STC_INDICATOR'].shift(-4)) & (df['STC_INDICATOR'].shift(-5) > 20), 1, 0) 
```  

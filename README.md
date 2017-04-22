### First place solution for How Much Did it Rain?

For a description of my solution see this [blog post](http://blog.kaggle.com/2015/07/01/how-much-did-it-rain-winners-interview-1st-place-devin-anzelmo/) on kaggle, or this [forum post](https://www.kaggle.com/c/how-much-did-it-rain/discussion/14242#78604) 

### Running

This should run with python 3 and the newest version of xgboost.The following folders should be in the top level directory, input, code, processed, models, output. 
Look at `documentation.pdf` for required directory structure and other information on running the code. Put `train_2013.csv` and `test_2014.csv` into the input folder. Run ./main.sh in the code folder.

### For faster run time 

Simple Features and methods
In train_subset4.py and train_subset5.py change the line `use_xtra_features = 
True` to `False`.

In `main.sh` comment out the lines 

`./make_xtra_features_train.sh` and `./make_xtra_features_test.sh`.

In make_predictions.py change the line with

`fn.make_prediction4(......use_xtra_features=True)` to
`fn.make_prediction4(.....use_xtra_features=False)`,

 repeat for

`fn.make_prediction5(....)`

Now run main.sh and it should shave off ~5 hours of run time. Final CRPS of about 0.00750.

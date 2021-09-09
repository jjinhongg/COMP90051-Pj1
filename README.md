# COMP90051-Pj1
# How to run
put train.csv and test.csv in the master folder, go into st-gcn folder, run preprocess.ipynb, choose the needed cell including minmax scaler and smote strategies to run, the processed data is saved as train.npy, label.pkl for train data and test.npy, label_test.pkl for test data.

Navigate to st-gcn folder, run ` python3 gen_tfrecord_data.py --label-path label.pkl --shuffle true --data-path train.npy --dest-folder tfrecord`
` python3 gen_tfrecord_data.py --label-path label_test.pkl --shuffle true --data-path test.npy --dest-folder tfrecord_test`

Run main.ipynb, make sure train-data-path and test-data-path(validation) are declared correctly, as well as test data path in main(), the result is saved as output.csv.

# To Ensemble Predictions
Simple Voting Ensemble: 
$ python ./src/kaggle_vote.py "./samples/method*.csv" "./samples/kaggle_vote.csv" 

Weighted Voting Ensemble:  
file name according to weights: _w3_method1.csv  
$ python ./src/kaggle_vote.py "./samples/_*.csv" "./samples/kaggle_vote_weighted.csv" "weighted" 

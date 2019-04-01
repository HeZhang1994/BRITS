# Description - proj2019
The source codes of RITS-I, RITS, BRITS-I, BRITS for health-care data imputation/classification (NeurIPS).

## Requirement

* __Python 2__

* __ujson__

* __ipdb__

others

## Usage

To run the code:

python main.py --epochs 1000 --batch_size 32 --model brits

## Data Format
In json folder, we provide the sample data (400 patients).
The data format is as follows:

* ./json/json file has 400 lines - represent health data of 400 patients
* Each line in ./json/json is a <str> represents a python dict, after using `json.loads()` function, we get a <dict>
* The structure of each dict is (i.e., the <dict> has 3 keys)
    * forward
    * backward
    * label

    'forward' and 'backward' is a list of python dicts, which represents the input sequence in forward/backward directions. As an example for forward direction, each dict in the sequence contains:
    * values: list, indicating x_t \in R^d (after elimination)
    * masks: list, indicating m_t \in R^d
    * deltas: list, indicating \delta_t \in R^d
    * forwards: list, the forward imputation, only used in GRU_D, can be any numbers in our model
    * evals: list, indicating x_t \in R^d (before elimination)
    * eval_masks: list, indicating whether each value is an imputation ground-truth

## Data Download Links

* Air Quality Data:
URL: https://www.microsoft.com/en-us/research/wp-content/uploads/2016/06/STMVL-Release.zip

* Health-care Data:
URL: https://physionet.org/challenge/2012/
We use the test-a.zip in our experiment.

* Human Activity Data:
URL: https://archive.ics.uci.edu/ml/datasets/Localization+Data+for+Person+Activity

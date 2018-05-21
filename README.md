# dpSubsetSelect

## Introduction
dpSubsetSelect is the software to implement the algorithm in the paper "Selecting Optimal Subset to Release Under Differentially Private M-Estimators from Hybrid Datasets". Please contact <mengw1@stanford.edu> for bugs. 

## Setup
### Dependencies 
* [R](https://www.r-project.org/) (version >= 3.3.0)


### Installation (Mac OS X/Linux)
1. Download dpSubsetSelect:    
`git clone https://github.com/mwgrassgreen/dpSubsetSelect.git`

2. Add execute permissions for [dpSubsetSelect.sh](https://github.com/mwgrassgreen/dpSubsetSelect/blob/master/dpSubsetSelect.sh):     
`cd dpSubsetSelect`    
`chmod a+x dpSubsetSelect.sh`

# Usage 
./dpSubsetSelect.sh --prefixPrvData --prefixPubData --numIndStart --numIndEnd --catIndStart --catIndEnd --eps --kStart --kEnd --kBy

# Options
  
  --prefixPrvData The file name and location for the private dataset.
  
  --prefixPubData The file name and location for the public dataset.
  
  --numIndStart	The starting column index for the numerical variables.
  
  --numIndEnd	The end column index for the numerical variables.
  
  --catIndStart	The starting column index for the categorical variables.
  
  --catIndEnd	The end column index for the categorical variables.
  
  --eps=privacy\_budget 	The privacy budget (recommend eps <=3).
  
  --kStart The initial number of public points to release.
  
  --kEnd The last number of public points to release.
  
  --kBy The segment of numbers of public data points to release.
  
# Example
  ./dpSubsetSelect.sh --prefixPrvData=./raw_data/raw_private_dataset.csv --prefixPubData=./raw_data/raw_public_dataset.csv  
  --numIndStart=2 --numIndEnd=3 --catIndStart=1 --catIndEnd=1 --eps=0.5 --kStart=10 --kEnd=1000 --kBy=100

# Output
 The outputs are (1) the selected optimal public subset under DP, (2) the estimated parameters in the logistic regression from the selected subset, (3) prediction errors results and their trend plot. 

## License
This project is licensed under the GNU General Public License v3.0 (see the [LICENSE](https://github.com/mwgrassgreen/dpSubsetSelect/blob/master/LICENSE) file for details).    



# HubPPR


## Environment and Preparation
Lib requirement: Boost version>=boost1.55 (tested on Ubuntu)

The following manual assumes that you are in the code repository.

Pre-compile: type cmake in terminal, <br>
$cmake . <br>

Compile: type make in terminal, i.e.,<br>
$make

Allow the test scripts to run <br>
$chmod +x *.sh <br>


Dataset format: <br>
Assume that we have a folder ./dataset which stores all the testing datatsets.<br> 
Each dataset will include an own folder in this directory. For instance, the dblp dataset will be in a folder named ./dataset/dblp/, and includes two files: attribute.txt, graph.txt.<br>
The ./dataset/dblp/attribute.txt file includes the information of the node and edge:<br>
n=613586<br>
m=3980318<br>

The dataset/dblp/graph.txt file includes the information of each edge in the form of "sourceid targetid" on each line. For instance, the first three lines of dataset/dblp/graph.txt includes:<br>
0 1<br>
0 2<br>
0 3<br>
...<br>

indicating that there are three edges starting from node 0, and ending at 1, 2, and 3 respectively<br>

## Generate query
$./generate-query.sh dataset-name dataset-dir<br>
For instance, to generate query for dblp dataset, we then run the script as: <br>
$./generate-query.sh dblp ./dataset/


## Hub selection
$./select-hub.sh dataset-name  dataset-dir<br>
For instance, to geenrate hubs for dblp dataset, we then run the script as:<br>
$./select-hub.sh dblp ./dataset/


## Build index for HubPPR

$./build-index.sh dataset-name dataset-dir<br>

## Run p2p query with HubPPR 
$./run-hubppr.sh dataset-name dataset-dir<br>

## Run top-k query with HubPPR
$./topk-hubppr.sh dataset-name dataset-dir k_size T_size<br>

For instance, to test on dblp with k=8 and target set size |T| = 400, we run the following command:<br>
$./topk-hubppr.sh dblp ./dataset 8 400<br>






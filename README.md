# crsf
# Accurate and Fast Time Series Classification based on Compressed Random Shapelet Forest



## Introduction

Achieving accurate, fast and interpretable time series classification (TSC) has attracted considerable attentions from data mining community over the past decade. In this paper, we propose an efficient algorithm, called compressed random shapelet forest (CRSF), to tackle this problem. Different from most of the shapelet-based TSC methods, CRSF obtains promising performance by greatly compressing the shapelet features space. In order to achieve the aim of compression, the time series dataset as well as the shapelets are represented by symbolic aggregate approximation (SAX) at first. Then, the shapelet-based decision trees are built upon a pool of high-quality shapelet candidates from which the useless shapelets and the self-similar shapelets have been pre-pruned. A new function for measuring distance between two SAX-represented time series is also introduced. Extensive experiments were conducted on 50 UCR time series datasets. The results show that, (1) CRSF can achieve the highest average accuracy on the datasets and it outperforms most of the existing shapelet-based TSC methods; (2) CRSF is slightly superior to gRSF in terms of accuracy and is significantly superior to gRSF in terms of the time cost. Specifically, it is averagely 41 times faster than gRSF according to the experimental results.

## Experimental Results

- [50 datasets](http://tsdm.lsnu.edu.cn/crsf/results/01-Dataset.csv) from [UCR Archive](https://www.cs.ucr.edu/~eamonn/time_series_data_2018/)
- [All accuracy](http://tsdm.lsnu.edu.cn/crsf/results/accuracy.pdf) of 50 datasets(.pdf)
- [Download all results](http://tsdm.lsnu.edu.cn/crsf/results/results.zip)(.csv)
- CD diagram of average rankings compared with 7 classifiers ![CD Diagram](http://tsdm.lsnu.edu.cn/crsf/img/Figure_03-CDDiagram.svg)
- Speedup ratio compared with gRSF ![Speedup Ratio compared with gRSF](http://tsdm.lsnu.edu.cn/crsf/img/Figure_04-Speedup.svg)

## Binary Code

We implemented the proposed algorithm CRSF in Java.

- Download
  You can download the [binary code](http://tsdm.lsnu.edu.cn/crsf/code/CRSF.zip) compressed with password, and you can get the password by contacting with [yangjun192@mails.ucas.ac.cn](mailto:yangjun192@mails.ucas.ac.cn).

- Usage

  \>>java -jar CRSF.jar arguments

  Arguments:
  -tr train_file: train file path, can be absolute or relative
  -ts test_file: test file path, can be absolute or relative
  -sax 1 omega alphabeta_size: omega is the window size and alphabeta is between 3 and 10
  [-zn]: optional, if the time series should be z-normalized first
  [-t tree_size]: optional, specify the number of trees to generate, default as 300
  [-times run_times]: optional, iterate times, default as 1

- Example

  If we want to run this algorithm on UCR dataset ECG200, and adopt 8 as the window size and 6 as the alphabeta size, we can follow the command line:
  \>>java -jar CRSF.jar CRSF -tr ECG200_TRAIN -ts ECG20_TEST -sax 1 8 6 -zn

## References

- Bagnall, A., Lines, J., Bostrom, A., Large, J., & Keogh, E. (2017). The great time series classification bake off: a review and experimental evaluation of recent algorithmic advances. Data Mining and Knowledge Discovery, 31, 606-660.
- Grabocka, J., Schilling, N., Wistuba, M., & Schmidt-Thieme, L. (2014). Learning time-series shapelets. In Proceedings of the 20th ACM SIGKDD international conference on Knowledge discovery and data mining (pp. 392-401).
- Karlsson, I., Papapetrou, P., & Boström, H. (2016). Generalized random shapelet forests. Data Mining and Knowledge Discovery, 30, 1053-1085.
- Li, G., Choi, B., Xu, J., Bhowmick, S. S., Chun, K.-P., & Wong, G. L. H. (2021). Efficient Shapelet Discovery for Time Series Classification (Extended Abstract). In 2021 IEEE 37th International Conference on Data Engineering (ICDE) (pp. 2336-2337).
- …

## Acknowledgement

Thanks the research community for supporting the datasets.

------

© 2021,LSNU Time Series Data Mining Group.

# CONO
Unsupervised cross-domain image retrieval based on noise pseudo-tags

Authors: Xiaoyun Ren, Qingchuan Tao, Yanmei Yu, Yongxiang Li

### Abstract


### Framework


### Requirements
```
pip install requirements.txt
```

### Datasets
The OfficeHome dataset could be downloaded from https://www.hemanthdv.org/officeHomeDataset.html.

The Office31 and image_CLEF dataset could be downloaded from https://github.com/jindongwang/transferlearning/tree/master/data.

The directory structure of datasets.

```
  --officehome
       --Art
       --Clipart
       --Real_World
       --Product
  --office31
       --amazon
       --dslr
       --webcam
       --...
  --...
```
### Quickly Training

#### Preheat to get fake tags
```
python train_setup1.py
```
At the end of the UCLS step, false labels with noise and image features corresponding to the data set class are obtained.
Then NPLS is used to train the noisy data.(You need to enter UCRP_TRIAN2 to properly start python train_setup2.py)
#### Noise pseudo-label training
```
python train_setup2.py
```

### Comparison with the State-of-the-Art Methods
We conducted UCRP unsupervised cross-domain image retrieval on three datasets to evaluate the performance of UCRP and other methods.The specific comparative experimental data of the three data sets are shown below.

![4](https://github.com/user-attachments/assets/8c559741-1033-44a2-a1f2-efd14e2056a6)

![5](https://github.com/user-attachments/assets/8245d05a-ad3e-41fe-b39a-9114e794605a)

![7](https://github.com/user-attachments/assets/3fdf36ca-cf8d-4303-babe-f942fb0b201c)


### Ablation Study
In the study of ablation experiments, the important role of each component is verified. LMAAD and LNCL in UCLS and NPLS can perform ablation experiments on each module. Here, we give the experimental results of the representative image_CLEF dataset, as shown in Table.

![2](https://github.com/user-attachments/assets/72a2deb4-011a-4c37-a2dd-6dd72c0d9d6b)

At the same time, we compared the three mainstream clustering methods, and finally chose K-means to be more advantageous. The data of the three clustering methods on the office31 dataset is shown below.

![9](https://github.com/user-attachments/assets/3d8f5739-8860-4449-8f4b-fd5436da629f)


### Example of Retrievals
In this Table, we present a comparison between the UCRP method and the CoDA method, showcasing their respective retrieval capabilities using examples from the OfficeHome dataset. This comparison aims to underscore the reliability and superiority of our approach in cross-domain image retrieval. For instance, consider a scenario where we retrieve an image of a pen from the Art domain and search for similar images.

![3](https://github.com/user-attachments/assets/88bfef80-94ca-4359-8e49-24e8098803ad)

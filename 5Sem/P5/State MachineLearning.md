# New (09.12.24)

> [!warning] **Har måske allerede kigget på?**
> - [SoK: Visualization-based Malware Detection Techniques](https://dl.acm.org/doi/fullHtml/10.1145/3664476.3664514)


> [!NOTE] **Måske brugbare**
> - Image-Based Malware Detection: [link](https://encyclopedia.pub/entry/51565)

## [Malware Classification and Visualization Using EfficientNet and B2IMG Algorithm](https://ieeexplore.ieee.org/document/9923524)


> [!NOTE] Plus
> TIlhørende **[GitHub link](https://github.com/theDreamer911/efficientnet-malware-big2015?tab=readme-ov-file)**

Signature-based and heuristic methods have already been used in malware classification for a long time, but since the growth of polymorphic, both methods have become irrelevant.This problem makes machine learning and deep learning popular to overcome this problem. 

**EfficientNet** is one of the transfer learning models, a deep learning subfield. this model could beat the state of the art of deep learning classification in **ImageNet.** mplemented several EffiicientNet models into two type of Malware BIG 2015 that had been **visualized into grayscale and RGB format.**


## [On Challenges in Evaluating Malware Clustering](https://link.springer.com/chapter/10.1007/978-3-642-15512-3_13?fbclid=IwZXh0bgNhZW0CMTAAAR0m7h5wfehApRuB3NyihnncXI67-fxdxRKQdN3wp685vIfVF_HF2vRFnwY_aem_FL9ZaPYVnW_JPZCS3wOX_w) 


# Datasets
## [Virus-MNIST: A Benchmark Malware Dataset](https://arxiv.org/abs/2103.00602)
image classification dataset consisting of 10 executable code varieties and approximately 50,000 virus examples. The malicious classes include 9 families of computer viruses and one benign set

[Human computer interaction](https://www.researchgate.net/profile/Daqing-Hou/publication/322877650_Shared_dataset_on_natural_human-computer_interaction_to_support_continuous_authentication_research/links/5b9d115c299bf13e60326c9a/Shared-dataset-on-natural-human-computer-interaction-to-support-continuous-authentication-research.pdf) 

[Human Errors Fuel Hacking as test shows nothing stops idiocy](https://www.bloomberg.com/news/articles/2011-06-27/human-errors-fuel-hacking-as-test-shows-nothing-prevents-idiocy?embedded-checkout=true)

[7 Deadliest USB Attacks (book)](https://books.google.dk/books?hl=en&lr=&id=T6jzJkqNonkC&oi=fnd&pg=PP1&ots=oRc73q4cYq&sig=E75L7LeF1cRG6lHpe0bcpCnAk08&redir_esc=y#v=onepage&q&f=false)

[Data Hiding Tactics for windows and uni file systems](https://www.sciencedirect.com/science/article/abs/pii/S0065245808006013)

[USB Firewall apparatus and method](https://patents.google.com/patent/US8646082B2/en) US8646082B2

[Nok nogle gode links her](https://scholar.google.com/scholar?hl=en&as_sdt=0%2C5&q=preventing+usb+device+firmware+attacks+Lumension&btnG=) (Preventing usb device firmware attacks lumension)
## [BODMAS: An Open Dataset for Learning based Temporal Analysis of PE Malware](https://ieeexplore.ieee.org/abstract/document/9474321)
By closely examining existing open PE malware datasets, we identified two missing capabilities (i.e., recent/timestamped malware samples, and well-curated family information), which have limited researchers’ ability to study pressing issues such as concept drift and malware family evolution.

we release a new dataset to fill in the gaps. The BODMAS dataset contains 57,293 malware samples and 77,142 benign samples collected from August 2019 to September 2020, with carefully curated family information (581 families). We also perform a preliminary analysis to illustrate the impact of concept drift

## [The MalSource Dataset: Quantifying Complexity and Code Reuse in Malware Development](https://ieeexplore.ieee.org/abstract/document/8568018)
we analyze the evolution of malware from 1975 to date from a software engineering perspective. We analyze the source code of 456 samples from 428 unique families and obtain measures of their size, code quality, and estimates of the development costs (effort, time, and number of people). Our results suggest an exponential increment of nearly one order of magnitude per decade in aspects such as size and estimated effort, with code quality metrics similar to those of benign software. We also study the extent to which code reuse is present in our dataset. We detect a significant number of code clones across malware families and report which features and functionalities are more commonly shared. Overall, our results support claims about the increasing complexity of malware and its production progressively becoming an industry.

## [Microsoft Malware Classification Challenge](https://arxiv.org/abs/1802.10135)

## MOTIF
[MOTIF: A Malware Reference Dataset with Ground Truth Family Labels](https://www.sciencedirect.com/science/article/abs/pii/S0167404822003133?fbclid=IwZXh0bgNhZW0CMTAAAR3pKk8Js-lPaLu__nSTjqJtuTSVwv_lzH2YHPtdYCwE0xmKWo9nAZtAIf4_aem_0LJd--FDgvzTDmzRmyT4fg)
[MOTIF: A Large Malware Reference Dataset with Ground Truth Family Labels](https://arxiv.org/abs/2111.15031)
- contains **3,095 malware samples** from **454 families**, making it the largest and most diverse public malware dataset with ground truth family labels to date, *nearly larger than any prior expert-labeled corpus and **larger than the prior Windows malware corpus.***
	- Classifcation of Malware families (warning about noise created from bad labeling approaches)
	- Malware Open-source Threat Intelligence Family

## Ember Dataset
### [EMBER: An Open Dataset for Training Static PE Malware Machine Learning Models](https://arxiv.org/abs/1804.04637?fbclid=IwZXh0bgNhZW0CMTAAAR2rWGmkp_lLlsXIpTIPRpPLNTzTHezZc6XUBdNO9QsYJJg5807ezVU9STA_aem_pTJvlfdulFTJIpxz5QH4rA)
[https://arxiv.org/abs/1804.04637](https://arxiv.org/abs/1804.04637?fbclid=IwZXh0bgNhZW0CMTAAAR2rWGmkp_lLlsXIpTIPRpPLNTzTHezZc6XUBdNO9QsYJJg5807ezVU9STA_aem_pTJvlfdulFTJIpxz5QH4rA)
Endgame Malware BEnchmark for Research (EMBER) dataset1 , extracted from a large corpus of Windows portable executable (PE) malicious and benign files. This allows free dissemination of both malicious and benign entities without legal or security concerns. Samples are released together with the sha256 hash of the original file, and a label to denote whether the file is deemed to be malicious or benign
### [Identifying Useful Features for Malware Detection in the Ember Dataset](https://ieeexplore.ieee.org/abstract/document/8951564)
- **Identifying Useful Features for Malware detection**
	- he task of distinguishing between malware and benign programs by learning their surface features, such as general file information and imported functions. **To make such attempts practical, a good balance among accuracy, learning time, and feature-data sizes is required**
	- we present a case study of feature selection in malware detection based on supervised machine learning. We used the Ember dataset as the target data and identified useful combinations of features in terms of accuracy, learning time, and data size.

# Kig på dem her
## [Detection of Advanced Malware by Machine Learning Techniques](https://link.springer.com/chapter/10.1007/978-981-13-0589-4_31?fbclid=IwZXh0bgNhZW0CMTAAAR1g7PJEcU8o8TuvDysHQLBodTY8DWYQDn3q1b1NTH-N13JvpTbZWtUHmCU_aem_S6J2-8zzOjpSNCqG5NTaFA) 
In today’s digital world most of the anti-malware tools are signature based, which is ineffective to detect advanced unknown malware, viz. metamorphic malware

In this paper, we study the frequency of opcode occurrence to detect unknown malware by using machine learning technique
### Feature Selection
Feature selection is an important part of machine learning. In the proposed approach, there are 1808 features among them many do not donate to the accuracy and even decrease it. In our problem, reduction of features is crucial to maintaining accuracy. Thus, we first used _Fisher Score (FS)_ [19](https://link-springer-com.zorac.aub.aau.dk/chapter/10.1007/978-981-13-0589-4_31#ref-CR19 "Golub, T.R., et al.: Molecular classification of cancer: class discovery and class prediction by gene expression monitoring. Science 286(5439), 531–537 (1999)") for feature selection and later four more feature selection techniques were also studied. The five feature selection method employed in this approach which functions according to the filters approach [20](https://link-springer-com.zorac.aub.aau.dk/chapter/10.1007/978-981-13-0589-4_31#ref-CR20 "Dietterich, T.G.: Machine learning in ecosystem informatics and sustainability. In: Proceedings of the Twenty-First International Joint Conference on Artificial Intelligence, pp. 8–13 (2009)"). In this method, correlation of each feature with the class (Malware or benign) is quantified, and its contribution to classification is calculated. This method is independent of any classification algorithm unlike wrapper approach and allows to compare the performance of different classifiers. In this approach, _Fisher Score (FS), Information Gain (IG), Gain Ratio (GR), Chi_-_Square (CS) and Uncertainty Symmetric (US)_ is used. Based on these feature selection measures, we have selected top 20 features as shown in Table [1](https://link-springer-com.zorac.aub.aau.dk/chapter/10.1007/978-981-13-0589-4_31#Tab1)
### Training the classifiers
After the feature selection, next step is to find the best classifier for the detection of advanced malware. Next step is to compare different classifiers on FS, IG, GR, CS and US using top 20 features. We studied nine classifiers, viz. Decision Stump, Logistic Model Tree (LMT), Random Forest, J48, REPTREE, Naïve Bayes Tree (NBT), J48 Graft, Random Tree, Simple CART available in WEKA. WEKA is an open-source GUI-based machine learning tool. We run all these classifiers on each feature selection technique using tenfold cross-validation to train the classifiers.
**it is clear that Fisher score method is best in among all and got accuracy 100% in case of Random Forest, LMT, NBT and Random Tree. So in our proposed, Fisher Score performs better than other methods, viz. Information Gain (IG), Gain Ratio (GR), Symmetrical Uncertainty and Chi-square.**
![[Pasted image 20241007112121.png]]
### Unknown Malware Detection
In an earlier section, we have noticed that Random Forest, LMT, NBT, J48 Graft and Random Tree achieved maximum accuracy, so we selected these five classifiers for depth analysis. We have randomly selected 3005 malware and 2286 benign programs which are 50% of the overall dataset.

### Conclusion
 we have presented an approach based on opcodes occurrence to improve malware detection accuracy of the unknown advanced malware. Code obfuscation technique is a challenge for signature-based techniques used by advanced malware to evade anti-malware tools. Proposed approach uses Fisher score method for the feature selection and five classifiers used to uncover the unknown malware. In the proposed approach Random forest, LMT, J48 Graft, and NBT detect malware with 100% accuracy which is better than the accuracy (99.8%) reported by Ahmadi et al. (2016). In future, we will implement proposed approach on different datasets and will perform in the deep analysis for the classification of advanced malicious software.

## [An effective approach for classification of advanced malware with high accuracy](https://arxiv.org/abs/1606.06897)
Combating malware is very important for software/systems security, but to prevent the software/systems from the advanced malware, viz. metamorphic malware is a challenging task, as it changes the structure/code after each infection. Therefore in this paper, we present a novel approach to detect the advanced malware with high accuracy by analyzing the occurrence of opcodes (features) by grouping the executables. These groups are made on the basis of our earlier studies [1] that the difference between the sizes of any two malware generated by popular advanced malware kits viz. PS-MPC, G2 and NGVCK are within 5 KB. On the basis of obtained promising features, we studied the performance of thirteen classifiers using N-fold cross-validation available in machine learning tool WEKA. Among these thirteen classifiers we studied in-depth top five classifiers (Random forest, LMT, NBT, J48 and FT) and obtain more than 96.28% accuracy for the detection of unknown malware, which is better than the maximum detection accuracy (95.9%) reported by Santos et al (2013). In these top five classifiers, our approach obtained a detection accuracy of 97.95% by the Random forest.

## [Malware Classification with Deep Convolutional Neural Networks](https://ieeexplore-ieee-org.zorac.aub.aau.dk/document/8328749)

## [Convolutional Neural Networks for Malware Classification](https://www.covert.io/research-papers/deep-learning-security/Convolutional%20Neural%20Networks%20for%20Malware%20Classification.pdf)
## [Malware images: visualization and automatic classification](https://dl.acm.org/doi/10.1145/2016904.2016908)
Malware binaries are visualized as gray-scale images, with the observation that for many malware families, the images belonging to the same family appear very similar in layout and texture. Motivated by this visual similarity, a classification method using standard image features is proposed. Neither disassembly nor code execution is required for classification. Preliminary experimental results are quite promising with 98% classification accuracy on a malware database of 9,458 samples with 25 different malware families. Our technique also exhibits interesting resilience to popular obfuscation techniques such as section encryption.

## [Very Deep Convolutional Networks for Large-Scale Image Recognition](https://arxiv.org/abs/1409.1556)
In computer vision, researchers have shown that deeper CNN architectures (e.g. [7]) are helpful in minimizing error for image classification tasks. In this paper, we take the approach of vision researchers and adopt their technique for malware classification.
## [Grouping the executables to detect malwares with high accuracy](https://www-sciencedirect-com.zorac.aub.aau.dk/science/article/pii/S1877050916001174)
The metamorphic malware variants with the same malicious behavior (family), can obfuscate themselves to look different from each other. This variation in structure lead to a huge signature database for traditional signature matching techniques to detect them. In order to effective and effcient detection of malwares in large amounts of executables, we need to partition these files into groups which can identify their respective families.
In addition, the grouping criteria should be chosen such a way that, it can also be applied to unknown files encounter on computer for classification.

We studied sizes of malwares generated by three popular second generation malwares (metamorphic malwares) creator kits viz. G2, PS-MPC and NGVCK, and observed that the size variation in any two generated malwares from same kit is not much. Hence we grouped the executables on the basis of malware sizes by using Optimal k-Means Clustering algorithm and used these obtained groups to select promising features for training (Random forest, J48, LMT, FT and NBT) classifiers to detect variants of malwares or unknown malwares. We find that detection of malwares on the basis of their respected file sizes gives accuracy up to 99.11% from the classifiers.
## [Polymorphic malware detection using sequence classification methods and ensembles](https://link-springer-com.zorac.aub.aau.dk/article/10.1186/s13635-017-0055-6)
The evolution of malware is much akin to mutations in biological sequences. Recently, high-throughput methods for gene sequence classification have been developed by the bioinformatics and computational biology communities.

we apply methods designed for gene sequencing to detect malware in a manner robust to attacker adaptations.

Whereas most gene classification tools are optimized for and restricted to an alphabet of four letters (nucleic acids), we have selected the _Strand_ gene sequence classifier for malware classification. Strand’s design can easily accommodate unstructured data with any alphabet, including source code or compiled machine code.




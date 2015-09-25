#Deep learning for computer vision tasks

Deep Machine Learning has been declared the new frontier in artificial intelligence research in 2010 in [@Arel2010][1].

The Convolutional Neural Networks (CNN) are a type of deep learning networks, [2]. CNNs are a family of multi-layer neural networks particularly designed for use on two-dimensional data, such as images. For quick introduction to CNNs, please refer to section 2.3 of the “Large-scale Computer Vision” overview on NLeSc’s MLPR’s interest group page. For a more elaborate introduction, please refer to the online book “Neural Networks and Deep Learning” and to the vast resources on deepleaning.net. For a flavor of what CNNs can achieve in image classification, try this online demo. 
It is important that in NLeSc we have knowledge and experience with the latest research in data analytics, where deep learning is currently the trend. In the context of project Sherlock we look at some of the questions asked by the digital forensic investigators, for example: “Can we automatically and quickly find a (red) Ferrari in the images on a suspect’s disk?”, “Can we automatically and quickly find the persons (identity/ age/ gender) in the image data?”, etc. Tacking such questions, which are image classification tasks, with deep learning seems very promising. 
The main targets of the team will be:
1.	Learn  about deep learning and CNNs and their application in CV tasks
2.	Verify weather CNNs are suitable for CV tasks found in digital forensics
To achieve these goals, the team will work on some use cases:
•	Car model classification, [3]
•	Person gender classification, [4]
•	Person age classification, [4]
We will try to achieve the goals following number of steps (subject to team discussion):
1.	Learning about basics of Deep learning and CNNs
2.	Follow tutorial(s) on deep leaning for image classification using Caffe. Caffe is a deep learning framework developed by the Berkeley Vision and Learning Center.
3.	Use CNNs pre-trained on ImageNet and fine-tuned on car and person’s datasets (available at Caffe Model Zoo) to get classification results as reported in [3], [4]
4.	Learn about fine-tuning pertained CNNs for a specific CV task. 
5.	Learn about training CNNs. 
6.	Learn about using Keras with Caffe models (?)
7.	Designing CNNs architectures (?)
8.	Software in git and lessons learned report
References

[@Arel2010]: 	paper "I. Arel, D. C. Rose and T. P. Karnowski., 'Research frontier: Deep machine learning- a new frontier in artificial intelligence research', Computer Intalligence Magazine, pp. 13-18, 2010"
[2] 	Y. Bengio, "Learning deep archiechures for AI," Foundations and Trends Machine Learning, vol. 2, no. 1, pp. 1-127, 2009. 
[3] 	L. Yang, P. Luo, C. C. Loy and X. Tang, "A Large-Scale Car Dataset for Fine-Grained Categorization and Verification,," in Computer Vision and Pattern Recognition (CVPR), Boston, 2015. 
[4] 	G. Levi and T. Hassner, "Age and Gender Classification using Convolutional Neural Networks," in IEEE Workshop on Analysis and Modeling of Faces and Gestures (AMFG), at the IEEE Conf. on Computer Vision and Pattern Recognition (CVPR), Boston, 2015. 


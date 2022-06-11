# Wi-Pose-Dataset
## Introduction
To further promote the research on WiFi-based human pose estimation, we construct the new dataset Wi-Pose by a camera, a 5 GHz wireless router, and a WiFi receiving host. Wi-Pose consists of 166,600 packets of .mat format. These packets contain pose annotations and WiFi channel state information (CSI) of 12 different actions performed by 12 volunteers. The pose annotations are generated by [Alphapose](https://openaccess.thecvf.com/content_ICCV_2017/papers/Fang_RMPE_Regional_Multi-Person_ICCV_2017_paper.pdf) [1] based on the pose images captured by the camera. The annotation of each pose image includes the coordinates of 18 skeleton points including the nose, neck, right shoulder, right elbow, right wrist, left shoulder, left elbow, left wrist, right hip, right knee, right ankle, left hip, left knee, left ankle, right eye, left eye, right ear, and left ear. The 12 actions include wave, walk, throw, run, push, pull, jump, crouch, circle, sit down, stand up, and bend. 

To make Wi-Pose more challenging and more adaptable to real scenarios, we invited 12 volunteers of different heights and weights and asked them to repeat each action 10 times. Each volunteer has about 13,200 corresponding packets of .mat format. Each packet contains 3 variable includes 'csi_serial', 'jointsVector', and 'jointsMatrix'. The 'csi_serial' stores the CSI with the size of 5×30×3×3, where 5 represents the 5 CSI data corresponding to the 1 image, 30 represents the 30 sub-carries, and 3×3 represents the 3 WiFi transmitting antennas and receiving antennas. The 'jointsVector' stores the pose annotations with the format of (x, y, c, c), where (x, y) represents the coordinate of each skeleton point, and c represents the confidence of the coordinate. Moreover, the 'jointsMatrix' stores the extended pose annotation matrix generated according to the following formula:
![Dataset](https://github.com/NjtechCVLab/Wi-PoseDataset/blob/main/Matrix.png)
The matrix makes the relative displacement between each skeleton point the regular term to enhance the robustness of the training model. Because of personal privacy and portrait rights, the public Wi-Pose does not include pose images of volunteers. Fortunately, it won't affect Wi-Pose-based model training. For data division, 132,847 and 33,753 packets are utilized for training, and testing, respectively.

## Dataset Access

### Google Drive
Link: [https://drive.google.com/file/d/1WL6bJ-rSVdsclRt9RFc0l5hhtXYmfNg9/view?usp=sharing](https://drive.google.com/file/d/1WL6bJ-rSVdsclRt9RFc0l5hhtXYmfNg9/view?usp=sharing)

### Baidu Netdisk
Link: [https://pan.baidu.com/s/14TbkIRPQN1DktDir9N2Y3A](https://pan.baidu.com/s/14TbkIRPQN1DktDir9N2Y3A)  
Password: wqeq 

## Reference
[1] Fang H S, Xie S, Tai Y W, et al. Rmpe: Regional multi-person pose estimation[C]//Proceedings of the IEEE international conference on computer vision. 2017: 2334-2343.

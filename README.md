# SnT-ARG-PilotDetect

![Sample Image](https://github.com/dcazzato/SnT-Arg-PilotDetect/blob/master/sample_image.png)

Official page of the SnT-ARG-PilotDetect dataset.

The dataset has been introduced to assess the capabilities to identify the UAV pilots in realistic scenarios.

The dataset is composed by six training sequences and one test sequence.

The training sequences have been released as part of the dataset to guarantee the reproducibility of the code, representing controlled scenarios and, to ease labelling procedure, with one single person present at any time. They have been filmed by a consumer camera placed at heights ranging in the interval of [2-3.0] meters. Two male subjects are framed in total, and both persons act alternatively as pilot or non-pilot to avoid introducing any bias derived from the body dimension and appearance. In total, 2,959 frames of non-piloting behavior and 3,699 of piloting behavior have been recorded and labelled.

The test set represents instead a realistic and long sequence in an urban scenario with a DJI M600 drone recording from a stabilized DJI Zenmuse X5R camera, patrolling the area (remotely controlled by a human pilot). The UAV changes its orientation and height during the flight, in the height range of [2.5-10.0] meters. The background varies and it includes buildings, parked cars, a field and an alleyway, and more people can be present at the same time. Also the trajectory of each person is not constrained, implying that several re-appearance can occur, and that the bounding box could be partially overlapped. In the full scene, three people act without constraints in terms of appearance and simulating three type of behavior: "pilot", "non-pilot, "using mobile phone".

The data has been created using EfficientDet-D2 to extract the bounding boxes around each detected people, and manually labelled. If the person turns away or only a small part is visible we used the following convention: if these cases happen after having previously clearly get a class label, then the frames are stored. If this happens when the person enters the scene for the first time, we waited that the human performing labelling was able to clearly identify the class label before starting storing the frames. In the total test sequence, 11,476 labelled samples have been provided.

The released dataset consists of the images whit the regions containing the persons in the scene with a padding of 5 pixels in each dimension, and a command separated values (CSV) structure where each line contains the information regarding the frame name and the bounding box of each detected person and the label. Also the normalized (in 0-1 interval, with -1 for a missing joint) skeleton coordinates automatically extracted by OpenPose have been added. Bounding boxes without a detected skeleton or the case of less than 5 estimated joints have been removed from the dataset. The CSV presents the following structure: 

- Column 1: Frame name;
- Column 2-5: Bounding box of the person;
- Column 6-55: Normalized detected joints;
- Column 56: Class label (0 for non-pilot, 1 for pilot, 2 for person using a mobile phone).

# License
All distributed software are subject to the GNU General Public License, version 3 license.


# Citation

Please cite this paper in your publications if it helps your research:

```
@inproceedings{cazzato2020preliminary,
  title={A Preliminary Study on the Automatic Visual based Identification of UAV Pilots from Counter UAVs.},
  author={Cazzato, Dario and Cimarelli, Claudio and Voos, Holger},
  booktitle={VISIGRAPP (5: VISAPP)},
  pages={582--589},
  year={2020}
}
```

# Contributors

List of people that have contributed:

+ Dario Cazzato (dcazzato85@gmail.com): Main Author, Maintainaince and Documentation.
	

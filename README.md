# BiCap Dataset

BiCap is a novel bimodal dataset designed to advance the development of learning-from-demonstration (LfD) algorithms for dual-arm robotic manipulation. It comprises 4,026 demonstrations collected from fifteen participants performing pouring, opening, and passing tasks with household objects. Each demonstration includes an RGB video recording, upper-limb kinematics, and a symbolic task plan annotated using a bio-inspired action context-free grammar (BACFG). BiCap overcomes fundamental limitations of existing LfD datasets, which often lack formally structured symbolic annotations and exhaustive capture of dual-arm manipulation skills, by coupling fine-grained symbolic representations with trajectory data. It provides a rigorous foundation for developing and evaluating algorithms capable of learning, planning, and generalising complex dual-arm manipulation behaviours.

## Brief Description

A unique dataset collected using an RGB camera and an advanced motion capture system. The paper presenting BiCap is in the [International Journal of Robotics Research (IJRR)](https://journals.sagepub.com/doi/abs/10.1177/02783649241290836). Nevertheless, several slight improvements have been made to the dataset since its publication in IJRR. This website provides the latest information on BiCap.

```bibtex
@article{carmona_bicap_2025,
	author = {Carmona, David and Yu, Haoyong},
	title = {BiCap: A novel bi-modal dataset of daily living dual-arm manipulation actions},
	journal = {The International Journal of Robotics Research},
	volume = {44},
	number = {6},
	year = {2025},
	pages = {891--907},
	issn = {0278-3649},
	url = {https://doi.org/10.1177/02783649241290836},
	doi = {10.1177/02783649241290836}
}
```

## Changelog

- 11-2025:
  * Create the website and the GitHub for BiCap.
  * Make BiCap available on Hugging Face to simplify the downloading.
  * Remove BiCap from Terabox and re-direct to Hugging Face.
  * Add the mp4 format of the RGB videos.
  * Remove the .svo videos as they are considerably large and require the ZED Explorer application to be opened.
  
- 05-2025:
  * IJRR publishes the issue containing the paper.
    
- 11-2024:
  * Publish the RGB videos, symbolic task plans, upper-limb kinematics, and online IJRR paper. The dataset is in Terabox.

## Getting Started

### Download

**BiCap can be downloaded from [Hugging Face](https://huggingface.co/datasets/davidcarmona/BiCap)**.

### Software

* The RGB videos are mp4 files. They can be visualised using any player that supports mp4, such as VLC Media Player.
* The motion capture data is inside csv files. Excel or LibreOffice Calc can be used to open the files.
* The symbolic task plans are inside xml files. Any text editor should be able to read the xml file.

### Folder Hierarchy

    BiCap
    ├── Motion Capture                          # Folder containing all the subjects' motion data.
	│   ├── BBM01                               # Data of the subject number BBM01.
	│   │    ├── pouring_bowl_cracker_01.csv    # The motion data for the first trial of the subject pouring box of crackers into a bowl.
    │   │    ├── pouring_bowl_cracker_02.csv    # The motion data for the second trial of the subject pouring box of crackers into a bowl.
    │   │    ├── passing_masterchef_04.csv      # The motion data for the fourth trial of the subject passing a masterchef can.
    │   │    └── ...
	│   └── ...
    ├── Videos                                  # Folder containing all the subjects' videos taken with the RGB camera and their corresponding task plans. 
    │   ├── BBM01                               # Data of the subject number BBM01.
	│   │   ├── Expt 1 (Pouring)                # Data of the first experiment (the pouring task).
    │   │   │   ├── Bowl and Cracker box        # RGB Video and task plan data for pouring a box of crackers into a bowl.
    │   │   │   │   ├── Trial 1.mp4             # RGB Video data from the camera for the first trial.
    │   │   │   │   ├── Trial 1.xml             # Task plan for the first trial.
    │   │   │   │   ├── Trial 2.mp4             # RGB Video data from the camera for the second trial.
    │   │   │   │   ├── Trial 2.xml             # Task plan for the second trial.
    │   │   │   │   └── ...
    │   │   │   └── ... 
    │   │   └── ...    
    │   └── ...
	├── participants.xlsx                       # The subjects' data.
    ├── readme.pdf
    └── readme.md

### Camera

The RGB videos were recorded with a [Stereolabs ZED2 camera](https://www.stereolabs.com/en-sg/blog/introducing-zed-2). A human expert annotated the symbolic task plans using the RGB videos and the BACFG.

### Motion Capture

The participants' motion was captured with four [Vicon Vantage 16](https://help.vicon.com/space/Vantage/15041618/V16+camera+specifications) and four [Vicon MX T160](https://help.vicon.com/download/attachments/11108354/T-Series_GoFurther_Rev1.3_2010Aug.pdf) cameras positioned across the workspace.
	
## Miscellaneous

### Subjects Identifiers

The subjects' identifiers inside the XML files differ from the folders' names (e.g., BBM01, BBM02, or BBM03). The mapping is:

* BBM01: 010
* BBM02: 012
* BBM03: 013
* BBM04: 014
* BBM05: 015
* BBM06: 016
* BBM07: 017
* BBM08: 018
* BBM09: 019
* BBM10: 020
* BBM11: 021
* BBM12: 022
* BBM13: 023
* BBM14: 024
* BBM15: 025

### Joint Angles Names

The joint angles present in the csv files are:

* LElbowAngles: Left elbow angles
* LShoulderAngles: Left shoulder angles
* LThoraxAngles: The forward tilt, the right tilt, and right rotation angles of the thorax
* LWristAngles: Left wrist angles
* RElbowAngles: Right elbow angles
* RShoulderAngles: Right shoulder angles
* RThoraxAngles: The forward tilt, the left tilt, and left rotation angles of the thorax
* RWristAngles: Right wrist angles

### Motion Capture Markers Positions

The markers' positions in the csv are:

* C7: Seventh cervical vertebra
* T10: Tenth toracic vertebra
* CLAV: Clavicle
* STRN: Sternum
* RBAK: Right back
* LSHO: Left shoulder
* LUPA: Left upper arm
* LELB: Left elbow
* LFRM: Left forearm
* LWRA: Left wrist marker A
* LWRB: Left wirst marker B
* LFIN: Left finger
* RSHO: Right shoulder
* RUPA: Right upper arm
* RELB: Right elbow
* RFRM: Right forearm
* RWRA: Right wrist marker A
* RWRB: Right wrist marker B
* RFIN: Right finger
* LASI: Left anterior superior iliac
* RASI: Right anterior superior iliac
* LPSI: Left posterior iliac
* RPSI: Right posterior iliac

### Unavailable Data

The following data is unavailable in the dataset:

* The motion data for subjects BBM11 and BBM13 are absent since the VICON system malfunctioned on the day of the experiments
* The motion data of the first trial for passing the MasterChef executed by subject BBM05 is unavailable
* The motion data for passing the power drill achieved by subject BBM12 is absent
* The video data for the passing the wood block by subject BBM01 is available for nine trials
* The video data for the pouring of the mug into the pitcher by subject BBM07 is absent
* The video data for the passing of the woodblock by subject BBM08 is available for nine trials
* The video data for the passing of the driller by subject BBM12 is absent
* The video data for the passing of the driller by subject BBM15 is available for nine trials
* The video data for the passing of the wood block by subject BBM15 is available for nine trials
  
### Contact

David Carmona: [dcmoreno@nus.edu.sg](dcmoreno@nus.edu.sg)

## License

This dataset is made available under the Creative Commons Attribution 4.0 International License - see the LICENSE.md file for details

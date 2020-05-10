
## PhD source code, data, models and results

This repository contains all the source code, links to data, trained models, results, and other
supplementary material that were developed as part of the work for the PhD thesis: 
		
		"Trajectory Space Factorisation for Vision-Based Automated Sign Language
		Recognition", Mark Borg, University of Malta, March 2020.

The **supplementary report** accompanying the above thesis is available here: [Supplementary report](https://drive.google.com/open?id=1NUgVn98tGKCQokzE3jDwo4wKFMBiSrhO).

--------------

**A Note on the Source Code and the pipeline approach**:

The source code developed as part of the work for this thesis is written in various languages. 

C++ is used for most of the body-part tracking algorithms, mainly skin detection, motion detection (frame differencing), KLT feature tracking, and for the MHT algorithm. C++ versions of the Boost and OpenCV libraries are used. Development was done using Windows Visual Studio. Much of the code is standard C++, but there might be a few Windows-specific parts, especially code sections dealing with the GUI (keyboard input and output). C++ is used here mainly because of its versatility, as well as execution speed. Project solutions are included with the code.

For the investigative and experimental parts, R and MATLAB are used. R is used for manipulating the lexicon and annotation files, as well as for some of the statistical analysis parts. R code is available in two formats: R files and R markdown files. The latter allows for combining both code and text, thus ideal for recording both the source code, description, as well as the results of an experiment. R markdown files can then be converted (weaved) to PDF, to serve as a record of an experiment. We include R markdown files and their corresponding PDFs for several of the experiments.

MATLAB is used mostly for the trajectory space factorisation code and visualisation of KLT trajectories, reconstructed trajectories, as well as the DCT coefficient matrices. 

Finally, Python was also used towards the end of the work on this thesis. Python is mainly used for the deep learning stuff, with Keras/TensorFlow as the deep learning framework of choice. Python is also great for combining the various components (written in other languages) into a "pipeline".

A pipeline approach is adopted in much of the work done here, with light to no coupling between the components. In other words, each component is treated independently of the others, and the input and output data streams to each component are saved to disk. These are saved as either CSV files, Matlab data (matrix) files, or Python numpy arrays. Such a diverse set of formats is used to allow for flexibility during the investigations, and also since all the languages used here (R, MATLAB, and Python) provide libraries or in-built functionality to support reading/writing from these data file formats. Finally, Python can serve as the "glue" to combine all the components together into an actual pipeline.


--------------

Material related to **Sign Language detection**:

Source code for signing detection is available at: [github.com/mark-borg/sign-language-detection.git](https://github.com/mark-borg/sign-language-detection.git), 
while the dataset ``Signing in the Wild'' can be found here: [github.com/mark-borg/Signing-in-the-Wild-dataset.git](https://github.com/mark-borg/Signing-in-the-Wild-dataset.git).


--------------

Material related to the **Body-part tracking pipeline**:

Skin detection source code and results can be found here: [skin detection](https://drive.google.com/open?id=1PzurIahlbbQuw5zsjTNamhMsSd_yzECf).

Frame differencing source code and results can be found here: [frame differencing](https://drive.google.com/open?id=1gF7gN3V-5aJs6wJlvFf5BFaNDqale3yk).

Face detection source code and results can be found here: [Viola-Jones face detector](https://drive.google.com/open?id=13dlfWHnUAw1L3AQCERVvyy02IRoyWfbw), [MTCNN face detector](https://drive.google.com/open?id=1rjb7mdpuZL9GAltc1t4_e-Sucw5P6QeD), and [face tracking and other misc experiments](https://drive.google.com/open?id=1lzrXEhIM-3AcWgv5R5woV13kwfQcJ9OQ).

KLT feature tracking source code and results can be found here: [KLT feature tracking](https://drive.google.com/open?id=1vN-OG0KZ1rh9f8FX_ftiPyAD_JAYYzWX).

Source code and experimental results in KLT feature grouping for long-term hand tracking can be found here: [KLT feature grouping and hand tracking](https://drive.google.com/open?id=1lv1Emyia0l8JyHD9mQqpO0r9c6QwMNxu). This includes experiments in KLT feature analysis. And the results of the non-KLT hand tracking experiments are available here: [non-KLT hand tracking experiments](https://drive.google.com/open?id=1C7-HgxG3kH3oevbj3frFhSNHSU240x69).

Code and experimental results of using OpenPose-based features instead of the KLT features can be found here: [OpenPose based hand features](https://drive.google.com/open?id=1TF3lOk46sn8S0e170cBY1Nk7MI6FBoYq).

And groundtruth related to body-part tracking is available [here](https://drive.google.com/open?id=1nlSk0A8erhJM48wXp48fjEyDB-BE1Lzf). A rudimentary tool was developed for doing basic groundtruthing. This is included in the same folder. Compared to other tools, it has serious limitations; but it sufficed for the job at hand. 


--------------

Material related to **Multiple Hypothesis Tracking (MHT) and hand motion constraints**:

The source code for the MHT and hand motion constraints, as well as a sample of results, can be found here: [MHT tracking](https://drive.google.com/open?id=1-FeQk-mjvWiWfjrunPX5HcClN5G7s70T). Also included are the R notebooks used for the experiments and hyperparameter tuning.


--------------

Material related to **Trajectory Space Factorisation**:

Source code and experimental results for Trajectory Space Factorisation can be found here: [Trajectory Space Factorisation](https://drive.google.com/open?id=1RnF44hpJO1yq1oUesLkqcp7h1LN9IPuf). Since we adopted a pipeline-based approach, the computed results of the sliding window trajectory space factorisation are saved (generally, the trajectory matrices W and coefficient matrices A) and used as input to later components of the pipeline, including sign recognition. These are MATLAB matrices saved to disk with the filename format having a pattern <name_of_matrix>[r|l].NNN_to_MMM.mat, where 'r' or 'l' indicates the hand of the signer, and NNN and MMM are the starting and ending video frames of the sliding window. 

Results of applying Structure from Motion (SfM) on the synthetic signing dataset, and the dataset itself, can be found at: [Synthetic Signing dataset](https://drive.google.com/open?id=1U0RwNAKTSnOI2ClrXZQz6ZuBXtJ773_B).

Experimental results in using the factorisation method for motion segmentation can be found here: [factorisation-based motion segmentation](https://drive.google.com/open?id=1CJodjlLMyJckCPcLojXoPHaay-0BUByR).



--------------

Material related to **Sign Recognition**:

The lexicon and associated annotation files used in the supervised training of both the HMM-based sign recognition system and the RNN-based system can be found here: [lexicon and associated annotation files](https://drive.google.com/open?id=1DqPHf28c7MBvObsBUP1GzI7YLiNmYjnI). The ELAN annotation tool is needed for the EAF files; this is available here: [ELAN tool](https://archive.mpi.nl/tla/elan).



--------------




The multimodal intention recognition task aims to identify the underlying intention (e.g., information, emotion, promotion) behind multimodal social media content (e.g., text-image pairs). Identifying the intention behind multimodal social media content helps to gain a deeper understanding of user behavior and preferences and accurately grasp the motivations behind user posts, thereby deepening our understanding of user behavior.

This response is the code base for ACM MM2024 "MIKO: Multimodal Intention Knowledge Distillation from Large Language Models for Social-Media Commonsense Discovery".

**1. Data**
   
For the challenge, we collected a mutlimodal social intention dataset containing 979 Twitter posts anotated with 7868 intentions. Specifically, the dataset is partitioned into 881 Twitter posts for training and 98 Twitter posts for testing. The intentions include nine different types of intentions extracted from ATOMIC and one open-domain intention. Specifically, nine ATOMIC-extracted intentions include ''xNeed'' (user's need), ''xIntent'' (user's intention), ''xAttr'' (user's attribute), ''xEffect'' (effect of user's action), ''xReact'' (user's reaction), ''xWant'' (user's desire), ''oEffect'' (impact on others), ''oReact'' (others' reaction), and ''oWant'' (others' desire), where ''x'' represents the thoughts and behaviors of the user after posting, and ''o'' denotes the impact of the post on others. The open intention, termed ''Open'', describes the motive and purpose behind a user's decision to publish a specific post content. Each intention is annotated with Label Studio where five annotators evaluate generated candidates' intentions alongside raw text-image pairs.

**2. Dataset Description**

The dataset comprises two files and a floder: **train.json**, **test.json** and **image**. The test.json file does not contain intentions. Participants are required to generate intentions for the test instances based on the provided text and image data. Each instance in the train.txt and test.json is represented as a dictionary, delineating the attributes of an individual tweet.. The dictionary includes the following fields, each with its corresponding meanings:
| Field            | Meaning                                                                                                                  |
|------------------|--------------------------------------------------------------------------------------------------------------------------|
| intention_labels | This field contains a list of labels. if `intention_labels[3]` equals 1, it signifies that `Intention 3` is the ground truth for the intention of this tweet. |
| image            | This field denotes the file of the tweet image. Correspondingly, the image file can be located in the `image` folder based on this provided name. |
| text             | This field encompasses the textual content of the tweet.                                                                 |
| intentions       | A dictionary comprising entries from `Intention 1` to `Intention 10`.                                                     |



**3. Metric**

The evaluation metric is the average BERT score(reported as percentages) for the 10 different aspects of the generated intentions.

Our benchmark has been published in the corresponding competition of IEEE BigDATA2024: Multimodal Intention Recognition in Social Media. Everyone is welcome to sign up for the competition.(https://www3.cs.stonybrook.edu/~ieeebigdata2024/BigDataCupChallenges.html).

**BibTeX formatted citation**
```
@inproceedings{lu2024miko,
  title={{MIKO}: Multimodal Intention Knowledge Distillation from Large Language Models for Social-Media Commonsense Discovery},
  author={Feihong Lu and Weiqi Wang and Yangyifei Luo and Ziqin Zhu and Qingyun Sun and Baixuan Xu and Haochen Shi and Shiqi Gao and Qian Li and Yangqiu Song and Jianxin Li},
  booktitle={ACM Multimedia 2024},
  year={2024},
  url={https://openreview.net/forum?id=wE3WS15pM2}
}
```


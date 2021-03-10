![overview](./imgs/poison_overview.png)

[P1] [Data Poisoning Attacks Against
Federated Learning Systems.](./Poison/P1_Data_Poisoning_Attacks_Against_Federated_Learning_Systems.pdf)

This paper studies targeted data poisoning attacks against FL systems in which a malicious subset of the participants aim to poison the
global model by sending model updates derived from mislabeled data.

[P2] [Local Model Poisoning Attacks to Byzantine-Robust Federated Learning.](./Poison/P2_Local_Model_Poisoning_Attacks_to_Byzantine_Robust_Federated_Learning.pdf)Usenix Security 20


It performs the first systematic study on round-based local model poisoning attacks to federated learning under Byzantine-Robust FL. This paper formulates their attacks as optimization problems and apply our attacks to four recent Byzantine-robust federated learning methods.

```python
what = "model poisoning"
why = " first to consider about model poisoning under defenses"
goal = "untargeted model poisoning"
how = "directed deviation, to deviate a global model parameter most towards the inverse of the direction under aggregation defenses"
```
<img src="./imgs/P2-1.png" width = "50%",  align="absmiddle"/>
where s = 1 or -1


[P3] [Learning to Detect Malicious Clients for Robust Federated Learning.](./Poison/P3_Learning_to_Detect_Malicious_Clients_for_Robust_Federated_Learning.pdf)

As the central server in the system cannot govern the behaviors of the clients, a rogue client may initiate an attack by sending malicious model updates to the server, so as to degrade the learning performance or enforce targeted model poisoning attacks (a.k.a. backdoor attacks). Therefore, timely detecting these malicious model updates and the underlying attackers becomes critically important. This work proposes a new framework for robust federated learning where the central server learns to detect and remove the malicious model updates using a powerful detection model, leading to targeted defense. 


[P4] [Targeted Backdoor Attacks on Deep Learning Systems Using Data Poisoning.](./Poison/P4_Targeted_Backdoor_Attacks_on_Deep_Learning_Systems_Using_Data_Poisoning.pdf)

It focus on backdoor data poisoning. In this paper, their studied poisoning strategies can apply under a very weak threat model: (1) the adversary has no knowledge of the model and the training set used by the victim system; (2) the attacker is allowed to inject only a small amount of poisoning samples; (3) the backdoor key is hard to notice even by human beings to achieve stealthiness. 

[P5] [Data Poisoning Attacks on Federated Machine
Learning.](./Poison/P5_Data_Poisoning_Attacks_on_Federated_Machine_Learning.pdf)

This paper focus on attacking a federated multi-task learning framework. They formulate the problem of computing optimal poisoning attacks on federated multi-task learning as a bilevel program that is adaptive to arbitrary choice of target nodes and source attacking nodes. Then it propose a systems-aware optimization method, ATTack, which is efficiency to derive the implicit gradients for poisoned data, and further compute optimal attack strategies in the federated machine learning. 

[P6] [Towards Poisoning of Deep Learning Algorithms with
Back-gradient Optimization.](./Poison/P6_Towards_Poisoning_of_Deep_Learning_Algorithms_with_Back-gradient_Optimization.pdf)

To date, data poisoning attacks have been devised only against a limited class of binary learning algorithms, due to the inherent complexity of the gradient-based procedure used to optimize the poisoning points (a.k.a. adversarial training examples). This work extend the definition of poisoning attacks to multiclass problems and propose a poisoning algorithm based on the idea of back-gradient optimization, i.e., to compute the gradient of interest through automatic differentiation, while also reversing the learning procedure to drastically reduce the attack complexity.

[P7] [A Flexible Poisoning Attack Against Machine
Learning.](./Poison/P7_A_Flexible_Poisoning_Attack_Against_Machine_Learning.pdf)

This article proposes an attack method in which the attacker makes the parameter value of the learning model close to his expected value and at the same time makes the model output wrong predictions for certain test samples. It considers the effect of attack and the concealment of attack. 


[P8] [How To Backdoor Federated Learning](./Poison/P8_How_To_Backdoor_Federated_Learning.pdf)

<img src="./imgs/P8-1.png" width = "70%" />
<img src="./imgs/P8-2.png" width = "50%" />


The paper proposes an input matrix manipulation to conduct targeted local model poisoning backdoor in federated learning. When the global is about to converge, the attacker could inject a malicious model based on the difference of the clean global one. And it proved to be efficient even when the attacker does not know the global learning rate. 

[P14] [Robust Federated Training via Collaborative Machine Teaching using Trusted Instances](./Poison/P14_Robust_Federated_Training_via_Collaborative_Machine_Teaching_using_Trusted_Instances.pdf)
AAAI

This paper considers partial corrupted local data while the rest fraction is trusted in FL. The clients are organized to jointly tune the corrupted training data set, such that the model learnt with the tuned training set by the server predicts consistent targets as the trusted instances. More specifically, it adopt two types of training data tuning operations: crafting the training instances and subset-selecting the training set.


[P15]
[dba distributed backdoor attacks against federated learning](./Poison/P15_dba_distributed_backdoor_attacks_against_federated_learning.pdf)
ICLR

```python
why, what, goal = "[P8]"
how = "use distributed trigger rather than one trigger to achieve better occultation"
```
<img src = "./imgs/P15.png" width = “80%“ />

Instead of applying the same trigger in the attackers' datasets in [P8], this paper studies the distributed triggers (multiple triggers for subtasks) in FL, which can be more insidious and hard to detect. Additionally, the impact of triggers factors (eg. size, gap, location) are studied.

[P16]
[Analyzing_Federated_Learning_through_an_Adversarial_Lens](./Poison/P16_Analyzing_Federated_Learning_through_an_Adversarial_Lens.pdf)
ICML

1. FedAvg, boost the malicious agent’s update to overcome the effects of other agents’ updates by K times with E=5;
2. propose an alternating minimization strategy, which alternately optimizes for the stealth objectives and the adversarial objective; 
3. using parameter estimation for the benign agents’ updates to improve on attack success by averaging methods assuming the cumulative updates were the same at each step for benigns;  
4. use a suite of interpretability techniques to generate visual explanations for both benign and malicious models to demonstrate indistinguishability.

```python
what = "model poisoning by a single, non-colluding malicious agent"
why = " first to consider about stealth in model poisoning"
goal = "targeted, effective, stealth under defenses"
how = "effective = boosting of updates, stealth = alternating minimization strategy"
conclusion = "model poisoning attacks are much more effective than data poisoning in FL"
```

[P17]

[P18]
[attack-of-the-tails-yes-you-really-can-backdoor-federated-learning-Paper](./Poison/P18-attack-of-the-tails-yes-you-really-can-backdoor-federated-learning-Paper.pdf)
NIPS

<img src = "./imgs/P18-1.png", width = 80% \>


```python
what = "edge-case backdoor: misclassify of easy inputs that are however unlikely to be part of the training, or test data, i.e., they live on the tail of the input distribution"
why = "hard to to filter under diverse data settings"
goal = "targeted under defense"
how = """
black-box: direct data poison;
PGD: periodically project their model on a small ball, centered around the global model of the previous round;
PGD+boosting[P16];
"""
```

This paper concludes that FL systems can NOT be tailored to be robust against backdoors. And it provides edge-case backdoors which forces a model to misclassify on seemingly easy inputs that are however unlikely to be part of the training, or test data, i.e., they live on the tail of the input distribution. Specifically, it is 3 attacks: black-box, PGD and PGD+boosting[P16]


[P19]
[Comprehensive-Privacy-Analysis-of-Deep-Learning-Passive-and-Active-White-box-Inference-Attacks-against-Centralized-and-Federated-Learning](./Poison/P19_Comprehensive-Privacy-Analysis-of-Deep-Learning-Passive-and-Active-White-box-Inference-Attacks-against-Centralized-and-Federated-Learning.pdf)
S&P

This paper proposes a white-box membership inference attacks, one observation from this paper is that latter layer leaks more information than the former, however the leakage of activation layer is similar to output layer. So the results of white-box and black-box using activation information are similar. It design deep learning attack models using the gradient vector over all parameters on the target data point as the main feature for the attack. The architecture (simple CNN + FCN) processes extracted (gradient) features from different layers of the target model separately, and combines their information to compute the membership probability of a target data point. Further, it designs an active attack in the federated learning setting, the adversary can actively push SGD to leak even more information about the participants’ data. 


```python
what = "passive and active, white-box, inference, membership, central and FL"
goal = "white-box membership inference attacks"
why = "the leakage of activation layer is similar to output layer"
how = "train a binary classification model using gradients, hidden layers, output, loss"
```
<img src = "./imgs/P19-1.png", width = 50%><img src = "./imgs/P19-2.png", width = 50%>


[P20] [FLTrust: Byzantine-robust Federated Learning via Trust Bootstrapping
](./Poison/P20-FLTrust-Byzantine-robust-Federated-Learning-via-Trust-Bootstrapping.pdf)
NDSS

Rather than performing anomaly detection in local model, this paper build bootstraping trust by compute the cosine similarity beteween server updates and clients' updates, which is named as trust score. The weighted aggregation is based on trust scores and updates normalized by the magnitude of server updates.

[P21] [Manipulating the Byzantine: Optimizing Model Poisoning Attacks and Defenses for Federated Learning
](./Poison/P21-Manipulating-the-Byzantine-Optimizing-Model-Poisoning-Attacks-and-Defenses-for-Federated-Learning.pdf)
NDSS

This paper presents a generic framework for model poisoning attacks and a novel defense   called divide-and-conquer (DnC) on FL. The key idea of its generic poisoning is that they introduce perturbation vectors and optimize the scaling factor $\gamma$ in both AGR-tailored and AGR-agnostic manners. DnC applies a singular value decomposition (SVD) based spectral methods to detect and remove outliers.

```python
what = "model poisoning + defense"
goal = "untargeted under defense"
why = "defenses exist"
how = """
poisoning: introduce perturbation vectors and optimize the scaling factor 
defense: singular value decomposition based spectral methods
"""
```
<img src = "./imgs/P21-1.png", width = 100%>

[P22] [Threats to Federated Learning: A Survey](./Poison/P22_Threats-to-Federated-Learning-A-Survey.pdf)

It summarizes the existing threats to FL

[P23] [Exploiting Unintended Feature Leakage in Collaborative Learning](./poison/P23-Exploiting-Unintended-Feature-Leakage-in-Collaborative-Learning.pdf)


```mermaid
graph LR
Z(Adversary)-->Z1(Attacks)
Z-->Z2(Defenses)
Z1-->A1(Training)
Z1-->A2(Inferrence)
A1-->B1(Data Poisoning)
B1-->M1(Dirty label)
B1-->M2(Clean label)
A1-->B2(Local Model Poisoning)
M1-->C1(Federated)
M1-->C2(Centralized)
B2-->D1(2)
B2-->D3(generic model poison-21)
B2-->D2(backdoor-8)
B2-->D4(distributed backddor-15)
B2-->D6(edge-case backdoor-18)
B2-->D5(alternative minimization and parameter estimation-16)
C1-->G1(Label flipping-1)
C1-->G2(3)
C1-->G3(Multi-task-5)
C1-->G4(Partial corrupted data-14)
C1-->G5(Edge-case-18)
C2-->H1(3)
C2-->H2(4)
C2-->H3(Multi-class back gradient optimization-6)
C2-->H4(7)
A2-->B3(Membership)
B3-->I1(white-box-19)
A2-->B4(Reconstructing)
A2-->B5(Misclassification)
Z2-->B11(Training)
Z2-->B12(Inference)
B11-->C11(Model poisoning)
B11-->C12(Data poisoning)
C11-->D11(20)
C12-->D12(Heterogenous data-17)
```

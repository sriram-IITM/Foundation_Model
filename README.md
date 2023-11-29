## Foundational Models for Fault Diagnosis of Electrical Motors
We have developed a foundational model for the first time in the field of electrical motor fault diagnosis.  The developed model can able to detect and diagnose faults within and across machines. This work is accepted at the IEEE conference (PESGRE 2023), and the preprint is available in arXiv [[1]](https://arxiv.org/abs/2307.16891)

## Abstract
A majority of recent advancements related to the
fault diagnosis of electrical motors are based on the assumption
that training and testing data are drawn from the same distribution. However, the data distribution can vary across different
operating conditions during real-world operating scenarios of
electrical motors. Consequently, this assumption limits the practical implementation of existing studies for fault diagnosis, as
they rely on fully labeled training data spanning all operating
conditions and assume a consistent distribution. This is because
obtaining a large number of labeled samples for several machines
across different fault cases and operating scenarios may be
unfeasible. In order to overcome the aforementioned limitations,
this work proposes a framework to develop a foundational model
for fault diagnosis of electrical motors. It involves building a
neural network-based backbone to learn high-level features using
self-supervised learning and then fine-tuning the backbone to
achieve specific objectives. The primary advantage of such an
approach is that the backbone can be fine-tuned to achieve a wide
variety of target tasks using very less amount of training data
as compared to traditional supervised learning methodologies.
The empirical evaluation demonstrates the effectiveness of the
proposed approach by obtaining more than 90% classification
accuracy by fine-tuning the backbone not only across different
types of fault scenarios or operating conditions, but also across
different machines. This illustrates the promising potential of
the proposed approach for cross-machine fault diagnosis tasks
in real-world applications.

## Dataset
The data set used in this work to construct the backbone model is the [Korea Advanced Institute of Science and Technology (KAIST) dataset](https://www.sciencedirect.com/science/article/pii/S2352340923001671) . The data comprises measurements under three loading conditions: 0 Nm, 2 Nm and 4 Nm. The sampling frequency for vibration, temperature, and driving current data was set at 25.6 kHz. This dataset contains 120 seconds of vibration data in normal states and 60 seconds in faulty states. The second part of the dataset focuses on vibration and current data acquired from the bearing, faults at different locations such as inner-race, outer-race, and ball. These data were collected under continuously varying speed conditions by modifying the motor speed between 680 and 2460 RPM. In this work, we specifically consider the vibration data for bearing faults, shaft misalignment faults, rotor unbalance faults at a constant speed, and bearing faults at varying speeds. The backbone model is trained by combining data from normal, inner race, outer race, shaft misalignment, rotor unbalance faults at constant speed, and normal, inner race, and outer race faults at variable speed conditions. 

## Flowchart for the proposed model
<p align="center">
<img src="https://i.imgur.com/01Re1p3.jpg" width=70% height=70%>
</p>
Proposed framework for developing foundational models for fault diagnosis of electrical motors.

## Contributions
This work, for the first time, presents a framework for
developing foundational models for fault diagnosis of electrical motors. This problem is approached as a two-step
process: 
1) Developing a backbone model to learn high-level features via self-supervised learning.
2) Fine-tuning approach to capture the finer details using a limited amount of labeled data.

The foundational model is evaluated based on the following aspects: <br>
  (a) Expressivity - the capacity to acquire and assimilate real-world data efficiently; <br>
  (b) Scalability - to manage large volumes of high-dimensional data effectively; <br>
  (c) Generalizability - the ability to work in varying environmental conditions. <br>
The experimental evaluation reveals that the proposed model demonstrates remarkable performance in diagnosing electrical motor faults by achieving the above
attributes of the foundational model. Such a study based on
foundational models has not been presented yet in the literature
related to fault diagnosis of electrical motors and is a novel
contribution of this work

## Proposed Foundation Model 
<p align="center">
<img src="https://i.imgur.com/hfy27u1.png" width=60% height=60%>
</p>

Fig. Architecture details of the proposed foundational model framework. First, the backbone model is trained to learn the representation of base machine data. Next, the learned features are transferred to the downstream task fault diagnosis network, which can be fine-tuned with less labeled samples to diagnose multiple target tasks within and across the machine.


## Target Tasks  
<p align="center">
<img src="https://i.imgur.com/S76ef1H.png" width=100% height=100%>
</p>

## Results
<p align="center">
<img src="https://i.imgur.com/Z6HqUzc.png" width=100% height=100%>
</p>


## Conclusions
This work introduces a novel foundational model-based
approach for fault diagnosis of electrical motors. It helps to
overcome the limitations of different data distributions across
working conditions and machines. In contrast to the existing
fault diagnosis approaches, the proposed framework involves
the development of a CNN-based backbone model that extracts higher-level features from the training dataset. The backbone
is then fine-tuned to achieve specific objectives based on
target tasks designed to perform diagnosis of different fault
types and severity levels across multiple speeds and loading
conditions. The proposed approach is evaluated based on three
key attributes, namely, expressivity, scalability, and generalizability, which are essential for the development of a robust
foundational model. The empirical evaluation reveals that a
good classification performance is obtained by fine-tuning the
backbone with much lesser labeled samples as compared to
supervised learning approaches. This approach gives excellent
results, even when the fine-tuning step is executed for target
tasks on another machine, thereby enhancing its scalability.
The proposed model is evaluated in multiple target tasks
by adding white Gaussian noise to the data. The results
demonstrate the remarkable generalization and scalability of
the model to handle different operating conditions effectively.
Overall, the proposed foundational model-based approach
offers a promising electrical motor fault diagnosis solution,
accommodating variations in data distributions and achieving
robust performance even with limited labeled samples. The
scalability and generalization capabilities of the proposed
model make it a valuable tool for real-world applications in
fault diagnosis for electrical motors. The future extension of
this work shall involve extensive testing across more target
tasks and incorporating physics information within the foundational models.


## References 
[1] Anbalagan, S., Agarwal, D., Natarajan, B. and Srinivasan, B., 2023. Foundational Models for Fault Diagnosis of Electrical Motors. arXiv preprint arXiv:2307.16891.


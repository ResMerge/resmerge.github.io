一、ResMerge思路梳理

pre-train robot polices 如何continual adaptation

Problem formulation：
Continual fine-tuning robot polices
每个任务Tk以及对应数据集Dk 接续到来，总共需要在robot policy上连续fine tune 5-10个任务

Challenges of continua Finetuning Generalist Robot Policies：
1.不泛化 （il-based pecft方法）
2.遗忘old tasks （传统方法）


baselines：
1、Task-FT：每个任务Tk with 数据集Dk，就用Dk来全参数fine-tune原来的策略
2、Co-FT：用Dk和原有数据Dinit混合起来全参数fine-tune原来的策略
3、Freeze-Task-FT：freeze住语言的backbone，用Dk来fine-tune策略的vision encoder、action head
4、LoRA-Task-FT：类似task-ft，但是用lora
5、LoRA-Co-FT：类似co-ft，但是用lora
6、DMPEL：

Ours：
ResMerge：用任务Tk学习Res_k，原策略frozen。任务Tk+1看已有策略是否能泛化，不能就学新的，然后看能否合并，能合并就合并为一个，不能就放到专家池作为扩展专家+1

出现的泛化现象：
说明两个model都学到了一些对新任务泛化的能力，但不够强，merge之后两个模型的泛化能力就被激发了
relate：on the other hand, model merging explicitly tries to elicit pretrained knowledge and combine it with finetuning knowledge in parameter space; （Sergey 2026）

我们跟Sergey不同的地方是：一个是持续学习setting，一个是ft单任务
他们的settings是训完了之后，评测：
（1）微调的single task
（2）该task的泛化task （更广泛范围内的该task）
（3）在pre-trained 任务上的generalist能力没有缺失

我们：
（1）每次微调的single task
（2）该task的泛化task （更广泛范围内的该task） — 把trails开大测试
（3）在old task上的能力没有缺失


Advs：
ResMerge Learn New Skills Robustly（成功率高） and Generalize More Broadly （新任务有泛化能力）
model merging performs better with seq fine-tuning、co-finetuning

-------

二、ResMerge网站思路

Pre-train robot polices 如何continual adaptation

1.先假设一个场景，能良好的把别人代入到我们的problem formulation。
比如有一个generalist robot policy和robot，在一个家庭/工厂场景里，需要连续学会5-10个任务

2.然后再引入现有的挑战
（1）不泛化
（2）遗忘old tasks

3.再是我们method
一张图
然后写一下我们的亮点
1、提出了一种continual adaption of pretrained robot policy的新范式（learn res rl and merging）
2、explore了model merging在res rl上的探索，并改进了原有的metric，实现了merging后模型成功率效果的提升
3、泛化and不遗忘 — 呼应challenges


4.实验set up


5.实验结果
（1） 主要结果
表格
（2）可视化图
多体现出来，根据我们做的什么改进，产生了什么影响/取得了什么效果

融合前—融合后 
可以融合的group vs 不可融合的group
task相似但correction action field差异很大的

泛化性体现


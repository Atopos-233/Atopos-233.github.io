# 对COVID-19流行病学传播的干预分析

## 摘要

本文使用SEIR-H模型对COVID-19的流行病学传播性质做干预分析，研究了再不同干预条件下病毒的传播水平，并用确诊与死亡人数作为表征。根据干预模型的分析结果，我们对控制病毒传播做了几点建议。

## 正文

2020年春，COVID-19率先在我国爆发，随后世界各地相继爆发。COVID-19传播面广，传播途径多样，因此对COVID-19流行病学性质的研究尤为必要。下文针对COVID-19的传播特点做了干预模型分析。

##SEIR-H模型

### SEIR-H模型简述

SEIR-H模型包括六种仓室：易感者、携带者、轻症患者、中症患者、重症患者和移出者。能够有效反应隔离措施，医疗资源对COVID-19的影响。

详细描述如下：

| 仓室     |                     仓室描述                      |
| :------- | :-----------------------------------------------: |
| 易感者   |   未接触病毒，无免疫力，有一定的概率变成携带者    |
| 携带者   |         携带病毒，但并不具有传染性的人群          |
| 轻症患者 |  具有轻微的临床特征的感染者，可以自行在家隔离。   |
| 中症患者 |  具有较严重的临床特征的感染者，需要在医院住院治   |
| 重症患者 | 具有非常严重的临床特征的感染者，需要在ICU进行治疗 |
| 移出者   |        包括死亡者和因病愈而具有免疫力的人         |

易感者在其中占大多数，易感者与感染者接触后可能转为携带者，也可能转为轻症患者。其中，轻中重症患者可以以一定概率相互转化。移出者中因病愈而具有免疫力的人群，在理想情况（病毒不发生变异）下，不会被再次感染。

###SEIR-H模型推导

$$
\frac{dS}{dt}=-\frac{\beta IS}{N}
\\
\frac{dE}{dt}=\frac{\beta IS}{N}-\alpha E
\\
\frac{dI_1}{dt}=\alpha E-\gamma_1I_1-p_1I_1
\\
\frac{dI_2}{dt}=p_1I_1-\gamma_2I_2-p_2I_2
\\
\frac{dI_3}{dt}=p_2I_2-\gamma_3I_3
\\
\frac{dR}{dt}=\gamma_1I_1+\gamma_2I_2+\gamma_2I_2
$$

其中*S*是易感人群、*I*是感染者、*E*是携带者、*R*是移出者、*N*是人口总数。

参数*β*控制病毒传播的概率（0.27[^1]），*γ*是移出概率（死亡率: 0.011[^2] ），*α*是携带者变成感染者的概率（0.2[^3] ）， *p*是进入下一临床状态的概率（*p*₁=0.033， *p*₂=0.042）[^4]。

## 干预因子

### 环境预设

本实验在虚拟的高密度大型人口规模城市（10000000人/1000平方公里）中进行，在基准环境下，病毒传播始于100个受感染个体，无外来输入病例，医疗资源充足。

### 干扰强度

我们引入4个干扰量对我们的模型进行干扰分析

| 干扰因子     |                   刻画指标                    |
| ------------ | :-------------------------------------------: |
| 社交隔离等级 | A.无隔离措施 B.避免聚集 C.弹性隔离 D.强制隔离 |
| 输入病例     |              每天输入病例的数目               |
| 病床容量     |               重症患者的住院率                |
| ICU容量      |              病危患者的ICU住院率              |



## 数值模拟

### 社交隔离等级的干扰



![image-20210207203115609](C:\Users\微软\AppData\Roaming\Typora\typora-user-images\image-20210207203115609.png)

![image-20210207203207049](C:\Users\微软\AppData\Roaming\Typora\typora-user-images\image-20210207203207049.png)

![image-20210207203259568](C:\Users\微软\AppData\Roaming\Typora\typora-user-images\image-20210207203259568.png)





### 输入病例的干扰

![image-20210207203615993](C:\Users\微软\AppData\Roaming\Typora\typora-user-images\image-20210207203615993.png)



![image-20210207203648179](C:\Users\微软\AppData\Roaming\Typora\typora-user-images\image-20210207203648179.png)





### 病床容量的干扰

![image-20210207204017043](C:\Users\微软\AppData\Roaming\Typora\typora-user-images\image-20210207204017043.png)

![image-20210207204046646](C:\Users\微软\AppData\Roaming\Typora\typora-user-images\image-20210207204046646.png)



![image-20210207204113801](C:\Users\微软\AppData\Roaming\Typora\typora-user-images\image-20210207204113801.png)

### ICU容量的干扰

![image-20210207204211306](C:\Users\微软\AppData\Roaming\Typora\typora-user-images\image-20210207204211306.png)

![image-20210207204330477](C:\Users\微软\AppData\Roaming\Typora\typora-user-images\image-20210207204330477.png)

![image-20210207204418256](C:\Users\微软\AppData\Roaming\Typora\typora-user-images\image-20210207204418256.png)







[^1]: Li R, Pei S, Chen B, et al. Substantial undocumented infection facilitates the rapid dissemination of novel coronavirus (SARS-CoV-2)[J]. Science, 2020, 368(6490): 489-493.
[^2]: Verity R, Okell L C, Dorigatti I, et al. Estimates of the severity of COVID-19 disease[J]. MedRxiv, 2020.
[^3]: Akhmetzhanov A R, Mizumoto K, Jung S, et al. Epidemiological characteristics of novel coronavirus infection: A statistical analysis of publicly available case data[J]. medRxiv, 2020.
[^4]: Wu Z, McGoogan J M. Characteristics of and important lessons from the coronavirus disease 2019 (COVID-19) outbreak in China: summary of a report of 72 314 cases from the Chinese Center for Disease Control and Prevention[J]. Jama, 2020, 323(13): 1239-1242.


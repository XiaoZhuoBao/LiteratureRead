# Ti-doped CeO2 Stabilized Single-Atom Rhodium Catalyst for Selective and Stable CO2 Hydrogenation to Ethanol

Rh-团簇→甲醇

Rh-单原子→乙醇
![加氢生成乙醇的过程.png](加氢生成乙醇的过程.png)

## 计算方法和参数设置

### 计算方法

- **软件包**：使用了Vienna Ab initio Simulation Package (VASP 5.4.4)进行所有自旋极化的DFT计算。
- **交换-相关能量**：采用PBE泛函处理。
- **核心-价电子相互作用**：通过投影增强波（PAW）方法处理。

### 参数设置

- **价电子描述**：
    - 氧 (O)：2s, 2p
    - 铈 (Ce)：5s, 5p, 6s, 5d, 4f
    - 钛 (Ti)：3p, 4s, 3d
    - 铑 (Rh)：5s, 5p, 4d
    - 碳 (C)：2s, 2p
    - 氢 (H)：1s
- **平面波基组截断能量**：400 eV
- **高斯展宽宽度**：0.05 eV
- **DFT + U方法**：用于确定局域电子的库仑势和交换相互作用，Ce 4f态的Ueff为5.0 eV，Ti 3d态的Ueff为4.2 eV。
- **结构优化**：使用共轭梯度算法，直到每个离子的力小于0.03 eV/Å。
- **能量收敛标准**：10^-5 eV
- **布里渊区采样**：在Γ点进行采样。

### 具体工作

- **过渡态搜索**：使用爬升图像弹性带（CI-NEB）方法，并通过频率测试验证。
- **表面模型**：
    - 构建了一个3 × 3的CeO2(111)超胞，包含三层O-Ce-O层和15 Å的真空间隙。
    - 用Ti原子替换一个表面Ce原子，模拟掺钛的CeO2。
    - 使用四层金红石TiO2(110)板块模型模拟TiO2表面。
- **铑结构模块**：在构建的CeO2、掺钛CeO2和TiO2表面上添加一个Rh原子或一个Rh10簇。
- **氧空位**：移除一个表面氧原子以描述氧空位的形成。
- **反应势垒计算**：通过过渡态能量减去初始能量计算。
- **吸附能计算**：
  $$E_{ads} = E(\text{吸附物 + 表面}) - E(\text{吸附物}) - E(\text{表面})$$
  其中，E(吸附物 + 表面)、E(吸附物)和E(表面)分别表示吸附物与表面的能量、气相中自由吸附物分子的能量和清洁表面的能量。负值的Eads表示放热吸附，值越负表示吸附能力越强。

### 结果分析

- **能量计算**：
    - 检查OUTCAR文件，提取每个中间体和过渡态的能量。
    - 绘制反应能量图，分析反应路径。

## 优化后结构

![载体的结构优化.png](载体的结构优化.png)

![Rh在CeO2上的结构.png](Rh在CeO2上的结构.png)

图2解读:

1. 能量剖面图：
    - 纵坐标 (E)：表示能量，单位为电子伏特 (eV)。
    - 横坐标：表示反应路径上的不同状态，从初始状态 (is) 到最终状态 (fs)。
    - TS=1.04：表示过渡态 (TS) 的能量为 1.04 eV。
2. 反应路径：
    - 初始状态 (is)：反应的起点。
    - 过渡态 (TS)：反应物转化为产物的关键步骤，能量最高点。
    - 中间体 (intermediates)：反应过程中出现的中间状态。
    - 最终状态 (fs)：反应的终点。
3. 结构表示
    - 图表下方的面板 (a) 到 (i) 展示了反应路径上不同阶段的分子结构：
        - (a) 初始状态 (is)：反应开始时的结构。
        - (b) 到 (h) 中间体：反应过程中出现的不同中间体，每个中间体的结构和能量不同。
        - (i) 最终状态 (fs)：反应结束时的结构。

          具体分析:
            - 初始状态 (is)：反应开始时，单原子 Rh 位于 CeO_2 模型表面。
            - 中间体：随着反应进行，单原子 Rh 逐渐聚集，形成不同的中间体。每个中间体的能量和结构都有所不同。
            - 过渡态 (TS)：在反应路径上，过渡态的能量最高，为 1.04 eV。这是反应物转化为产物的关键步骤。
            - 最终状态 (fs)：反应结束时，单原子 Rh 聚集形成稳定的结构。

## 工作内容

### Ti 掺杂和 Rh 负载量对反应活性和选择性的影响

![Ov形成能.png](Ov形成能.png)

![Ov形成能2.png](Ov形成能2.png)
在 Rh1/CeTiOx 催化剂模型上计算的不同位点的氧空位形成能和相应结构。

![CO2吸附能比较.png](CO2吸附能比较.png)

![CO形成机制1.png](CO形成机制1.png)
![CO形成机制2.png](CO形成机制2.png)
![CO形成机制3.png](CO形成机制3.png)

![态密度.png](态密度.png)
![态密度分析.png](态密度分析.png)
![Rh团簇降低乙醇选择性.png](Rh团簇降低乙醇选择性.png)
钛掺杂和铑负载对一氧化碳（CO）选择性的影响:

研究发现，在所有单原子催化剂（SACs）中，Rh1/TiO2表现出最高的CO选择性（11.44%），尽管CO2转化率较低（1.28%）。通过密度泛函理论（DFT）计算，支持羧基中间体路径比直接裂解CO2更容易，因为COOH
*中的C-O键由于H原子向C-O键反键轨道的电子供给效应而减弱（1.50 Å vs 1.26 Å for CO2）。Rh1/CeTiOx在COOH*中C-O键裂解的能量障碍较低（0.16
eV），这归因于氧空位（Ov）和相邻Rh单原子位点之间的Lewis酸碱对，O原子与Lewis酸性Ov位点结合，C原子与Lewis碱性Rh位点结合，电亲和和亲核位点的协同效应有助于COOH中C-O键的解离生成CO。Rh1/TiO2显示较低的CO脱附能（1.48
eV），导致较高的CO选择性。计算的CO吸附在Rh
SACs上的态密度显示，Rh1/TiO2中CO和Rh的轨道在费米能级以上有高重叠，表明CO和Rh之间的相互作用较弱。电子电荷密度差异图也证实，在Rh1/CeTiOx中，Ti和Rh原子之间存在较大的电子富集区，有利于通过增强的电子转移形成更强的C-Rh键。增加的Rh负载量略微提高了CO选择性，同时显著提高了甲醇选择性，这可能归因于氧空位（Ov）位点的富集和H
*物种供应的增加，增强了在Ov-Rh
Lewis酸碱对上CO的形成。金属Rh位点有利于CO的解离和氢化，而Rh+位点更有利于CO的稳定。尽管Rh簇上CO吸附略微困难，但它显示出更强的CO*
氢化为CHxO*中间体形成甲醇的能力，Rh簇还导致CO*与CHx*耦合的高能障碍，从而降低了乙醇的选择性。
![团簇和单原子Rh的产物导向.png](团簇和单原子Rh的产物导向.png)

### CO2 加氢反应机理

![不同吸附位点上CO2吸附能.png](不同吸附位点上CO2吸附能.png)
为了深入了解Rh1/CeTiOx催化剂上CO2加氢生成甲醇和乙醇的过程，我们进行了DFT计算，以寻找合理的中间体并建立详细的反应路径。正如前面提到的，Lewis酸碱对促进了CO2的吸附和活化，能量为-1.59
eV（图S59），能量为负值（-1.59 eV）表明吸附过程是放热的，这意味着CO2在这些位点上是稳定的。其中CO2
*具有弯曲结构，C原子与Lewis碱性Rh位点结合，一个O原子与Lewis酸性Ov位点结合。CO2*可以被氢化成HCOO*
，这是一个关键中间体，进一步氢化可以生成HCOOH*和H2COOH*。相比于HCOOH*，H2COOH*中的C-O键裂解更有利（图S60-62）。生成的CH2O*
可以进一步氢化成CH2OH*、CH3O和CH3OH*（图S63-66）。

![1.png](1.png)
![4c.png](4c.png)
![2.png](2.png)
![3.png](3.png)
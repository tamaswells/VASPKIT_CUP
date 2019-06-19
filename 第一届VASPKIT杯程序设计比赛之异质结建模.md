# 第一届VASPKIT杯程序设计比赛之异质结建模

为丰富和完善VASPKIT 软件包的功能，VASPKIT开发者团队决定举办**第一届VASPKIT杯程序设计比赛**。本届比赛以通过编写程序脚本、实现异质结建模为主要内容，期待各方程序设计高手参赛，其中优秀程序作品可将其功能并入**VASPKIT**软件包。此次比赛同时也为了激发广大计算化学工作者动手编程的热情，锻炼大家自己动手以编程的方式解决实际问题的能力。**期待**各位计算学子热情参与。

####  **VASPKIT杯事宜：**

- 参赛时间：7月1日-7月31日。**北京时间**31日22:00**投稿截止**。

- 参赛方式：将自己的**软件源码及参赛文档**发送电子邮件至：[vaspkit_cup@hotmail.com](mailto:vaspkit_cup@hotmail.com)，邮件标题为：“**真实姓名-单位全称-异质结建模**”，中英文皆可。建议附件用同样格式命名。

- 评判方式：**优先看**脚本交互性、普适性、建模效果，次要考虑计算时间.

- 评判团队： **VASPKIT杯组织者团队**，包含**VASPKIT**软件开发者**王伟**，**许楠**，**刘锦程**；新加坡国立大学博士研究生**王添**；中国科技大学博士研究生**吴道雄**；剑桥大学博士后**张召富**（以上排序不分先后）。

- 参赛奖励：**视参与人数与赞助数目定奖金**，保证**至少**一等奖一名，奖金至少**800**元人民币；二等奖至少一名，奖金至少**400**元；三等奖至少一名，奖金至少**200**元；参与奖人数不限，**完成基本内容即可获得参与奖**。同时优秀的代码**有机会**添加到**VASPKIT**主程序中。第一、二、三等奖以**快递邮寄**形式颁发**实体证书**，其他参与者颁发**电子参与证书**。

- 版权和法务：参赛者需要**签署**并提交附件中的参赛文档：<a href="VASPKIT杯程序设计比赛参赛文档.docx">VASPKIT杯程序设计比赛参赛文档.docx</a>，**声明**自己提交的脚本是**自己原创**、并非抄袭的脚本，避免不必要的麻烦。签署方式**推荐手写真实名字**并拍照或扫描为电子版，与自己的作品一起发送到比赛邮箱。**VASPKIT**开发者团队**保证**签名不会用于其他用途。

- 相关链接：

  **VASPKIT**软件官方网站链接：<https://vaspkit.com/>

  **VASPKIT**开发者之一GitHub链接：[https://github.com/tamaswells](https://github.com/tamaswells/VASPKIT_manual) 

  **并行科技**公司官网链接：<https://www.paratera.com/>

#### **参赛须知：**

1. 使用自己独立撰写的**脚本或程序**，来实现下述列举的异质结建模测试项目，完成基本要求即可；加分项为备选项，可以不完成；

2. 输入文件（独立材料的POSCAR）已经提供，输出文件为异质结的POSCAR文件；

3. 程序语言包括但不限于**Python**, **Fortran**, **Shell**, **MATLAB**，**C/C++**,等，推荐选择可以在**Linux**系统下运行的脚本或程序；

4. 异质结建模脚本可以充分调用如**VASPKIT**或者其他**开源**软件/脚本，*如使用商业软件MS等会酌情减分*。如需调用**VASPKIT**以外的脚本，需在上传源码中附上相应的软件/脚本，并详细列清楚使用说明。

5. 下述测试项目中涉及到的文献仅为例子，方便参赛者了解材料结构和基本性质，参赛者可以自己寻找更多参考文献。

6. 最终解释权归**VASPKIT**杯组织者团队

#### **测试项目：**

1.  **2D/2D异质结简单版本**：两个2D材料基矢夹角相同，晶格常数误差范围内相同。例子：MoS2/WSe2

   基本要求：利用提供的01_MoS2_POSCAR 和01_WSe2_POSCAR 文件构建最小原子数、且*mismatch在5%之内*的异质结，初始层间距为3Å，异质结真空15Å，保持异质结基矢夹角与单层材料一致（即120$^{\circ}​$），晶格常数为两个slab材料的平均数。

   注：初始层间距定义为 MoS2 和 WSe2 之间 S 原子层和 Se 原子层之间的距离

   Ref: 2014 Stacking effects on the electronic and optical properties of bilayer transition metal dichalcogenides MoS2, MoSe2, WS2, and WSe2

   加分项1：可以人工自定义初始层间距

   加分项2：可以人工自定义异质结真空厚度

   加分项3：可以人工自定义mismatch

   加分项4：可以人工自定义异质结夹角

   加分项5：可以读取提供的的01_MoS2_bulk_POSCAR和 01_WSe2_bulk_POSCAR两个体材料结构自动切割出单层slab，并且做异质结建模

   加分项6：可以自定义异质结晶格选取标准：使用上层材料晶格、下层材料晶格、上下层材料晶格平均值。

   加分项7： 可以输出多个不同的原子堆垛方式的异质结。输出可以为多个POSCAR文件，也可以使用一个平移矢量表示：异质结中下层材料相对于其 slab 结构中的位置的平移矢量(以分数坐标表示)。以测试项目中提供的 POSCAR 为例，假设 MoS2 在下，构建异质结时不平移，则是 AA 堆垛方式。MoS2 平移 [-1/3 1/3 0] 构建的就是异质结就是 AB’堆垛），参考Phys. Rev. B **89** (2014) 075409, Figure 1.

    

2. **2D/2D异质结中级版本**：两个2D材料基矢夹角相同，晶格常数不同。例子：MoS2/graphene

   基本要求：利用提供的02_MoS2_POSCAR 和02_Graphene_POSCAR 文件构建最小原子数、且*mismatch在5%之内*的异质结，初始层间距为3Å，异质结真空15Å。

   Ref: 2017 First-principles study of the structural and electronic properties of graphene/MoS2 interfaces

   加分项：程序可以输出符合要求 mismatch 前提下，异质结晶胞晶格最小的三种 slab 晶胞搭配方案，并给出这三种搭配方案基本信息，比如异质结晶胞原子数和晶格常数/夹角。

 

3. **2D/2D异质结复杂版本**，两个2D材料基矢夹角不同，晶格常数不同。例子：graphene/black P

   基本要求：利用提供的03_black_P_POSCAR和03_Graphene_POSCAR 文件构建最小原子数、且mismatch在5%之内的异质结，初始层间距为3Å，异质结真空15Å。异质结夹角为90$^{\circ}​$。

   Ref: 2015 Electronic Properties of Phosphorene/ Graphene and Phosphorene/Hexagonal Boron Nitride Heterostructures

   加分项：可以人工自定义满足mismatch的其他异质结夹角

 

4. **金属/半导体异质结**：Ni/MoS2 

   基本要求：利用提供的04_Ni111_POSCAR和04_MoS2_POSCAR 文件构建最小原子数、且*mismatch在5%之内*的异质结，初始层间距为3Å，异质结真空15Å。

   Ref: 2015 3D Behavior of Schottky Barriers of 2D Transition-Metal Dichalcogenides

 

5.  **3D/3D异质结**： HfO2/GaN，其中两侧都是FCC结构

   基本要求：利用提供的05_GaN001_POSCAR和05_HfO2001_POSCAR文件构建最小原子数、且*mismatch在5%之内*的异质结，初始层间距为2Å，异质结真空15Å。

   Ref：2015 GaN as an Interfacial Passivation Layer: Tuning Band Offset and Removing Fermi Level Pinning for III−V MOS Devices

<div style="float:right"><img src="章.png" ></img><br>
<span>VASPKIT杯组织者团队</span><br><br>
<span>2019/06/19</span></span><br><br></div>                                                                                                                                                       

​																					       																				

​                                                                                                                                                                                       
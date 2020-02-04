## 无医疗自由扩散

### 模型参数说明
人数，分布太复杂，直接随机生成分布<br>
pop = 5000 


人群迁移模型属于复杂网络内容，这里直接用感染几率与日均接触人数来简单刻画<br>
传播方法用患病人群的最近距离人数（touch）随机受感染几率（beta）决定<br> 
init_infec =  10 # 初始患者数量<br>
beta = 0.3   # 感染几率<br>
touch = 5   # 日均接触人群数

测试时间100天

####先测试一下不同隔离程度的感染状况

![image](https://github.com/rayzzy/sir_model/blob/master/pic1.gif) 

#### 接触3人，无医疗的传播过程图
![image](https://github.com/rayzzy/sir_model/blob/master/propa3.gif) 
#### 接触5人，无医疗的传播过程图
![image](https://github.com/rayzzy/sir_model/blob/master/propa.gif) 


## 带医疗扩散

### 模型参数说明
参考视频模型，这里主要测试不同床位即医疗条件对病情的抑制情况，治愈时间和症发时间都需要数据参数估计。为简化，直接设置固定治疗时间及症发时间。
并规定如下假设：<br>
1.症发后才能进医院就医<br>
2.进医院后不再感染其他人<br>
3.进医院人员及恢复人员不再被感染<br>
4.不考虑死亡<br>
bed = 100 # 床位<br>
cure_days = 10 # 治愈时间<br>
discover = 10 # 症发时间<br>

之前的传播速度有点过快，在100天内就到边界了，调整一下参数降低扩散速度<br>
init_infec =  10 # 初始患者数量<br>
beta = 0.1   # 感染几率<br>
touch = 4   # 日均接触人群数

#### 测试一下20张床，疫情起飞了

![image](https://github.com/rayzzy/sir_model/blob/master/cure20.gif) 

#### 100张床，基本有效果了

![image](https://github.com/rayzzy/sir_model/blob/master/cure100.gif) 

#### 200张床，100天内基本快压制住疫情了

![image](https://github.com/rayzzy/sir_model/blob/master/cure200.gif) 

#### 200张床传播及治疗过程图
![image](https://github.com/rayzzy/sir_model/blob/master/cured.gif) 

以上基本是全部内容了，时间有限，模型非常简陋，供参考

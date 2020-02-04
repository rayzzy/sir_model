## 自由扩散
人数，直接随机生成分布<br>
pop = 5000  


人群迁移模型太复杂，直接用感染几率与日均接触人数来简单刻画<br>
传播方法用患病人群的最近距离人数（touch）随机受感染几率（beta）决定<br>
init_infec =  10 # 初始患者数量<br>
beta = 0.3   # 感染几率<br>
touch = 5   # 日均接触人群数

测试一下不同隔离程度的感染状况

#### 接触3人，无医疗的传播过程图
![image](https://github.com/rayzzy/sir_model/blob/master/propa3.gif) 
#### 接触5人，无医疗的传播过程图
![image](https://github.com/rayzzy/sir_model/blob/master/propa.gif) 

## 带医疗扩散

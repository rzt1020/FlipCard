## award奖励配置



一张牌的奖励会在开启GUI时根据奖励配置中的奖励方案被row出。

**相同的，每种奖励方案的命名应该是1开始递增1的自然数。**

```yaml
award:
  1:
    type: mc
    material: GOLDEN_APPLE
    amount: 1~5
    rate: 3
    edge: very_rare
```

- type: 奖励方案的种类，mc为minecraft的原版物品、item是在item文件夹中保存的物品、itemsadder是ia插件的物品、mmoitems是mi插件的物品。**每种奖励的配置略有不同**。
- amount: 数量，如果可写成”1”的形式也可以写成”1~5”的形式，区别在于数量是否区间内随机。
- rate: 概率，数值越大越容易被抽到，当有多种奖励时，抽中奖励A的概率为 $$ {P}_{A} $$:

$$
{P}_{A}=\frac {rate_A} {\sum_{k}(rate_{k})}
$$

-  edge: 抽到某种奖励时的边框材质名，可以用来表现稀有度，边框的材质名在config.yml中查看。
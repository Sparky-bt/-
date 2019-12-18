# 研究项目
从世界儿童抚养比看各国家的少年儿童的负担系数问题。

### 项目简介
初步分析：世界儿童抚养比的数据来看，发达国家的儿童抚养比较低，而发展中国家的数值普遍较高。所以目前发展中国家的负担问题主要是对少年儿童的负担，并且少年儿童的负担是老人负担系数的十倍，因为他们完全需要劳动年龄人口抚养，并且还需要智力投资，而老年人可能有积蓄或者尚在劳动。所以发展中国家的每一个家庭儿童负担系数就会占家庭总支出的比重更大。

### 数据来源
世界银行和
https://population.un.org/wpp/Download/Standard/Population/

### 需要的数据
- 世界各国家地区儿童抚养比
- 世界各国人均GDP

### 使用技能
数据清洗
plotly或pyechart制作图表
交互按钮
css元素

### 设想
先画出国际人均GDP的地图，观察发达国家与发展中国家之间人均GDP的差距。之后导入世界儿童抚养比的数据，会发现发达国家的儿童抚养比较低，而发展中国家的数值普遍较高。从而初步分析发达国家由于收入高，人口红利好，所以生育率较低，所以少年儿童的负担系数较低。而发展中国家由于需要青壮劳动力，所以生育率较高，所以每一个家庭的儿童负担系数就会占家庭总支出的比重更大。

### 可能使用的图表类型

- 世界地图
代码示例：
def map_world() -> Map:
    c = (
        Map()
        .add("商家A", [list(z) for z in zip(Faker.country, Faker.values())], "world")
        .set_series_opts(label_opts=opts.LabelOpts(is_show=False))
        .set_global_opts(
            title_opts=opts.TitleOpts(title="Map-世界地图"),
            visualmap_opts=opts.VisualMapOpts(max_=200),
        )
    )
    return c
    
- 漏斗图
代码示例：
from pyecharts.faker import Faker
from pyecharts import options as opts
from pyecharts.charts import Funnel, Page


def funnel_base() -> Funnel:
    c = (
        Funnel()
        .add("商品", [list(z) for z in zip(Faker.choose(), Faker.values())])
        .set_global_opts(title_opts=opts.TitleOpts(title="Funnel-基本示例"))
    )
    return c

![漏斗图](https://github.com/Sparky-bt/Interactive_Visual_final/blob/master/images/%E6%89%B9%E6%B3%A8%202019-12-18%20235344.png)

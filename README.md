# roadmap-data

GenSilicon **AI EDA Roadmap** 的数据源 —— 当前阶段只覆盖**厂商产品时间轴**(`vendors/`),后续可能扩展自主等级、失效模式等数据。

被 [chipai-hub](https://github.com/GenSilicon/chipai-hub)(网站后端)hourly 拉取并通过 `/api/vendors` 提供给前端 `Roadmap → 厂商图谱` 视图。

## 仓库布局

```
vendors/
├── synopsys.yaml        # 一家公司一个 yaml
├── cadence.yaml
├── siemens.yaml
├── ansys.yaml
├── empyrean.yaml        # 华大九天
├── xepic.yaml           # 芯华章
└── ...
```

## 加一个新厂商 / 新产品

1. 在 `vendors/<vendor-id>.yaml` 里追加产品(或新建一个 yaml 文件)。
2. 提交 PR,描述里**附上信息来源**(官网新闻稿 / 媒体报道 / 论文)。
3. 合并后,网站会在下一个整点 + 7 分钟自动同步;也可以联系维护者立即触发 `/api/vendors/refresh`。

> **数据准确性原则**:每条产品**必须有公开来源可核实**,不接受"业内传闻"、"按命名套路推测"。如果某产品的发布日期不确定到月份,只填年份(`date: '2024'`),不要硬填月份。

## yaml 字段说明

```yaml
id: synopsys                # 全站唯一 slug
name: Synopsys              # 显示名(英文)
nameCn: 新思科技             # 显示名(中文,可选)
region: us                  # us | eu | cn
color: '#22d3ee'            # 主色 hex,用于泳道 / 节点高光
accent: '#7c3aed'           # 副色(可选,渐变末端)
tagline: 一句话定位
url: https://www.synopsys.com/ai.html

products:
  - name: DSO.ai
    date: '2020-03'          # YYYY 或 YYYY-MM,引号必加
    stage: ga                # announced | shipped | ga | discontinued
    capabilities:            # 可多选
      - digital-impl         # digital-impl | verification | analog | signoff
                             # | dft | pcb | copilot | multi-physics | foundation
    summary: 一句话功能描述
    url: https://...         # 可选
    highlight: true          # 可选,标志性产品在时间轴放大显示
```

## License

数据为公开信息整理,采用 CC-BY-4.0 协议;贡献者请确保使用的来源允许转述。

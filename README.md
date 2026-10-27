# metricmap

**核对声明的评测指标与实际计算的指标是否一致。**

`metricmap` —— 把指标声明与实现逐项对照，标出名称相近但定义不同的指标

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`metricmap.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install ubidangman-metricmap
```

装完直接用命令名调用：

```bash
metricmap --help
```

也可以不用安装，直接把 `metricmap.py` 拷走用——它只依赖标准库。

## 为什么需要它

只做定义层面的对照，不重新计算指标

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 评测指标对齐 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python metricmap.py --file input.txt
python metricmap.py --text "示例内容"
python metricmap.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 分组靠标签与关键词相似度，分错组时不保证可解释。
- 不评估分组质量。

## 跑测试

```bash
python test_metricmap.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/ubidangman/metricmap>

---

## 关于作者

ubidangman 做评测指标对齐相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://ubidangman.github.io>
- 仓库：<https://github.com/ubidangman/metricmap>

## 许可

MIT，见 [LICENSE](LICENSE)。

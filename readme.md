# FinEval-KR Dataset

This repository contains the sample data for "FinEval-KR: A Financial Domain Evaluation Framework for Large Language Models' Knowledge and Reasoning".

## About the Project

Large Language Models (LLMs) demonstrate significant potential but face challenges in complex financial reasoning tasks requiring both domain knowledge and sophisticated reasoning. Current evaluation benchmarks often fall short by not decoupling these capabilities indicators from single task performance and lack root cause analysis for task failure.

To address this, we introduce **FinEval-KR**, a novel evaluation framework for decoupling and quantifying LLMs' knowledge and reasoning abilities independently, proposing distinct knowledge score and reasoning score metrics. Inspired by cognitive science, we further propose a cognitive score based on Bloom's taxonomy to analyze capabilities in reasoning tasks across different cognitive levels.

This repository releases a new open-source **Chinese** financial reasoning dataset to support reproducible research and further advancements in financial reasoning.

Our experimental results reveal that LLM reasoning ability and higher-order cognitive ability are the core factors influencing reasoning accuracy. We also specifically find that even top models still face a bottleneck with knowledge application. Furthermore, our analysis shows that specialized financial LLMs generally lag behind the top general large models across multiple metrics.

### Citation
[TODO]

## The Dataset

The full FinEval-KR dataset contains 9,782 questions. This open-source release provides a sample of **625 instances** from the full dataset. This sample is representative of the complete dataset and covers all **22 subfields** of finance included in our study.

### Data Format

The data is provided in a JSONL format. Each line in a file is a complete JSON object. Each JSON object contains the following fields:

* **`instruction`**: The evaluation question.
* **`gt`**: The ground truth, showing the detailed step-by-step solution process for the problem.
* **`point`**: The key knowledge points or concepts required to solve the question.
* **`per_step`**: The corresponding cognitive level for each step in the reasoning process.
* **`classification`, `subcategory`**: The domain and sub-domain to which the question belongs.

### Example

Here is an example of a data entry:

```json
{
    "instruction": "在2020年3月新冠疫情爆发之初，虽然当时美国的通货膨胀率保持在目标水平2%，但美联储出于对经济下行风险的担忧，决定将联邦基金利率从1.5%大幅下调至0.25%。假设此时的均衡实际利率（r*）为0.5% ...", 
    "gt": "步骤一：根据泰勒规则公式计算联邦基金利率：\n\\[ i = r^* + \\pi + 0.5 (\\pi - \\pi^*) + 0.5 (Y - Y^*) \\]\n步骤二：代入已知数据：\n- 平衡实际利率 \\( r^* = 0.5\\% \\)\n- 实际通货膨胀率 \\( \\pi = 2\\% \\)\n- 目标通货膨胀率 \\( \\pi^* = 2\\% \\)\n- 产出缺口 \\( Y - Y^* = 0 \\)...", 
    "point": "泰勒规则 名义利率计算 货币政策宽松 实际利率决策 经济下行风险。", 
    "per_step": "{'步骤一': '记忆 理解', '步骤二': '应用', '步骤三': '应用', '步骤四': '应用', '最终答案': '评价'}", 
    "classification": "金融", 
    "subcategory": "货币金融学"
}
```



### Subfields Covered

The dataset encompasses a wide range of financial topics, categorized into the following 22 subfields:

1. Intermediate Financial Accounting (中级财务会计)
2. Advanced Financial Accounting (高级财务会计)
3. Cost Accounting (成本会计学)
4. Management Accounting (管理会计学)
5. Financial Management (财务管理学)
6. Auditing (审计学)
7. Monetary Finance (货币金融学)
8. Financial Engineering (金融工程学)
9. Central Banking (中央银行学)
10. Investments (投资学)
11. Financial Markets (金融市场学)
12. Commercial Banking (商业银行金融学)
13. International Finance (国际金融学)
14. Corporate Finance (公司金融学)
15. Insurance (保险学)
16. Public Finance (财政学)
17. Econometrics (计量经济学)
18. Microeconomics (微观经济学)
19. Macroeconomics (宏观经济学)
20. International Economics (国际经济学)
21. Corporate Strategy and Risk Management (公司战略与风险管理)
22. Tax Law (税法)

## Authors

* **Shaoyu Dou\*** (Ant Group)
* **Yutian Shen\*** (Shanghai University of Finance and Economics)
* **Mofan Chen\*** (Shanghai University of Finance and Economics)
* **Zixuan Wang** (Shanghai University of Finance and Economics)
* **Jiajie Xu** (Shanghai University of Finance and Economics)
* **Qi Guo** (Ant Group)
* **Kailai Shao** (Ant Group)
* **Chao Chen** (Ant Group)
* **Haixiang Hu** (Ant Group)
* **Haibo Shi** (Shanghai University of Finance and Economics)
* **Min Min** (Shanghai University of Finance and Economics)
* **Liwen Zhang** (Shanghai University of Finance and Economics)

(*Equal contribution)

## License

The released dataset is distributed under the Creative Commons Attribution-NonCommercial 4.0 International License (CC BY-NC 4.0).


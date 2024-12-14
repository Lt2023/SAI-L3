# SAI LLM_Mode1

## 🚩项目简介

本项目是一个基于 TensorFlow 和 Keras 构建的简单中文-英文语言模型。模型使用 LSTM 神经网络进行文本生成，支持从自定义数据集训练，生成针对问题的自然语言回答。它可以适应不同领域的问题，生成基于输入的唯一和多样的回答。

模型训练过程中，使用了中文分词工具 `jieba` 来处理中文文本，并通过 `Tokenizer` 将文本转化为数字序列进行神经网络训练。生成的回答通过 Top-k 采样进行随机化，从而避免每次生成相同的回答。

## ⚠️版权声明

- **非商业性使用**：作品可以被共享、复制和修改，但仅限于非商业用途。
- **禁止商业用途**：作品不得用于商业目的，如销售、租赁或任何形式的商业经营。
- **署名要求**：在使用作品时，必须适当地标明作者并提供协议副本。
- **免责声明**：作品是“按原样”提供的，作者不承担因使用作品而产生的任何责任。

## 😮功能特点

- **中文文本处理**：通过 `jieba` 对中文问题和答案进行分词。
- **LSTM 网络模型**：使用 LSTM 神经网络构建语言模型，生成自然语言回答。
- **自定义训练数据**：用户可以加载自己格式化的 JSON 数据文件进行模型训练。
- **生成多样化回答**：采用 Top-k 采样方法，确保每次回答不重复。
- **逐步显示回答**：生成回答时，逐步显示各个部分并按序号输出。

## 🫥环境要求

### ✨必要依赖

- TensorFlow 2.11.0
- NumPy 1.23.5
- Jieba 0.42.1
- TermColor 2.3.0
- TQDM 4.64.1

### 🥽安装依赖

您可以通过以下命令安装所有依赖项：

```bash
pip install -r requirements.txt

```
## 🧾数据格式
### 项目支持自定义数据集，数据需以 JSON 格式存储。每个数据项包含问题（question）和回答（answer）。以下是数据集格式的示例：
```bash
{
  "data": [
    {
      "question": "你是谁？",
      "answer": "我是一个语言模型。"
    },
    {
      "question": "今天的天气如何？",
      "answer": "今天天气晴，适合出门。"
    }
  ]
}
```

### 🗝️您可以根据需要编辑 train_data.json 文件。每个问题和答案都可以根据具体应用进行修改和添加。

## 修改数据集：

### 打开 train_data.json 文件。
### 添加新的问题和答案对，确保每对数据都包含 question 和 answer 字段。
### 保存文件，重新运行训练脚本。
### 您可以根据自己的需求扩展数据集内容，使其适应不同领域的问答对。

## 项目文件说明
以下是本项目中各个文件的作用：

### model.py：此文件包含语言模型的实现，包括 LSTM 网络结构、训练逻辑和文本生成函数。用户可以在此文件中调整网络的架构（如层数、单元数等），以及控制文本生成的行为（如温度、最大生成长度等）。

### train.py：此文件负责模型的训练和用户交互部分。在该文件中，您可以设置训练轮次（epochs），以及开始训练并保存训练好的模型。训练完成后，它会启动一个简单的交互式问答界面，用户可以输入问题，模型会给出答案。

### train_data.json：这是您的训练数据文件。每一条数据包含一个问题和对应的答案。您需要根据自己的需求修改此文件来训练模型。

### requirements.txt：列出所有项目运行所需的依赖项。使用 pip install -r requirements.txt 安装所有依赖库。


## 😅如何训练模型
准备数据：修改 train_data.json 文件，确保数据格式正确。
训练模型：运行 train.py 文件来开始训练，默认情况下，模型会进行 10 轮训练。如果您希望修改训练轮数，可以调整 train.py 中的 model.train(epochs=10) 参数。
交互使用：训练完成后，程序会进入一个交互模式，您可以输入问题并接收模型生成的回答。输入 exit 可退出程序。
生成回答
当模型训练完成后，您可以通过交互模式提问，模型会返回生成的回答。生成的回答将被逐步显示，每个部分都会用 "回答1", "回答2" 等标号表示，直到回答完整为止。

## 🫠项目结构
```bash
├── model.py              # 模型定义文件，包含 LSTM 网络和训练代码
├── train.py              # 训练脚本，包含模型训练和用户交互代码
├── train_data.json       # 训练数据文件（包含 question 和 answer）
├── requirements.txt      # 项目依赖文件
└── README.md              # 项目目录以及内容相同，支持英文对话，参数量更大。
```

## 😁相关论文和文章
## 《Sequence to Sequence Learning with Neural Networks》 - Google 深度学习团队提出的 Seq2Seq 模型。
## 《Long Short-Term Memory》 - LSTM 网络的原始论文，介绍了 LSTM 如何解决传统 RNN 的长程依赖问题。
## 《A Survey on Language Models》 - 综述文章，介绍了现代语言模型的进展，包括基于 Transformer 的模型（如 GPT 和 BERT）等。

# 贡献
### 如果您有改进建议或想要贡献代码，欢迎通过 GitHub 提交 issues 或 pull requests。

# 联系方式
### 如果您有任何问题或需要帮助，请通过以下方式联系：

### 通过 GitHub Issues 提交问题
### 通过 Email:anan15919991635@163.com 联系我

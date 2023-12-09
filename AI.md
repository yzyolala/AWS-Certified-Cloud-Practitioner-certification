## 亚马逊识别（Amazon Rekognition）：

此服务提供面部分析和识别、对象和场景检测以及图像和视频中的文字。它经常用于用户验证、人数统计和与数据库或名人面孔进行比较。

**想要在图像和视频中找到物体、人物、文本或场景**

## 亚马逊转录（Amazon Transcribe）：

一个自动语音识别服务，旨在将语音转换成文本。它还可以从转录中删除个人可识别信息，并支持多语言音频的自动语言识别。

## 亚马逊Polly（Amazon Polly）：

该服务使用深度学习将文本转换为逼真的语音。它使开发人员能够创建可以交谈的应用程序。

## 亚马逊翻译（Amazon Translate）：

一种语言翻译服务，提供自然和准确的语言翻译，帮助本地化国际用户的内容，并能高效翻译大量文本。

## 亚马逊 Lex 和 Connect:

Amazon Lex: 使用与亚马逊Alexa相同的技术，它可以将语音转换为文本（ASR），并且理解自然语言以识别文本和来电者的意图。这项服务有助于构建聊天机器人和呼叫中心机器人。

Amazon Connect: 是一个接听电话、创建联系流程的云基础虚拟联系中心。它可以与其他客户关系管理（CRM）系统或AWS集成，无需预付费用，比传统联系中心解决方案便宜80%。

流程：从电话呼入开始，通过Connect服务接入，然后使用Lex进行语言识别，再通过Lambda服务执行调用，最后与CRM系统进行日程安排。

## 亚马逊 Comprehend:

这是一个为**自然语言处理（NLP**而设计的完全托管和无服务器服务。

它使用机器学习来发现文本中的洞见和关系，包括识别文本的语言、提取关键短语、地点、人物、品牌或事件，并理解文本的情感倾向。

它还能分析文本的词汇化和词性，并自动按主题组织文本文件集合。

示例用例包括分析客户互动（如电子邮件）以找出导致积极或消极体验的原因，以及创建并按主题对文章进行分组，Comprehend将揭示这些主题。

## 亚马逊 SageMaker:

这是一个全面托管的服务，供开发者和数据科学家构建、训练和部署机器学习模型。

它简化了机器学习流程，使用户能在一个地方完成所有相关的机器学习过程并配置服务器。

## 亚马逊 Forecast:

这是一个使用机器学习提供高精度预测的全面托管服务。

例如，它可以预测雨衣的未来销售情况，并且声称比直接观察数据本身要准确50%。

它可以减少预测时间，从几个月缩短到几小时，并用于产品需求规划、财务规划、资源规划等多个用例。

## 亚马逊 Kendra:

这是一个由**机器学习提供支持的全面托管的文档搜索服务。**

它可以从文档中提取答案（包括文本、PDF、HTML、PowerPoint、MS Word、常见问题解答等格式的文档）。

它具有自然语言搜索功能，并能从用户互动/反馈中学习，以推广首选结果。

## 亚马逊 Personalize:

**使开发人员能够轻松地为客户在其应用程序中创建个性化的推荐。**

这是一个全面托管的机器学习服务，用于构建带有实时个性化推荐的应用程序。

它可以集成到现有网站、应用程序、SMS、电子邮件营销系统等中，并在几天而不是几个月内实施。

## 亚马逊 Textract:

这是一个自动提取扫描文档中的文本、手写内容和数据

## 总结

Rekognition（识别）：人脸检测、标签化、名人识别

Transcribe（转录）：音频转文本（例如：字幕）

Polly（波莉）：文本转音频

Translate（翻译）：翻译服务

Lex（莱克斯）：构建对话机器人 - 聊天机器人

Connect（连接）：云联系中心

Comprehend（理解）：自然语言处理

SageMaker（贤者制造者）：为每个开发人员和数据科学家提供机器学习

Forecast（预测）：构建高度精确的预测

Kendra（肯德拉）：基于机器学习的搜索引擎

Personalize（个性化）：实时个性化推荐
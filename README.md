# tesseract_learn
Learn and study Tesseract-OCR

# 识别引擎
Tesseract 4.0开始 版本具备两种识别引擎：
- 新的基于LSTM（神经网络）引擎
- 传统引擎。

# 通过在初始化时设定不同的EngineMode启动。
  - 0    Legacy engine only.
  - 1    Neural nets LSTM engine only.
  - 2    Legacy + LSTM engines.
  - 3    Default, based on what is available.
  - 当设置OcrEngineMode为2时，则表示启动双引擎进行识别，Tesseract首先会尝试LSTM引擎，如果识别失败，则会再使用传统引擎进行识别，此种模式追求高精确度，但会消耗较多的系统资源。
    
# GitHub上tessdata类型
 - tessdata_fast （https://github.com/tesseract-ocr/tessdata_fast）  基于LSTM引擎的训练数据，不可以用于传统引擎。
 - tessdata_best （https://github.com/tesseract-ocr/tessdata_best）  基于LSTM引擎的训练数据，不可以用于传统引擎。
 - tessdata      （https://github.com/tesseract-ocr/tessdata）       基于传统引擎的训练数据，不可以用于LSTM引擎。
 
# 压缩/合并训练数据*.traineddata
## 1. 解压
### 含义为：将当前路径上一级目录中的eng.trainneddata解压到当前目录中名称为1的子目录，且所有文件以eng.开头。
| combine_tessdata -u ..\tessdata\eng.traineddata ..\tool\jTessBoxEditor\samples\eng\eng.
| combine_tessdata -u ..\tessdata\chi_sim.traineddata ..\tool\jTessBoxEditor\samples\chi_sim\chi_sim.


## 2. 合并 
### combine_tessdata .\eng. 命令则会将当前路径下以eng.开头的文件打包到eng.trainneddata，执行成功效果如下
| combine_tessdata ..\tool\jTessBoxEditor\samples\eng\eng.



# startup

github page:[open-mmlab/mmdetection: OpenMMLab Detection Toolbox and Benchmark (github.com)](https://github.com/open-mmlab/mmdetection)

大致就是，通过config file导入模型，将导入的模型与checkpoints共同运行构建检测模型，可以较方便地完成train与inference的任务。

安装一定要注意cuda的版本（`\usr\local\cuda`）！！！使用conda创建一个共mim使用的虚拟环境。

在doc: https://mmdetection.readthedocs.io/en/latest/ 可以查找到所有的API reference。

现在大概知道了怎样运行已有的模型，如果要做出更改呢？怎么做？

注意torch，torchvision，cudatoolkit，CUDA的版本都需要对应，四个package间存在的所有对应关系都需要满足需求！

注意从清华源安装的torch和torchvision不是gpu版本的！需要`-c pytorch`安装才能安装gpu版本！

应该是装好了……最后一个`nms is not compiled with GPU support `问题，貌似是装了mmdet，mmcv之后又重装过torch和torchvision导致的，之后重装了**mmcv（这个报错track到了mmcv）**和mmdet之后可以执行verification代码了。

（现在的mmcv和mmdet是用的我clone下来的github代码安装的，版本分别是1.3.8和2.14.0，符合相互对应关系、与cuda对应关系的要求！）

**一定一定要注意包的安装顺序！**
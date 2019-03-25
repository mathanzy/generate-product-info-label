# generate product info label in Excel
Automatically generate product information by using python openpyxl 自动根据产品信息批量生成标签。

作为一个生产型企业，其产品种类繁多。按照客户要求，每种产品在出货时都需要在包装上贴上如下信息标签，以便识别。 标签上需要包含6种信息：“品牌、型号、物料编号、批次号、生成日期、数量”。

我们注意到原始信息中的品牌，有些是大写，有些是小写，而标签要求全部大写，因此在填入之前需要先做处理。公司的常规做法是充分发挥人海战术，安排一个小组的人一哄而上，先手动将小写字母替换为大写，然后开始一系列的"复制"加"粘贴"。通常完成一个物料的标签信息需要35秒，100个物料就需要约1小时。可怜那些操作人员，除了手酸，脖子硬，眼睛疼，再加上键盘上的“ctrl，C，V”三个键像光头一样光滑外，还容易出错。如果原始信息有误，部分标签还得小心翼翼、如履薄冰地重新复制粘贴来修正。有时候，操作人员一走神，复制或者粘贴错了，还会被客户投诉，继而被老板训斥，整个心情都不好了。

通常一个订单有上百种物料，每天需要处理约30个订单，需要4个人全职处理这些信息。使用Python, 只需要很少量代码即可轻松搞定，运行只需几秒钟时间。只要原始信息没问题，Python会保质保量完成任务。

首先，我们需要将空白标签的格式复制足够多个。为方便打印，本例是在A4纸上每排放3个标签。也可让Python去自动填写标签第一列的信息，但涉及格式操作，还不如在Excel内直接设置方便。

以上操作完成后，就可以开始后续的信息读取和填写了，步骤如下：

1.从“info”工作表读取所有物料的信息
2.转换字母为大写，存储好信息
3.将处理好的信息逐个写入到“label”工作表
4.保存工作表

就在情人节前一天一款叫ControlNet的SD插件发布了，这款插件在短短的两天内成为了AI绘画领域最新的热点。而它的出现代表着AI生成开始进入真正可控的时期，而AIGC的可控性是它进入实际生产最关键的一环。

在此之前，大家用了很多方法想让AI生成的结果尽可能的符合要求，但是都不尽如人意，ControlNet 比之前的 img2img 要更加的精准和有效，可以直接提取画面的构图，人物的姿势和画面的深度信息等等。有了它的帮助，就不用频繁的用提示词来碰运气，抽卡式的创作了。

## **ControlNet的作者：张吕敏**

![](https://pic4.zhimg.com/v2-01fd8a0542ba723e6cca9c5a8b3222fb_b.jpg)

ControlNet 的作者是一个2021年才本科毕业，目前正在斯坦福读博的中国人。

之前很火的 Style2Paints 也是他制作的，除此之外他还做了一款名为 YGOPro2 的Unity 纸牌游戏，这款游戏在国内外都有不少粉丝。

![](https://pic3.zhimg.com/v2-0b2d09b6dfb277b12bd6123ee0389222_b.jpg)

AI线稿上色这个领域一直都是他在做，感觉几乎没有其他人了，不知道是大厂嫌这块蛋糕太小还是其他原因。Style2Paints 今年1月已经迭代到了第5版。下图是Style2Paints 线稿到插画的示例图。

![](https://pic2.zhimg.com/v2-0736de18207f937536614de087399385_b.jpg)

**Style2Paints的项目地址：**[https://github.com/lllyasviel/style2paints/tree/master/V5\_preview](https://github.com/lllyasviel/style2paints/tree/master/V5_preview)

在读博，写论文，做这些AI工具之余还能玩票做了一款热度还挺高的游戏，现在的00后都这么强的么？

##   
**ControlNet是什么？**

ControlNet 直译就是控制网，ControlNet 是作者提出的一个新的神经网络概念，就是通过额外的输入来控制预训练的大模型，比如 stable diffusion。这个本质其实就是端对端的训练，早在2017年就有类似的AI模型出现，只不过这一次因为加入了 stable diffusion 这样优质的大模型，让这种端对端的训练有了更好的应用空间。

它很好的解决了文生图大模型的关键问题：单纯的关键词的控制方式无法满足对细节控制的需要。

ControlNet 把每一种不同类别的输入分别训练了模型，目前公开的有下面8个。分别是：canny，depth，hed，mlsd，normal，openpose，scribble，seg。

![](https://pic4.zhimg.com/v2-d09cce54de68386b0ee0917cf9b1efdb_b.jpg)

## **ControlNet 相关资源**

**ControlNet项目地址：**[https://github.com/lllyasviel/ControlNet](https://github.com/lllyasviel/ControlNet)

**ControlNet 的 WebUI 扩展：**[https://github.com/Mikubill/sd-webui-controlnet#examples](https://github.com/Mikubill/sd-webui-controlnet#examples)

**模型下载（5G）**[https://huggingface.co/lllyasviel/ControlNet/tree/main/models](https://huggingface.co/lllyasviel/ControlNet/tree/main/models)

**模型下载（700mb）**[https://huggingface.co/webui/ControlNet-modules-safetensors/tree/main](https://huggingface.co/webui/ControlNet-modules-safetensors/tree/main)

**中文教程：**

**英文教程：**[https://www.youtube.com/watch?v=vFZgPyCJflE](https://www.youtube.com/watch?v=vFZgPyCJflE)

[https://www.youtube.com/watch?v=OxFcIv8Gq8o](https://www.youtube.com/watch?v=OxFcIv8Gq8o)

[https://www.youtube.com/watch?v=YJebdQ30UZQ](https://www.youtube.com/watch?v=YJebdQ30UZQ)

**controlNet导入方法（日语）**[https://miro.com/app/board/uXjVPnNbqTA=/](https://miro.com/app/board/uXjVPnNbqTA=/)

## **ControlNet可以做什么？**

**1 canny 边缘检测，提取线稿**

通过从原始图片中提取线稿，来生成同样构图的画面。这个案例是输入鸟的图片和提示词。

![](https://pic3.zhimg.com/v2-670affaf8ac7deee56d4202dd775cf96_b.jpg)

通过给线稿上色来制作的小动画，稳定性很好。

[![](https://picx.zhimg.com/v2-64a3304afa03dfa6238397e155ad4036.jpg?source=382ee89a)https://www.zhihu.com/video/1609677566062575616](https://www.zhihu.com/video/1609677566062575616)

图片来源：[https://twitter.com/izumisatoshi05/status/1625835599017148416](https://twitter.com/izumisatoshi05/status/1625835599017148416)

### **2 depth 深度检测，提取深度图**

通过提取原始图片中的深度信息，可以生成具有同样深度结构的图。

![](https://pic2.zhimg.com/v2-fc8662c7ca32c57a7d0dfba40eb23a59_b.jpg)

用Blender创建空间→创建深度图→用ControlNet Depth创建插图→粘贴为Blender空间中的纹理，就可以创建无限弹出的立体书

[![](https://picx.zhimg.com/v2-0335a5115199ea5dbee4a2cbecdc54df.jpg?source=382ee89a)https://www.zhihu.com/video/1609677363276673024](https://www.zhihu.com/video/1609677363276673024)

来源：[https://twitter.com/TDS\_95514874/status/1625849823957233664](https://twitter.com/TDS_95514874/status/1625849823957233664)

### **3 hed HED边缘提取，跟canny类似**

![](https://pic2.zhimg.com/v2-f460e709502204f3f6c6ad02568cc4c1_b.jpg)

相对于使用普通的 img2img ，边缘线提取的方式可以生成更加清晰完整的图，黑色描边也得到了很好的重绘。

![](https://pic3.zhimg.com/v2-c27220344e15eadfbcbc2620673cd4ca_b.jpg)

图片来源：https://twitter.com/hesui\_channel/status/1625462909878034433

### **4 mlsd 线段识别，适用于建筑场景**

![](https://pic4.zhimg.com/v2-13b736b00496fac31e8aba600f9468ef_b.jpg)

### **5 normal 模型识别，适用于建模**

跟深度图有点类似，通过读取原图片中的深度信息和法线背景阈值。它比深度模型对于细节的保留更加的精确。

![](https://pic2.zhimg.com/v2-78e52b97e8b6db43437f0beb7c991999_b.jpg)

### **6 openpose 姿势识别，用于人物动作**

这个功能对于人物设计和动画十分有利，应该会很快用在影视行业。

![](https://pic1.zhimg.com/v2-c17ec2410cf24970daaa40168616a3e0_b.jpg)

除了生成单人的姿势，它甚至可以生成多人的姿势，这点非常关键，在此之前AI生成的画面里多个人物的特定动作是几乎无法靠提示词来实现的。

![](https://pic2.zhimg.com/v2-9b4d55e7da79684851d23af51aaf119d_b.jpg)

图片来源：https://twitter.com/toyxyz3/status/1626138471256715265

通过控制人物姿势，在人物角色设计上的尝试。

![](https://pic1.zhimg.com/v2-8af8af5151ecf327fa893b704e71df58_b.jpg)

图片来源：https://twitter.com/DiffusionPics/status/1626012676554952707

### **7 scribble 黑白稿提取**

![](https://pic1.zhimg.com/v2-512f2dade2bca6c700f0fba35608a360_b.jpg)

图片来源：https://www.bilibili.com/read/cv21848861/

### **8 seg 语义分割识别**

这个之前英伟达做过类似的产品。

![](https://pic2.zhimg.com/v2-bb0a8f3865091f704db29ce004edfb8d_b.jpg)

## **总结**

AI工具以及细分领域应用的公司们，可以做的事情越来越多了。而今年才过了不到两个月，我们无法想象在年底的时候，AIGC的发展会到达什么样的程度。

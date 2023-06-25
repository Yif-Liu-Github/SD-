***本文正在参加 人工智能创作者扶持计划***[#人工智能作者扶持计划](https://juejin.cn/magic/eco/runtime/release/645b024810b64a0356a51db4?appType=juejin&magic_page_no=1?utm_source=web10&utm_medium=feed&utm_campaign=rgznqy202305 "https://juejin.cn/magic/eco/runtime/release/645b024810b64a0356a51db4?appType=juejin&magic_page_no=1?utm_source=web10&utm_medium=feed&utm_campaign=rgznqy202305")

大家好，我是小鱼姐姐。

开局一张图，首图是我好多年前画的一幅画，最近实验拿出来让AI Scribble一下，大家能看出来哪个是人工涂色，哪个是AI涂色么？？

上节我们简单介绍了一下Stable Diffusion的基础模型及lora，今天我们接着讲解一下SD提示词的实践篇及ControlNet常用模型篇，本文总字数3000+，同时包含大量的图片及提示词分享。欢迎阅读。

## SD如何写提示词

下面是我多方整理以及自己常用的一些标准提示词，在我的案例中，大家也基本能看出来，我经常用这些提示词。 我按标准提示词、内容提示词、画幅构图视角、提示词的权重分配、正向提示词示例、反向提示词给大家都举了一些例子，欢迎尝试。

## 一、标准提示词

**通用高画质：**

masterpiece:杰作

nsanely detailed，ultra-detailed，highly detailed：疯狂的细节，超精细的细节绘制

best quality：高质量

**特定高分辨率类型：**

HD Quality：高清

8k：8k高清

sharp focus：焦点清晰

unreal engine rendered：虚幻渲染

**画家风格：**

19世纪肖像画家：John Collier

偏写实和现代风格：Stanley Artgerm Lau

擅长女性肖像，偏印象派：John Singer Sargent

擅长画平面肖像：Alphonse Mucha

**画风：**

插画风：illustration,painting,paintbrush

二次元：anime,comic,game CG

写实系：photorealistic,realistic,photograph，Ultra realistic illustration

肖像画风：Portrait 用于生成脸部或者头像

数字艺术风格：Digital painting

2D插图风格：Concept art

Ultra realistic illustration

**风格：**

印象派：hyperrealistic

超现实主义：fantasy

波普艺术：surrealist

## 二、内容提示词：

**人物及主体特征：**

精致的脸，清晰的脸：exquisite face，clear face

服饰搭配：white dress

发型发色：blonde hair,long hair

五官特点：small eyes, big mouth

面部表情：smiling

肢体动作：stretching arms

人物皮肤：(high detailed skin:1.2)

**场景特征：**

室内/室外：indoor/outdoor

大场景：forest,city,street

小细节：tree,bush, white flower

**环境光照：**

白天黑夜：day/night

特定时段：morning,sunset

光环境：sunlight,bright,dark

天空：blue sky, starry sky

## 三、画幅构图**视角：**

十种基础构图关键词：

对称构图：Symmetrical composition

对角线构图：diagonal composition

水平线构图：horizontal composition

散点构图：Scattered composition

遮挡构图：blocking composition

线条构图：Line composition

仰拍构图：upside-down composition

俯拍构图：perspective composition

对比构图：Contrast composition

架构式构图：frame composition

距离：close-up,distant

**其他一些常用的提示词：**

人物比例：full body,upper body

观察视角：from above, view of back

aerial view/aerial photography/overhead shot---鸟瞰，做一些宏达的场景俯视图

镜头类型：wide angle,sony v7

适合景色的一些构图：

massive scale宏伟场景构图

Epic level composition史诗级构图

street level view路人视角

lush vegetation茂盛的植被

idyllic田园般的

Matte painting当总是远景，希望有近景，景深一点

blurry background背景虚化

## 四、提示词的权重分配

**括号+数字：**

（red flower:1.5）:调节red flower出现的权重是原来的1.5倍，加强。

（red flower:0.5）:调节red flower出现的权重是原来的0.5倍，减弱。

**套括号：**

（(red flower))：每套一层，权重*1.1倍，此处表示调节red flower出现的权重是原来的1.1*1.1倍，加强。

{{red flower}}：每套一层，权重*1.05倍，此处表示调节red flower出现的权重是原来的1.05*1.05倍，加强。

\[\[red flower\]\]：每套一层，权重*0.9倍，此处表示调节red flower出现的权重是原来的0.9*0.9倍，加强。

## 五、正向提示词示例：

((masterpiece)),((nsanely detailed)), ((intricate)),((exquisite face))illustration,a beautiful young girl ,full body，standing，white dress，perfect lighting

常用模板：画质标准+风格+人物特征要求+光线

## 六、反向提示词：

一般写你不希望画面中出现的内容。

watermark 水印

Low/worst quality 低质量

Logo 标识文字

NSFW 不需要的属性

个人常用的反向提示词1：

NSFW,lowrs,blurry,(deformed, distorted, disfigured:1.3), (stacked torsos:1.2), (totem pole:1.1), poorly drawn, bad anatomy, wrong anatomy, missing arms, missing legs, extra arms, extra legs, fused fingers, too many fingers, long neck,extra limb, missing limb, floating limbs, (mutated hands and fingers:1.4), disconnected limbs, mutation, mutated, ugly, disgusting, blurry, amputation, (extra fingers:1.2), (worst quality, low quality:1.3)out of frame, worst quality, low quality, jpeg artifacts, ugly, duplicate, morbid, mutilated, mutation, deformed, blurry, dehydrated, bad proportions, extra limbs, cloned face, disfigured, gross proportions, malformed limbs

个人常用的反向提示词2：

NSFW，out of frame, worst quality, low quality, jpeg artifacts, ugly, duplicate, morbid, mutilated, extra fingers, mutated hands, poorly drawn hands, poorly drawn face, mutation, deformed, blurry, dehydrated, bad anatomy, bad proportions, extra limbs, cloned face, disfigured, gross proportions, malformed limbs, missing arms, missing legs, extra arms, extra legs, fused fingers, too many fingers, long neck

没有人物时常用的反向提示词：

NSFW，out of frame, worst quality, low quality

## 七、案例：

下面再给大家看个实际的例子吧.

1、不加任何画质、风格的提示词。

大模型选择：sd1.5基础大模型

提示词：a beautiful young girl,white dress

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/a5242ff6abb6428a8916dbc745888b02~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

可以看出来脸部、手部、画风都比较一般。

下面我加上对画质的要求（比如：masterpiece、exquisite face）、风格（比如：photorealistic）的要求、还有镜头距离的要求（比如：close up）、反向提示词看看效果：

提示词：((masterpiece)),((exquisite face)),((best quality)),((photorealistic)),a beautiful young girl,white dress,close up, Appropriate lighting

反向：NSFW，out of frame, worst quality, low quality, jpeg artifacts, ugly, duplicate, morbid, mutilated, extra fingers, mutated hands, poorly drawn hands, poorly drawn face, mutation, deformed, blurry, dehydrated, bad anatomy, bad proportions, extra limbs, cloned face, disfigured, gross proportions, malformed limbs, missing arms, missing legs, extra arms, extra legs, fused fingers, too many fingers, long neck

生成图片如下：（可以看出来，脸部算比较清晰精致了，然后也理解了真实的摄影风格，然后近景）

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/10ed0735c32d4deca6439ce9ad7a9e6d~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

## CONTROLNET简介

ControlNet是斯坦福大学研究人员开发的Stable Diffusion的扩展，使创作者能够轻松地控制AI图像和视频中的对象。它将根据边缘检测、草图处理或人体姿势等各种条件来控制图像生成。ControlNet可以概括为一种简单的稳定扩散微调方法。下面我给大家简单介绍一下ControlNet如何使用，下图是ControlNet的webui的页面，我着重讲一下标识出来的4个模块：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/eb519f3b9d3f430489b39a0fa1558a5c~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

## 1、在ControlNet Image：

常用几个选项:

+   Enable :选中此框以启用ControlNet。（需要使用controlnet时这个启用一定要勾选，还有电脑显存较小时勾选上，其他选项我平时用的不多）
+   Low VRAM（低显存模式）:这将减缓ETA进程，但有助于使用更少的计算空间(显存小于6 GB VRAM建议使用)
+   Pixel Perfect（像素完美）：勾选后会更清晰,画面色调会更基于原图

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/aa20df49fb2648e998512cbd6f0de264~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

+   Allow preview：预览模式，勾选后，右侧可以预览不同模型的预览效果。

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/9194f6baf034456ab47b6d9ce9f0e05d~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

## 2、文生图+ControlNet 模型：

这里还是基于上面那个SD案例中的白裙小女孩，我们先加上controlnet看看效果吧。后续第三节再细节每个controlnet模型的使用场景哈。

提示词保持不变：((masterpiece)),((exquisite face)),((best quality)),((photorealistic)),a beautiful young girl,white dress,close up, Appropriate lighting

加上ControlNet-candy的效果：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/e123049147cf42fc8fb17c225583d3f1~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

生成图片效果如下：（白裙、精致的脸庞、candy姿势基本都保持了，👍）

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/91c4782baffd47558001ac31ed97c4e9~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

## 3、control model模型：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/e63bee3cbe5c405ba68a8edf60e77041~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

（此图来源于网络，供大家简单理解）

以下原图是自己拍摄的一张图片，后续尽量都会基于这张图片试验controlnet的各种图生图的效果。

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/b63328a72d57447485a687a133c41eb0~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

### canny-一线稿

Canny通过使用边缘检测器创建高对比度区域的轮廓来检测输入图像。线条可以捕捉到非常详细的信息，但如果你的图像背景中有一些物体，它很可能会检测到不需要的物体。所以背景中物体越少效果越好。

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/799c4d7a13bc48cf81b6afc54a2838f3~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

使用场景：希望保留参考图的形状，轮廓会和原图比较接近

提示词：((masterpiece)),((nsanely detailed)), ((HD Quality)),((best quality))((Illustration style)), the back of a girl, the background is the scenery near Oriental Pearl TV Tower in Shanghai

我重绘幅度调的0.75，建筑已经比较接近原图了，用图生图的功能时，重绘幅度越大，AI发挥空间越大。一般0.6-0.75左右会比较接近原图。但是人物衣服的颜色也差距较大。

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/caaf6d4d8a4645d5a50f47490f2b3a62~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

### **Scribble**

涂鸦的目的是从简单的黑白线条画和草图生成图像。用户也可以使用“Canvas”选项创建特定大小的空白画布，用于手动素描（也可以直接上传图像）。如果草图和绘图由白色背景上的黑线组成，则需要选中“Invert Input Color”复选框。

![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/45909cfc27fc49a08afb11c156e27a4b~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image?) 上图能看出来哪个是人工涂色，哪个是AI涂色么？

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/c327568102d342e7ac60f5e64e8ff478~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/e983ba10cac641d7af7c2ecc3e3d8c31~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/c95d97976ed240c6be519ad33df6199f~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

### depth-深度图（重绘幅度0.75）

这个预处理器有助于生成输入图像的深度估计。深度通常用于控制图像内物体的空间定位。浅色区域意味着它离用户更近，而深色区域则离用户更远。

在大图像时它可能会丢失图像内部的细节(面部表情等)。一般会与control\_sd15\_depth模型组合使用。Midas Resolution函数用于增加或减少detectmap中的大小和细节级别。它的级别越高，将使用更多的VRAM，但可以生成更高质量的图像，反之亦然。

说明：保留参考图的空间关系，缺少细节。

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/012a95b1a6184cf1bdb624e7ffc6ee1c~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

包包、衣服的细节变化比较大。

这张图可能效果不太明显，我换一张图，下面是预览效果：（使用depth-midas）

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/52a1695eb49c4e05991b73df04c6b064~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

生成效果如下：（可以看出来深度保留的很好，但是有些细节比如中间那个路的细节丢失了）

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/658d5f89d4284cf18611680c4e4e0085~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

### depth leres-深度图

Depth Leres有与Depth 相同的基本概念，但在地图中包含更广泛的范围。但有时它会从图片中捕获了太多信息，可能会生成与原始图像略有不同的图像。

生成对比图如下：（可以看到高楼细节变化还是很大的，但是图片深度的空间定位保留的很好）

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/6313c3cb369b46518baf4defe5a9ca6f~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

这2种差不多，可以根据不同的图试用两种预处理器，然后决定用哪一种更好。

### normal map一法线图（normal-midas）

法线图使用了三种主要颜色(红、绿、蓝)，通过不同的角度来精确定位物体的粗糙度和光滑程度。它生成法线图的基本估计，可以保留相当多的细节，但可能会产生意想不到的结果，因为法线图完全来自图像，而不是在3D建模软件中构建的。

法线图有利于突出复杂的细节和轮廓，并且在定位对象方面也很有效，特别是在接近度和距离方面。“Normal Background Threshold”用于调整背景成分。设置一个更高的阈值可以移除背景的远处部分(将其混合成紫色)。降低阈值将命令AI保留甚至显示额外的背景元素。

背影图生成效果如下：（变化比较大）

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/37462cbe10ad4867be002895378a1488~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

可能这个controlnet用这张图片不合适，我换一个建筑图试一下。

预览效果：（可以看到丢失了一些轮廓）

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/82c58d9e07924e719f2c9ca6d684d2bb~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

生成效果如下：(背影居然增加了海滩的部分，然后主楼也变了）

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/0849e4925e104eb2a848d23a8ea37f33~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

### openpose-动作姿态图

控制生成人物的动态;这个预处理器生成了一个基本的骨骼火柴人形象。这种技术被广泛采用，因为多个 OpenPose 骨架可以组合成一个图像，这有助于引导稳定扩散生成多个一致的主题。

示例效果：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/d45f0fcd8aea42689efc65ab381c3da7~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

### openpose hand

动作姿态和手部图一控制生成人物的动态和手;

### segmentation一语义分割

分割预处理器检测并将上传的图像分割为同一图像内的段或区域。该模型在生成一组新的图像时，将detectmap图像应用于文本提示。

用不同色块生成对应的物体，背影图效果如下:

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f36794e8e72d4dadab7af29305cbc9a1~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

我再用上面的建筑图试一下：

预览效果：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/2c58b29c419b443b82186caac0522622~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

生成图片：（可以看出来色泽是保留的最好的）

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/c70d8c26494f4cf7ac6370a35e99a32a~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

最后再看一组玩偶我用controlnet生成的效果：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/c4b94ffe404c40919ff98439806f6094~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

## 4、control mode：

用于设置是提示词和controlnet那个比重更高，比如你只希望大概参考controlnet的一些形状，希望出现更多你提示词里面的内容，则可以选择my prompt is more important，一般可以选择balance。

## 5、Resize Mode：

提供了调整ControlNet大小和上传图像的纵横比。

+   Just Resize拉伸:不保留纵横比的情况下，改变ControlNet图像的大小以匹配Txt2Img设置的宽度和高度。这包括拉伸或压缩图像以适应指定的尺寸。

比如我生成的图片设置的512\*512，但是因为我原图是竖版的图片，所以它会自动将原图拉伸后进行匹配再生成。

示例效果：（不推荐使用）

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/73252acb03ed4fb5b1ae3f64b7519a5a~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

+   Crop and resize(裁剪并调整大小):调整ControlNet图像的大小以适应Txt2Image的尺寸。它将调整图像的大小，直到它能够适应Txt2Image设置的宽度和高度。比例不会变。

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/a6b5f47726db468bacf8a0f15a65a743~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

+   Resize and Fill(调整大小并填充):调整Txt2Image的大小以适应ControlNet图像的尺寸。它将调整图像的大小，直到Txt2Image设置可以适合ControlNet图像。

这种不会改变原图比例，且对自动补全左侧原图没有的部分，**推荐使用！**

示例效果：

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/dd214ed0335145529f91e2b18ed4ea92~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.image)

恭喜你，已经阅读结束，希望本篇文章对您有帮助。

后续有空还会继续更新stable diffussion的使用技巧，下节会讲如何生成脸部尽量一致的人物，如何控制人物的动作，欢迎关注或者点赞哦，再次感谢您的阅读。

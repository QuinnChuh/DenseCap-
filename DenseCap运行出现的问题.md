# DenseCap运行时出现的错误

> 具体的DenseCap工程链接：https://github.com/jcjohnson/densecap

因为我的电脑没有GPU，所以，我只下载了训练好的模型进行测试。

### Step

1 . 按照工程要求，我安装了下面的内容： [Torch](http://torch.ch/)， [torch/torch7](https://github.com/torch/torch7), [torch/nn](https://github.com/torch/nn), [torch/nngraph](https://github.com/torch/nngraph), [torch/image](https://github.com/torch/image), [lua-cjson](https://luarocks.org/modules/luarocks/lua-cjson), [qassemoquab/stnbhwd](https://github.com/qassemoquab/stnbhwd), [jcjohnson/torch-rnn](https://github.com/jcjohnson/torch-rnn)

安装上面的东西使用使用下面的命令：

```
luarocks install torch
luarocks install nn
luarocks install image
luarocks install lua-cjson
luarocks install https://raw.githubusercontent.com/qassemoquab/stnbhwd/master/stnbhwd-scm-1.rockspec
luarocks install https://raw.githubusercontent.com/jcjohnson/torch-rnn/master/torch-rnn-scm-1.rockspec
```

工程没有加nngraph，所以我自己也加了下面的命令

```
luarocks install nngraph
```

2 . 后面的GPU的安装需求，我没有去装了。

3 . 然后，我git clone了工程到我的**机械硬盘**上。

4 . 执行了下面的命令下载已经训练好的模型  

```
 sh scripts/download_pretrained_model.sh
```

下载后，它没有不用解压了，直接已经解压好了

5 . 然后我运行测试代码的命令

```
th run_model.lua -input_image imgs/elephant.jpg -gpu -1
```

![微信图片_20180201095610](D:\龙马智芯\Intership\question\imgs\微信图片_20180201095610.jpg)

便出现了上面的问题。

**尝试解决：**

我自己又去网络上找了一张图，并把它保存为png格式，图片放在同样的目录下，并起名为elephant.png。运行了下面的代码：

```
th run_model.lua -input_image imgs/elephant.png -gpu -1
```

出现了下面的错误

![微信图片_20180201095613](D:\龙马智芯\Intership\question\imgs\微信图片_20180201095613.jpg)

不知道问题在哪里？重装过libpng，但还是一样的效果，请老师看看是什么问题。
模式	| 描述
---|---
|r |	以只读方式打开文件。文件的指针将会放在文件的开头。这是默认模式。|
rb |	以二进制格式打开一个文件用于只读。文件指针将会放在文件的开头。
r+ |	打开一个文件用于读写。文件指针将会放在文件的开头。
rb+ |	以二进制格式打开一个文件用于读写。文件指针将会放在文件的开头。
w |	打开一个文件只用于写入。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。
wb |	以二进制格式打开一个文件只用于写入。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。
w+ |	打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。
wb+ |	以二进制格式打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。
a |	打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。
ab |	以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。
a+ |	打开一个文件用于读写。如果该文件已存在，文件指针将会放在文件的结尾。文件打开时会是追加模式。如果该文件不存在，创建新文件用于读写。
ab+ |	以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。如果该文件不存在，创建新文件用于读写。

下图很好的总结了这几种模式：

![](file-mode.png)

模式|	r|r+|	w	|w+	|a	|a+
---|---|---|---|---|---|---
读|	+|	+|	|	+|	|	+
写|	|	+	|+|	+|	+|	+
创建|	|	|	+|	+|	+|	+
覆盖|	|	|	+|	+|
指针在开始	|+|	+|	+|	+|
指针在结尾	|	|	|	|	|+|	+


w, r, wt, rt 都是 python 里面文件操作的模式。

w 是写模式，r 是读模式。

t 是 windows 平台特有的所谓 text mode(文本模式）,区别在于会自动识别 windows 平台的换行符。

类 Unix 平台的换行符是 \n，而 windows 平台用的是 \r\n 两个 ASCII 字符来表示换行，python 内部采用的是 \n 来表示换行符。

rt 模式下，python 在读取文本时会自动把 \r\n 转换成 \n。

wt 模式下，Python 写文件时会用 \r\n 来表示换行。
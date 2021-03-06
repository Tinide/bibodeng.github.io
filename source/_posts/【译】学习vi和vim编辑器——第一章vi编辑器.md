---
title: 【译】学习vi和vim编辑器——第一章vi编辑器
date: 2012-09-07 12:16:37
---
{% raw %}
<div><h2>第一部分 &nbsp;vi基础以及高级技巧</h2>
</div>
<div class="part_head">
<div>第一部分是为你快速上手vi编辑器而设置的，并且提供令你工作效率倍增的高级技巧。这些章节涵盖了vi源起，核心vi，并提供在任何版本可用的vi命令。后面的章节介绍流行的vi克隆版本。本部分包括下面的章节：</div>
<div>&nbsp;</div>
<div>第一章， vi 编辑器</div>
<div>第二章，简单编辑</div>
<div>第三章，快速移动</div>
<div>第四章，基础之外</div>
<div>第五章，ex编辑器介绍</div>
<div>第六章，全局替换</div>
<div>第七章，高级编辑技巧</div>
<div>第八章，vi的克隆版本</div>
<div>&nbsp;</div>
</div>
<div><h3>第一章 &nbsp; &nbsp;vi 编辑器</h3>
</div>
<div>&nbsp;</div>
<div>unix中有许多的编辑器可以处理文本内容，无论这些文件包含数据，源代码，还是句子。有些是行编辑器，例如ed和ex编辑器，它们显示一行的文件内容到屏幕上；有些是屏幕编辑器，例如vi和emacs，可以再你的终端屏幕上显示一部分文件内容。基于X Window系统的编辑器也普遍可用，并且变得愈发流行起来。GNU emacs和它的衍生物XEmacs，提供多个X 窗口。两个很有趣的选择是来自贝尔实验室的sam 和 Acme 编辑器。Vim也提供基于X Window的界面。</div>
<div><br />
</div>
<div>vi是你系统上最有用的文档标准编辑器之一。（vi是visual editor的缩写，发音为vee-eye,见图1-1.）不像Emacs,vi在unix系统上是几乎完全相同的形式出现，因此提供了许多文字编辑语言。你也许会说ed和ex也一样，但是屏幕编辑器一般来讲更加易用。（其实行编辑器几乎没人在用了。）有了一个屏幕编辑器，你可以上下滚动页面，移动光标删除行，插入字符等等许多操作，同时也可以立即可见结果。屏幕编辑器非常地受欢迎，因为它们允许你浏览和修改文件内容，假如你想编辑一个打印页，你会非常迅速完成任务。</div>
<div><br />
</div>
<div>许多新人，vi用起来很直观但笨拙，而不是用特殊的控制键来完成字处理且一直在正常地打字，它几乎使用了所有的常规按键来组织命令。当键盘用作组成命令时，vi就进入了命令模式。你必须要在插入模式中才能打出文字到文档中。另外，vi其实有很多的命令，多乎哉不多也（哇咔咔偷笑）</div>
<div><br />
</div>
<div>图1-1 [待整理]</div>
<div><br />
</div>
<div>只要你一开始学习，你就会认识到vi是一个设计优良的编辑器。你可以只用几个按键就可以让vi完成复杂的任务。你学习vi，就是学习完成各种工作的快捷键，它们传达给vi完成各种计算。vi不是一个所见即所得的编辑器，如果你想写出格式化文档，你必须敲出控制其他程序显示方式的输出格式的代码。如果你想要段落缩进，比如说，你放了一段代码在缩进的起始和终止处。格式化代码允许你测试或者修改打印的样式，并且从许多方面来讲，它给你许多控制文本表现方式的自由。unix支持troff格式的包，the TeX和Latex格式非常流行，也是可选的。vi 支持一些简单的格式化机制，例如，当到达行尾的时候，你可以让它自动缠绕。或者自动缩进。此外vim7提供自动拼写检查。</div>
<div><br />
</div>
<div>就像所有的技巧一样，练得越多，基础就变得越简单了，熟能生巧嘛。当你掌握了强大的vi力量的时候，你就很难回到那些“简单”的编辑器了。</div>
<div><br />
</div>
<div>什么才是编辑器的组成部件呢？首先，你可以插入文本；其次可以删除文本，当然也不需能修改文本。你或许会想将文本从一处移向另外一处。有时，你也会想要将文本复制然后黏贴到各个地方。不像许多其他字处理软件，vi的命令模式才是常规模式。往复杂地说，交互式的编辑器可以用几个键就能进行。你可以敲进几个非常简单的“插入”命令，然后继续打字。</div>
<div><br />
</div>
<div>一个或者两个字符被用来作为基本的插入命令，例如：</div>
<blockquote>
<div>i &nbsp;插入</div>
<div>cw &nbsp;编辑单词</div>
<div><br />
</div>
</blockquote>
<div>把字母当命令来用，你可以快速地编辑文件了。你不用去记住一大堆的功能键或者把你的手指移动到处寻找组合键了。当然你也可以再也不用鼠标了，你完全可以手不离开键盘了（很酷吧），也不用去摆弄一些菜单了。很多的命令都可以轻松地记住，几乎所有的命令都用简单的模式并且相互关联。</div>
<div><br />
</div>
<div>一般来说，vi命令：</div>
<blockquote>
<div>1、 大小写敏感 大写和小写是不同的例如 G和g是不同的</div>
<div>2、不会被输出，也就是说你看不到你输入的命令</div>
<div>3、不用在命令结束按下enter键，因为当你按下的时候，它已经起作用了</div>
<div><br />
</div>
</blockquote>
<div>当然也有一组的命令用来在屏幕底部输入。底部命令以不同的标号开头。斜杠号“/”和问号“?”是查找命令的开头，我们将会在第三章详细讨论。一个冒号“:”是所有的ex命令的开头。ex命令是用来进行ex行编辑的命令。当你使用vi的时候，ex命令是可用的，因为ex是vi的底层，只不过vi是ex的可视化形式而已。ex命令和概念会在第五章讨论，但是本章介绍一个退出编辑文件的命令":q"。</div>
<div><br />
</div>
<div class="small_title">【一个历史的透视】</div>
<div><br />
</div>
<div>在进入vi的世界之前，需要了解你的环境这样会帮助你理解vi的世界观。特别是能让你理解vi，而不是得到一些莫名其妙的错误，当然也能了解vi的克隆版本在vi之上的改进。</div>
<div><br />
</div>
<div>vi的历史应该追溯到程序员们在计算机终端上工作时，好几百个不同的终端在同时使用。每个终端都做同样的事情（清屏，移动鼠标等等），但是完成这些操作的命令却是不同的。除此之外，unix系统让你可以选择一些字符作为退格键，然后产生一个中断信号，还有其他的命令在终端非常有用，就像那些吊起或者恢复输出。这些在stty（终端）努力的举措仍然在继续。</div>
<div><br />
</div>
<div>原始的UCB版本的vi将终端的控制信息抽象出来，将它们从代码变成一个终端文本文件类型的数据库。这个数据库由termcap管理着。在1980年代系统V推荐了一个二进制终端信息数据库以及终端信息库。两个库很大程度上在功能上是等价的。为了告诉vi编辑器哪个是你的终端，你需要设置好TERM环境变量。这类工作一般在shell启动文件中已经完成了，例如.profile或者.login就是这类文件。</div>
<div><br />
</div>
<div>如今，每个人都使用图形界面下的终端模拟器（例如xterm）。系统很可能在设置TERM的时候照顾你。（你依然可以在没有图形界面的终端使用vi，当然这在单用户环境下做系统恢复工作时很有用，当然也没有人想在这样的环境下使用它）。在日常的使用中，你很大可能会选用一个图形界面vi 编辑器，例如vim编辑器或者其他拷贝版本。在windows或者mac系统中，图形界面的vi是默认的，然而，当使用图形终端模拟器的时候，还是会使TERM和termcap或者terminfo的信息且同样和stty设置密切相关。使用时，相比其他环境，vi运行在终端模拟器提供了一条比较省力的路径。</div>
<div><br />
</div>
<div>另一个需要知道的事实是vi是在unix系统被认为还不如今天这样稳定的时候。过去的vi用户要随时防备计算机突然崩溃。所以vi编辑器包含了恢复所编辑文件的支持，如果编辑中间发生了错误导致停机了，则可以恢复。因而当你学习vi编辑器的时候，如果出现了问题，记住这个历史记录的工具。</div>
<div><br />
</div>
<div class="small_title">【打开和关闭文件】</div>
<div><br />
</div>
<div>你可以用vi来编辑任何文本文件，vi把待编辑文件拷贝到一个缓冲区（一片内存空间），然后显示该缓冲区到屏幕上（这也是为啥你只能每次看到一屏的缘由）。然后你可以 增、删、查、改。当你保存文件的时候，vi把缓冲区的内容拷贝到一个临时文件中，并且以原文件的名称替换之前的文件。记住你永远在编辑一份源文件的拷贝，你的编辑不会改变原文件，直到你保存修改为止。保存也叫做“保存缓冲区”或者更通俗地讲“保存文件”。</div>
<div><br />
</div>
<div class="small_title">【打开文件】</div>
<div><br />
</div>
<blockquote>
<div>$vi [filename]</div>
<div><br />
</div>
</blockquote>
<div>上面这条命令在unix系统中，是调用了vi编辑器，然后可以编辑原有文件或者新建一个文件。语法如上所示。</div>
<div>中括号表明filename是可选的，中括号本身不用敲出来。美元符号是unix系统的命令提示符，举一个例子：</div>
<div>打开一个叫做test.txt的文件</div>
<div><br />
</div>
<blockquote>
<div>$vi test.txt 立马可以打开test.txt文件</div>
<div><br />
</div>
<div>$vi newfile.txt 生成一个新文件，名字叫做newfile.txt</div>
<div><br />
</div>
</blockquote>
<div>也可以什么都不写，直接$vi进入编辑器，编辑完后，可以为文件命名。现在，让我们用命令行来为文件命名。</div>
<div><br />
</div>
<div>一个文件名必须要是在该目录下唯一的，一个文件名可以包括任何字符除了斜杠（/），因为斜杠是保留字符，被用来作为路径的分界符。在ASC2 NUL,是所有位全为0的字符。你甚至可以在文件名中包含空格，只要打一个反斜杠“\”在空格前就可以了。在练习中，文件名可由大小写字母、数字、下划线、点符号随意组合而成。请记住unix是大小写敏感的：大写和小学字母是不同的。另外，你还要按下 【Enter】键告诉Unix你完成$vi [filename]的命令。</div>
<div><br />
</div>
<div>当你想要打开一个目录下的某个新文件时，通过vi命令给你的文件一个新名字，这样就生成了一个新的文本文件了。例如，如果你想创建一个叫做 practice的文件，那么只需：</div>
<blockquote>
<div>$vi practice&nbsp;</div>
</blockquote>
<div>因为这是一个新文件，缓冲区是空的，所以屏幕显示如下：</div>
<blockquote>
<div>~</div>
<div>~</div>
<div>~</div>
<div>~</div>
<div>"practice" &nbsp;[New file]</div>
<div><br />
</div>
</blockquote>
<div>每一行前面的波浪号表示改行没有任何文本，甚至连空格都没有。最下面的提示行，或者说是状态行，会显示文件的名称和当前状态，现在可看到该文件是一个新创立的文件。</div>
<div><br />
</div>
<div>你可以编辑任何当前目录下存在的文件，只需要输入其文件名。假设unix下有一个文件的路径名是/home/john/letter 如果你在/home/john目录下</div>
<div>那么直接使用相对路径，如下：</div>
<blockquote>
<div>$vi letter</div>
</blockquote>
<div>将会产生一份拷贝，并显示到屏幕上。</div>
<div>如果你在别的目录下，那么只需要给出全路径名就可以开始编辑了：</div>
<blockquote>
<div>$vi /home/john/letter</div>
</blockquote>
<div class="small_title">【打开文件可能碰到的问题】</div>
<div>*当你调用vi，消息[open mod]将会显示出来。</div>
<div>你的终端没有正确的鉴定，立刻用:q命令退出编辑会话。检查你的环境变量$TERM。它应该设置成为你的终端名称。或者叫你的系统管理员提供可行的终端类型设置。</div>
<div><br />
</div>
<div>*你看到了如下的任何一条信息：</div>
<div><br />
</div>
<blockquote>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>Visual needs addressable cursor or upline capability</div>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>Bad termcap entry</div>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>Termcap entry too long</div>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>terminal: Unknow terminal type</div>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>Block device required</div>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>Not a typewriter</div>
</blockquote>
<div>你的终端要么未定义，或者你的terminfo或termcap入口出了什么问题。按下 :q命令退出。检查你的$TERM环境变量，或者问你的管理员为你提供一个终端环境。</div>
<div><br />
</div>
<div>*一个[New file]信息显示，但你认为这是一个早已存在的文件</div>
<div>首先检查你的文件名拼写和大小写是否有误，如果没有，那么看看你是否进错了目录。按下:q命令退出。然后检查你是否在正确的目录下，如果你在正确的目录下，检查你的文件列表（使用ls命令）看看是否有存在不易察觉的文件名相似。</div>
<div><br />
</div>
<div>*你调用了vi，但是你看到的是一个冒号，意味着你正在ex行编辑器模式下</div>
<div>你可能是在vi命令前面打了一个中断，在vi绘制屏幕之前发生了。没关系，在ex的提示后面(:)按下vi命令。</div>
<div><br />
</div>
<div>*如果看到了下面的信息：</div>
<blockquote>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>[read only]</div>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>File is read only</div>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>Permission denied</div>
</blockquote>
<div>read only意味着你只能浏览文件，而不能编辑。你不能保存任何的修改到文件中，你可能用vi的view模式打开文件（vi -R）,或者你没有写该文件的权限。查看第十页的“保存文件的错误”一节。</div>
<div><br />
</div>
<div>*出现如下信息：</div>
<blockquote>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>Bad file number</div>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>Block special file</div>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>Character specail file</div>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>Directory</div>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>Executable</div>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>Non-ascii file</div>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>file non-ASCII</div>
</blockquote>
<div>你所调用编辑的文件不是一个常规的文本文件，退出编辑（ 用命令:q! ），然后检查你要编辑的文件，可以使用file命令。</div>
<div><br />
</div>
<div>*当你打:q命令想要退出的时候，下面的信息出现了：</div>
<blockquote>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>No write since last change (:quit! overrides).</div>
</blockquote>
<div>你可能不经意间修改了文件，按下:q!离开编辑，你的修改将不会保存到文件。</div>
<div><br />
</div>
<div class="small_title">【模式手法】</div>
<div>之前提过，当前模式就是vi工作的基本原理。vi有两个状态，命令模式和插入模式。你一开始进入vi的时候是命令模式，任何一个键都是命令。在插入模式，你敲打的任何字符都会插入到你的文件里。</div>
<div><br />
</div>
<div>通常，你可以立即进入插入模式，或者离开插入模式。在其他情况下，你按下的键使得你的文件修改了，并且这种修改时你不想要的。</div>
<div><br />
</div>
<div>按下 ESC 键可以强制vi从插入模式退出到命令模式，如果你早已在命令模式下，那么如果你按下ESC,可以听到系统发出的beep声音。这也是为什么命令模式被叫做 beep模式。</div>
<div><br />
</div>
<div>当你安全到达命令模式的时候，你可以修复一些意外的修改，然后继续你的编辑。</div>
<div><br />
</div>
<div class="small_title">【保存后退出文件】</div>
<div>你可以随时退出你的作业，保存你的文件，然后返回到unix的命令行。vi编辑器的保存并退出命令是ZZ,两个Z都是大写的。</div>
<div><br />
</div>
<div>让我们假设你创建了一个叫做practice的文件，然后你在里面输入了6行。要保存文件，首先要确保你在命令模式下，如果不是，按下ESC键回到命令模式。然后输入ZZ命令。</div>
<div><br />
</div>
<div>图</div>
<div><br />
</div>
<div>你也可以用ex的命令，输入:w可以保存文件，但是还没退出，输入:q可以直接退出。输入:wq可以保存后退出。（:wq等价于ZZ）我们将会在后面第五章详细讲解怎样使用ex命令，现在，你只需要记住几个保存文件的命令就可以了。</div>
<div><br />
</div>
<div><br />
</div>
<div class="small_title">【不保存直接退出】</div>
<div>当你初次学习vi编辑器，特别是如果你初生牛犊不怕虎，有两个非常趁手的ex命令，可以让你免受各种乱七八糟的修改（当然这是你做的）。如果你想要擦掉所有的编辑，不保存你做的任何修改的话，下面的命令：</div>
<blockquote>
<div>:e! ENTER键</div>
</blockquote>
<div>将你带回最后一次保存的状态，然后你可以重新开始</div>
<div><br />
</div>
<div>如果你只是想要回到最初始的状态，那么直接退出不保存就行了：</div>
<blockquote>
<div>:q! &nbsp;ENTER键 强制退出</div>
</blockquote>
<div>退出后将回到unix的命令提示，用了这些命令，你就可以忽略在buffer中的修改，回到你最后一次保存的状态。vi一般不会让你丢失修改，但是这两个命令可以让你突破禁令，尽管缓冲区被修改了。</div>
<div><br />
</div>
<div class="small_title">【保存文件存在的问题】</div>
<div><br />
</div>
<div>* 你试图写文件，但是你得到下面的消息：</div>
<blockquote>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>File exists</div>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>File file exists -use w!</div>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>[Existing file]</div>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>File is read only</div>
</blockquote>
<div>输入:w! 文件名 可以覆盖已存在文件，或者可以:w 新文件名 把文件内容保存到一个新的文件中。</div>
<div><br />
</div>
<div>* 你想写文件，但是你没有写的权限。你会得到这类的信息“Permission denied.”</div>
<div><br />
</div>
<div>用:w 新文件名 把内容写入到一个新文件中，如果你有该目录的写权限，那么可以用mv命令将原有文件移除，然后用你的文件覆盖原文件。如果你没有该目录的写权限，那么使用:w 路径名/文件名 将你的文件写入到你有写权限的文件中去（例如你的home目录，或者根目录下的/tmp目录）。</div>
<div><br />
</div>
<div>* 你试图写文件，但系统提示你文件系统已满。</div>
<div><br />
</div>
<div>可以输入 :!rm 垃圾文件名 来删除不需要的垃圾文件以腾出空间（以!开头的ex命令表示让终端命令行执行一个unix/linux命令，在vi中输入:!ls和在unix终端输入 ls的效果是一样的）。 或者，你可以输入 :!df 来看看别的文件系统有没有剩余的可用空间。如果有，那么恭喜你，可用选择一个目录把你的文件写入到文件中:w 路径名 （df是unix系统上查看磁盘空余空间的命令 df = Disk's Free space）。</div>
<div><br />
</div>
<div>* 系统把你置于开放模式下，并告诉你文件系统满了</div>
<div><br />
</div>
<div>可能vi编辑下的目录所在的磁盘已经满了，输入:!ls /tmp 看看临时空间里有什么可以删除的以获取空间。如果有，创建一个临时的unix shell，然后输入一些命令完成文件的组织工作。你可以用:sh命令来创建一个shell，按下 CTRL+D 或者输入 exit 来退出shell回到vi编辑器中。（在现代unix操作系统中，你可以使用工作控制shell，简单地按下CTRL+Z就可以挂起vi编辑器的进程，然后回到unix的提示命令行。输入fg返回vi）当你释放了一些空间的时候，使用:w!命令写入文件。</div>
<div><br />
</div>
<div>* 你试图写文件，但是你发现磁盘共享已经被锁了</div>
<div><br />
</div>
<div>用ex的:pre命令（:preserve的缩写）强制你的系统保存你的文件，如果无效，那么移除一些文件，如果你正在使用一个作业控制器，使用:sh 或者 CTRL+Z，进入shell移除一些文件，按下CTRL+D（或者fg）来返回vi编辑器。然后用:w!写文件 。</div>
<div><br />
</div>
<div class="small_title">【练习】</div>
<div><br />
</div>
<div>学习vi的唯一方法就是练习，你现在应该明白了怎样创建一个新文件然后回到unix提示命令行。创建一个叫做practice的文件，插入一些文字，然后保存然后退出编辑。</div>
<div><br />
</div>
<blockquote>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>打开一个叫做practice的文件 &nbsp; &nbsp; &nbsp; &nbsp;vi practice</div>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>插入文本 <span class="Apple-tab-span" style="white-space:pre;">			&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span>按下&nbsp;i &nbsp;然后输入你想插入的文本</div>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>返回到命令模式 <span class="Apple-tab-span" style="white-space:pre;">			&nbsp;&nbsp;&nbsp;&nbsp;</span>ESC键</div>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span>退出vi，保存文件<span class="Apple-tab-span" style="white-space:pre;">		&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span>ZZ</div>
<div><span class="Apple-tab-span" style="white-space:pre;">	</span></div>
</blockquote>
<div>translated by bibodeng 《learning the vi and vim editors》 &nbsp; 2012-09-07 &nbsp; <span style="color:#e53333;">有误之处还请多指教讨论</span></div>
<div><br />
</div>
<style type="text/css">
body{
font-size: 14px;
}

h3{
background-color:#000000;
color:#FFFFFF;
padding: 10px;
}

blockquote{
background-color:#CCFF99;
-webkit-border-radius: 5px;
}

.part_head{
background-color:rgba(0,0,0,0.2);
padding: 10px;
-webkit-border-radius: 5px;
}

.example{
background-color:#CCCCCC;
font-size:1.2em;
-webkit-border-radius: 5px;
}

.small_title{
font:bold;
font-size: 1.5em;
padding: 5px;
}
</style>{% endraw %}

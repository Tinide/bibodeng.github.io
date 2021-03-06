---
title: 【译】学习vi和vim编辑器第二章——简单编辑
date: 2012-09-22 07:20:58
---
{% raw %}
<h3>第二章 简单编辑操作</h3>
<div name="perface">
<p>本章将会向你介绍使用vi来进行编辑，本章被当做是初级教程。在本章你将会学习怎样移动光标，还有怎样做简单的编辑工作。如果你从来没有使用过vi编辑器，那么你应该阅读整章内容。</p>
<p>后续的章节将会带领你拓展你的技能，来更加快速更加高效地完成你的编辑工作。其中最大的优点就是对熟手来说，那就是你可以有很多选项可用。（其中对菜鸟来说最大的好处就是vi真的太TMD多命令了。）</p>
<p>你不能单纯靠记忆单个vi命令来学习vi编辑器，可以考虑从本章介绍的基本命令开始学起。记住一点，这些命令的使用模式都是一样的。</p>
<p>当你学习vi的时候，将你能做的工作更多地代理给编辑器来做，然后找到能够完成该任务的命令。在后面的章节，你将会学习更多高级的特性，但是在你掌握高级技巧之前，先把简单的掌握好！行吗？</p>
<p>本章将会覆盖：</p>
<blockquote>
<ul>
<li><a href="/admin/#moveMouse">移动光标</a></li>
<li><a href="/admin/#changeText">添加或者修改文本</a></li>
<li><a href="/admin/#deleteAndCopy">删除、移动、复制文本</a></li>
<li><a href="/admin/#moreInsertion">更多进入插入模式的方法</a></li>
</ul>
</blockquote>
<p></p>
</div>
<h3 name="main_content">vi命令</h3>
<p name="main_content">vi有两种模式：命令模式和插入模式。当你用vi进入一个文件的时候，你所处的是命令模式，此时编辑器正在等待着你输入命令。一些命令可以让你移动到文件的任何位置，可以进行编辑，可以进入编辑模式来添加新文本。也可以使用退出编辑文件回到unix的命令（保存或者丢弃修改都可以）。</p>
<p name="main_content">你可以假设这两种不同的模式代表着不同的键盘，在插入模式，你的键盘的功能就像一个打字机，打出你想要的内容，而在命令模式，每个键都是有命令的含义，可以指示编辑器做什么。</p>
<p name="main_content">你有许多的方法告诉vi编辑器你想进入插入模式，其中一种最常见的就是按下 <strong>i</strong> 这个键.i不会出现在屏幕上，但是你按下了之后，接下来按下的任何按键将会出现在屏幕中，并且会被存储到内存缓冲区内。光标表示当前的所在位置。当你想退出插入模式的时候，按下ESC键，回到命令模式。按下ESC键光标会退后一格，所以你将看到光标在你输入的最后一个字符上面。</p>
<p name="main_content">例如，假设你新建了一个文件，并且想要输入"introduction"，如果你按下的按键顺序是这样的<strong>iintroduction</strong>，那么你的屏幕中将会看到这样的结果： </p>
<blockquote name="main_content">
<p>introduction</p>
</blockquote>
<div name="main_content">当你新建了一个文件，vi处在命令模式下，第一个i是进入到插入模式的命令,而后续的所有按键都是要输入文件的内容，因为你进入了插入模式，直到你按下ESC键离开插入模式。当你输入错误的时候，退格删除，然后重新输入。退格的作用要取决于你使用的终端类型，有的是直接删除你的输入内容，有的是直接退格而不删除内容。记住，你不能用<strong>backspace</strong>键来退格到你进入插入模式之前的位置，但是如果你取消了vi的配置，Vim允许你退格到进入插入模式前的位置。 </div>
<p name="main_content"></p>
<p name="main_content">vi有一个选项可以设置一个右边距离，然后一行到达一定长度会自动换行，但是现在，你可以使用<strong>ENTER</strong>键来换到下一行。</p>
<p name="main_content">有时候你不知道是在插入模式还是在命令模式，当vi的反应不像你所预期的那样，那么按下<strong>ESC</strong>键一次或者两次来检查你所处的模式。当你听到beep声，那么已经在命令模式下了。</p>
<h3 id="moveMouse" name="main_content">移动光标</h3>
<p name="main_content">你可能只需要一丁点的时间来在插入模式插入新文本，但是将会花多一点时间在修改已有文本上。</p>
<p name="main_content">在命令模式下，你可以将光标移动到任何你想要的位置，当你开始编辑时，你总是想把光标放到相应的位置，无论你进行的是什么操作（修改、删除、还是复制），你都想要尽可能飞快地到达你想要操作的位置。</p>
<p name="main_content">下面是一些移动光标的命令： </p>
<blockquote name="main_content">
<ul>
<li>上下左右，一次一个字符距离</li>
<li>字符块为单位向前或者向后，例如单词，句子，或者段落</li>
<li>在文件前移或后移，一次一个屏幕空间</li>
</ul>
</blockquote>
<div name="main_content">在图表2-1中，一个下划线表示光标当前所在的位置，圆圈告诉你各种命令所达到的目标位置。 </div>
<p align="center" name="main_content"><a href="/content/plugins/kl_album/upload/201209/8eeef6358dfee764853d3e23ede496522012092123201719468.png" target="_blank"><img border="0" alt="点击查看原图" src="/content/plugins/kl_album/upload/201209/8eeef6358dfee764853d3e23ede496522012092123201719468.png" width="480" height="166" /></a></p>
<blockquote name="main_content"></blockquote>
<div name="main_content">图表2-1 简单移动命令 </div>
<p name="main_content"></p>
<h4 name="main_content">简单移动</h4>
<p name="main_content">按键h,j,k和l，这些刚刚好在你手指下面的按键，可以移动光标：</p>
<blockquote name="main_content">h 左移一格<br />
j 下移一行<br />
k 上移一行<br />
l 右移一格<br />
</blockquote>
<div name="main_content">你可以使用方向键（←↓↑→）控制上下左右，还有+和-来上移下移。或者使用ENTER和BACKSPACE键，但是它们是有特殊作用的。刚开始，你会觉得它们看起来很笨拙，用字母按键来代替鼠标光标移动。但是之后你会发现这将是你最喜欢的vi的特性之一,那是因为你可以不用离开键盘中心就可以随意移动（省力）。<br />
在你移动光标之前，先按下ESC键以确保你在命令模式下，用h,j,k,l按键来向前向后移动当前光标所在的位置。当你可以在一个方向上快速飞奔的时候，你将会听到一个beep声，因为你到了文本的边界，此时光标也不动了。当你在一行的头部或者尾部的时候，你不能再用h或者l来前后移动到前一行或者下一行，你必须要用j和k按键。你不能将光标移到没有文档字符的地方，比如有"~"标号的行（表示没有任何字符），当然也不能移动光标到第一行更顶的位置。 </div>
<p name="main_content"></p>
<h4 name="main_content">带数字参数的移动</h4>
<p name="main_content">你可以优化移动命令，方法是使用数字。图表2-2展示了命令<strong>4l</strong>怎样移动光标到右边第四个空格处的，就像你按下了4次的l命令（llll）。</p>
<p name="main_content">&nbsp;</p>
<p align="center" name="main_content"><a href="/content/plugins/kl_album/upload/201209/dd8e723edf5d5e15c64c0a1d9754cb9a201209212320175942.png" target="_blank"><img border="0" alt="点击查看原图" src="/content/plugins/kl_album/upload/201209/dd8e723edf5d5e15c64c0a1d9754cb9a201209212320175942.png" width="480" height="91" /></a></p>
<!-- 图表2-2 --><p name="main_content">多次命令可以让你有更多的选择以及效率来发挥你学习到的命令的作用。记住它，当你学到更多命令的时候，你将受益无穷。</p>
<h4 name="main_content">行内移动</h4>
<p name="main_content">当你保存了practice文件，vi将会告诉你该文件有多少行。一行未必和屏幕上显示的行一样长（通常限制为80个字符），一行结束是以ENTER键换行来结束的。如果你在按下ENTER键之前输入了200个字符的内容，vi将视这200个字符为一行（虽然可能会被分作很多行来显示在屏幕上）。也就是说，一行是以行结束标志来决定其长度的。</p>
<p name="main_content">我们前面第一章的时候提到过，我们可以设置右边距离，vi将会自动在距离右边界一定距离的地方插入一个换行，这个距离（right margin）是可以设置的。选项wrapmargin（简写是wm），你可以用下面的命令来设置wrapmargin:</p>
<blockquote name="main_content">:set wm=10 </blockquote>
<div name="main_content">本命令不会影响你早已经输入的行，而只会影响你将来要输入的行。我们将会在第七章选项设置深入讨论。<br />
如果你不用vi的自动wrapmargin换行的话，你应该用换行来控制一行文本的长短。<br />
<br />
这里有两个非常有用的命令，让你在行内移动游刃有余：<br />
</div>
<blockquote name="main_content">0 (零) 移动到所在行的开头<br />
$ (美刀符号) 移动到所在行的尾部<br />
</blockquote>
<div name="main_content">在下面的例子中，行号是已经显示出来了（行号显示可以用vi的number选项来控制，输入“:set nu”命令就可以了，这个也将在第七章讲解）。</div>
<p align="center" name="main_content"><a href="/content/plugins/kl_album/upload/201209/7d5f0e89be4e507a1197261d93c5d388201209212320201591.png" target="_blank"><img border="0" alt="点击查看原图" src="/content/plugins/kl_album/upload/201209/7d5f0e89be4e507a1197261d93c5d388201209212320201591.png" width="480" height="90" /></a></p>
<div name="main_content"><br />
</div>
<div name="main_content">逻辑行的第3行，即可见行第5行没有和上面的对齐。如果光标在单纯delete的d位置，当你按下$命令的时候，你的光标将会移动到逻辑行尾部，也就是下面的them单词。如果你按下0命令，那么你将回到第二行的开头，也就是字母move的m字母。<br />
</div>
<h4 name="main_content">字符块间移动</h4>
<div align="center" name="main_content">你可以一整块一整块字符地跳跃，单词，句子，段落等。w命令可以一次前移一个单词的位置，计数器可以计入标点符号或者不计入，下面的行演示光标是怎样移动的：<br />
&nbsp;</div>
<p align="center" name="main_content"><a href="/content/plugins/kl_album/upload/201209/bb9ed57f3e0461af2516328af4c71980201209212320216052.png" target="_blank"><img border="0" alt="点击查看原图" src="/content/plugins/kl_album/upload/201209/bb9ed57f3e0461af2516328af4c71980201209212320216052.png" width="320" height="41" /></a></p>
<div name="main_content">你可以一个单词一个单词地移动，不计入标点符号和间隔，只需要将命令改为大写的W。那么光标使用W来移动就和上图的第二行一样。</div>
<p align="center" name="main_content"><a href="/content/plugins/kl_album/upload/201209/c8b426cebaaa989aeed5871b5a0d74a22012092123202214677.png" target="_blank"><img border="0" alt="点击查看原图" src="/content/plugins/kl_album/upload/201209/c8b426cebaaa989aeed5871b5a0d74a22012092123202214677.png" width="288" height="28" /></a></p>
<div name="main_content"><br />
要往回整个单词间隔地移动，那么就使用<strong>b</strong>命令,每次后移一个单词距离。大写的<strong>B</strong>命令可以让你不计标点和间隔地移动一个单词的间隔。<br />
我们前面提到，移动命令是可以接受数字参数的，所以，无论是w命令还是b命令，都可以让你的移动间隔加倍。2w让你向前移动2个单词，5B让你后移动5个单词，且标点符号不计入内(标点符号不计做单词)。</div>
<div name="main_content"><br />
要移动到一个特定的行，你可以使用G命令，G命令将会移到文件的末尾，1G将移动到文件的第一行，42G将会到达第42行。我们将会在后面一节“G命令”里面详细讨论。</div>
<p align="center" name="main_content"><a href="/content/plugins/kl_album/upload/201209/f349c015f6d47d17c2ffafe7ee6f3c0d2012092123201921481.png" target="_blank"><img border="0" alt="点击查看原图" src="/content/plugins/kl_album/upload/201209/f349c015f6d47d17c2ffafe7ee6f3c0d2012092123201921481.png" width="480" height="252" /></a></p>
<div name="main_content"><br />
&nbsp;</div>
<div name="main_content">我们将会在第三章讨论以句子为间隔的移动，但现在，用你知道的命令来移动光标，把他们和数字参数结合起来，加倍移动。 </div>
<p name="main_content"></p>
<h3 name="main_content">简单编辑</h3>
<p name="main_content">当我们输入文本到你的文件中，一切都是那么完美。但是你会发现当你打印错误或者想要优化你的短语，或者当你的程序有一个bug的时候。当你输入字符的时候，你很有可能要修改它们，删除，或者移动，甚至复制。图2-3就向你展示了一些对文本的修改。修改是用文本纠错标记的。</p>
<p name="main_content">在vi中你可以完成上图所示的编辑任务，仅仅需要一些简单的按键命令:i 插入，a可以在光标后面追加文本，c 可以更改文本，d删除。要移动或者拷贝文本，你可能需要一些组合命令，你可以用d 删除来移除文本，然后用p命令来放到需要的地方（粘贴）。你可以单纯地拷贝文本，用y命令(yank)，然后用p来(put)。每个编辑都将会在本章进行描述。图表2-4将会展示完成图表2-3所示修改的vi命令。</p>
<h4 name="main_content">插入文本</h4>
<div name="main_content">你早就在前面看到过插入命令了，用来插入文本到新文件中。你也可以在编辑现存的文本时添加忘掉的字符、单词、句子时使用插入命令。在practice文件中，假设你有下面的句子： </div>
<blockquote name="main_content">you can scroll<br />
the page, move the cursor, delete<br />
lines, and insert characters. </blockquote>
<p align="center" name="main_content"><a href="/content/plugins/kl_album/upload/201209/c78566f6b8fe90e7a7d828ca15516a962012092123202027477.png" target="_blank"><img border="0" alt="点击查看原图" src="/content/plugins/kl_album/upload/201209/c78566f6b8fe90e7a7d828ca15516a962012092123202027477.png" width="480" height="222" /></a></p>
<p name="main_content">由当前光标所示的位置，来编辑句子。输入下面的命令:</p>
<p align="center" name="main_content"><a href="/content/plugins/kl_album/upload/201209/26db770248a3c1e11b45b42ff61ea7162012092123202332618.png" target="_blank"><img border="0" alt="点击查看原图" src="/content/plugins/kl_album/upload/201209/26db770248a3c1e11b45b42ff61ea7162012092123202332618.png" width="480" height="200" /></a></p>
<h4 name="main_content">追加文本</h4>
<p name="main_content">a, 你可以在任何地方的后面追加文本，只需要一个简单的<strong>a</strong>命令,这个命令的做的工作和i差不多，但是a和i不同的是，它在光标所在的后面插入，而不是在光标所在位置的前面插入。你也许已经发现了当你按下i命令进入插入模式的时候，光标不会移动，直到你输入文本为止。当你按下a命令进入插入模式时，光标将会移动到右边一格。当你输入文本时，将追加文本到原始光标所在位置的后面。</p>
<h4 name="main_content">修改文本</h4>
<p name="main_content">c,你可以通过使用c命令替换任何的文本。要告诉c命令有多少文本要被修改，你需要将c和移动命令w或b结合在一起使用。使用此种方法，移动命令就充当了文本对象。例如，c可以像下面一样使用，将修改从光标处开始到特定位置：</p>
<blockquote name="main_content">cw 修改从光标到当前单词结束位置之间的文本<br />
c2b 修改从光标到后退两个单词的位置之间的文本<br />
c$ 修改从光标到行尾之间的文本<br />
c0 修改从光标到行首之间的文本<br />
</blockquote>
<p name="main_content">当组织好一个修改命令后，你可以用任意长度的文本来替代上面所说的文本，没有字符，一个字符，或者几百个字符都可以。c 命令，就像 i 和 a 一样，带你进入插入模式，按下ESC键退出插入模式就好了。</p>
<p name="main_content">影响只会限制在当前行，vi 将会标记将被修改的尾部，以一个$来标识。所以你可以看到哪部分被修改了。（vim和vi稍微有不同，vim会删除掉单词，然后让你输入，不会用$标记出修改部分的尾部）</p>
<!-- 这里需要插入一段P20-P22  --><h4 name="main_content">单词</h4>
<p name="main_content">要修改一个单词，将c命令（change）和w命令（word）结合使用，你就可以用待会输入的文本（或长或短）替代一个单词的长度，cw可以被看作是“删除指定的单词，并插入新文本直到按下ESC键之前。假设在你的practice文件中有如下的行：</p>
<blockquote name="main_content">with an editor you can scroll the page.</blockquote>
<p name="main_content">然后你想要修改“an“为a,你只需要修改一个单词：</p>
<p align="center" name="main_content"><a href="/content/plugins/kl_album/upload/201209/9eac8e563e006ab548f42d7f8940cf382012092123202315451.png" target="_blank"><img border="0" alt="点击查看原图" src="/content/plugins/kl_album/upload/201209/9eac8e563e006ab548f42d7f8940cf382012092123202315451.png" width="480" height="142" /></a></p>
<p name="main_content">cw也可以只修改单词的一部分，例如将spelling修改为spelled，则可以将光标移动到i处，然后按下cw命令，则可以输入ed以替换ing，按下ESC键退出编辑模式，则完成编辑。</p>
<blockquote name="main_content">
<h3>vi命令的一般格式</h3>
<p>在刚才的修改命令中，你可能发现vi命令有如下的模式：<br />
<i>(命令)(文本对象)</i><br />
命令就是修改命令c，文本对象就是移动命令所描述的从光标到目标位置之间的预期的字符串（如w，$，0）。c命令不是唯一的需要接文本对象的命令，d（删除）命令以及y（yank 复制）命令也遵循这一的模式。</p>
<p>记住移动命令是可以带参数的，所以数字可以添加到c，d，y命令中（例如 d2w或2dw都可以删除连续的两个单词），记住了这点，你就会发现其实很多命令都有下面的模式：<br />
<i>(命令)(数字参数)(文本对象)</i><br />
或者将数字参数提前(等效的):<br />
<i>(数字)(命令)(文本对象)</i><br />
它们的原理是：数字和命令是可选参数，没有了它们剩下的就是一个移动命令了，当你加上一个数字参数时，那么命令就变成了一个加倍移动（表示尾部和首部的$/0除外）。另外一方面，与c,d,y结合，则可以变成一个编辑命令，当你意识到可以有多少种组合的方法时，你就会知道vi有多么强大的威力了!</p>
</blockquote>
<h4 name="main_content">行</h4>
<p name="main_content">cc命令可以替换掉整个当前行，cc修改整个行，后来输入的文本将会替代该行，直到按下ESC键退出插入模式为止。光标在行内什么位置不重要，cc都会替换掉整行。像cw这样的命令和cc命令的工作模式是不一样的，使用cw时，原先的文本依旧存在，直到你覆盖了它，然后所有的原先的内容在你按下ESC之后消失，而使用cc命令时，原先的文本将会被擦除，留下一个空行来插入文本。覆盖方法发生在影响小于一行的修改命令中，而“空行”方法发生在影响整行或更多行的命令中。 C（大写C）替换从当前光标所在位置到该行行尾的所有字符，它具有和c$一样的功效。命令cc和C是其他命令的快捷方式，所以它们不遵循一般的vi命令规则，你将会看到类似的其他快捷键，这将会在后面的删除和复制命令中讲到。</p>
<h4 name="main_content">字符</h4>
<p name="main_content"><strong>r</strong>另一个替换编辑命令r，r替换掉光标所在位置的单个字符为你输入的另一个字符，你无需按下ESC键来返回命令模式，这里有一个拼写错误：</p>
<blockquote name="main_content">Pith a screen editor you can scroll the page</blockquote>
<div name="main_content"><br />
只有P字符需要修改，你不想用cw命令替换掉整个单词，因为你将纠正整个单词为”with“。这个时候r命令就很方便了，用来替换掉单个字符:<br />
</div>
<blockquote name="main_content">
<p>按下rW 替换当前光标所在字母为W</p>
<p><a href="/content/plugins/kl_album/upload/201209/46753011d5465929eccb8e410ae3cd6a2012092123202418794.png" target="_blank"></a><a href="/content/plugins/kl_album/upload/201209/9eac8e563e006ab548f42d7f8940cf382012092123202315451.png" target="_blank"></a>&nbsp;</p>
</blockquote>
<p name="main_content"></p>
<h4 align="center"><a href="/content/plugins/kl_album/upload/201209/46753011d5465929eccb8e410ae3cd6a2012092123202418794.png" target="_blank"><img border="0" alt="点击查看原图" src="/content/plugins/kl_album/upload/201209/46753011d5465929eccb8e410ae3cd6a2012092123202418794.png" width="480" height="81" /></a></h4>
<h4 name="main_content">部分文本</h4>
<p name="main_content"><strong>s</strong>，假设你想修改几个字符，而不是一个单词，部分替换命令s,它本身只替换单个字符，然后插入若干个字符（以多个字符替换单个字符），就像修改命令（c）一样，文本最后一个字符将会用一个$符号来标记（貌似我的机子上的vim没有这个），然后你就可以清楚地看到你有多少字符被修改。</p>
<p name="main_content">S（大写S）,让你修改整行，与命令C相比，C只删除从光标到行尾的文本，而S命令删除整行，无需关心光标在行的何处。然后vi将你带入插入模式，加上数字前缀可以让你替换多行。s和S命令都会将你带入插入模式，当你完成了编辑时，按下ESC键退出插入模式。（老调重弹了很多次了）</p>
<p name="main_content">R 命令，就像他的小兄弟r一样，是用来替换文本的，只不过R简单地进入叠印（覆盖）模式，然后一一地修改，而r只修改一个字符。</p>
<h4 name="main_content">修改大小写</h4>
<p name="main_content">修改一个字符的大小写是一种特别的替换，波浪号<strong> ~</strong> 命令，可以将一个小写字母改写成大写字母，或者将一个大写字母改写成小写字母。将光标移动到你想要修改的字符所在的位置，然后输入 ~ 命令，字符的大小写将会改变，光标将会移动到下一个字符。 </p>
<p name="main_content">在早期版本的vi中，你不能使用数字前缀来修饰此命令，但是在现在的vi中，允许使用数字前缀作为参数，然后可以一次修改若干字符的大小写。如果你想一次修改若干行的大小写的话，你必须用unix的tr等命令过滤文本，将会在第七章讨论。</p>
<h4 name="main_content">删除文本</h4>
<p name="main_content">d命令，你可以删除文件中的任何文本，毫无疑问使用删除命令<strong>d</strong>就可以了。就像修改命令一样，删除命令需要一个<b>文本对象</b>（需要修改的文本的数量或者范围）。你可以删除一个单词，使用的是<strong>dw</strong>命令，删除行使用<strong>dd</strong>（或者D）命令，或者其他种种移动命令。在这些删除命令中，你需要把光标移动到要做修改的地方，然后用d命令结合文本对象（例如w）来工作。</p>
<h5 name="main_content"><span style="font-size:18px;">单词</span></h5>
<p name="main_content"><strong>dw</strong> 假如你有如下的文本：</p>
<blockquote name="main_content">
<p><span style="color:red;">S</span>creen editors are are very popular,<br />
since they allow you to make<br />
changes as you read through a file.</p>
</blockquote>
<p name="main_content">光标位置为红色字体所示，你想要删除第一行的<i>are</i>：</p>
<p name="main_content">&nbsp;</p>
<p align="center" name="main_content"><a href="/content/plugins/kl_album/upload/201209/33a554f2cc57cbe28f33863f03771bc3201209212320257416.png" target="_blank"><img border="0" alt="点击查看原图" src="/content/plugins/kl_album/upload/201209/33a554f2cc57cbe28f33863f03771bc3201209212320257416.png" width="480" height="185" /></a></p>
<!-- 插入图表dw --><p name="main_content">dw 删除一个单词，且是从光标处到所在单词的尾部。记住，跟随单词的空格也会被删除。dw也可以完成单词内的部分删除，如下面的例子：</p>
<blockquote name="main_content">since they allow<span style="color:red;">e</span>d you to make</blockquote>
<p name="main_content">你想要删除掉ed（allowed的末尾）。可以用下面的键：</p>
<p align="center" name="main_content"><a href="/content/plugins/kl_album/upload/201209/d76b36c8c33e60c647adce30f5fcdf91201209212320255585.png" target="_blank"><img border="0" alt="点击查看原图" src="/content/plugins/kl_album/upload/201209/d76b36c8c33e60c647adce30f5fcdf91201209212320255585.png" width="480" height="92" /></a></p>
<!-- 图表 按键 --><p name="main_content">dw会删除下一个字母之前的空格，但是在本例中我们并不想这么做，要保留单词间的空格，则使用<strong>de</strong>命令，这样就只删除到文件的末尾了。使用<strong>dE</strong>命令可以删除到单词的末尾，包括标点符号。</p>
<p name="main_content">你也可以向后删除（db，聪明的你可以想象一下它的效果）或者删除到一行的末尾或者开头（d$ 和 d0）.</p>
<h4 name="main_content">行</h4>
<p name="main_content"><strong>dd</strong> 命令删除光标所在的整行，dd不会删除行的一部分，要么全删，要么不动。就和其他完全命令 （如cc）一样， dd是一个很特殊的命令。用和上个例子完全相同的文本，光标在第一行。</p>
<p align="center" name="main_content"><a href="/content/plugins/kl_album/upload/201209/2930b3597879fb898a2d323ae3a94f642012092123202610294.png" target="_blank"><img border="0" alt="点击查看原图" src="/content/plugins/kl_album/upload/201209/2930b3597879fb898a2d323ae3a94f642012092123202610294.png" width="480" height="82" /></a></p>
<!-- 插入图表 p24 dd --><p name="main_content">大D命令删除从当前位置到行末尾的文本，D是 d$的快捷方式。（其实很多方法都是和其他命令如C相似），例如：</p>
<!-- 插入图表 p24 D --><p name="main_content">你可以删除删除从光标起的右边部分的文本：</p>
<p align="center" name="main_content"><a href="/content/plugins/kl_album/upload/201209/5f89eca018292ce26e6832624bbbf48f2012092123202614605.png" target="_blank"><img border="0" alt="点击查看原图" src="/content/plugins/kl_album/upload/201209/5f89eca018292ce26e6832624bbbf48f2012092123202614605.png" width="480" height="101" /></a></p>
<p name="main_content">&nbsp;</p>
<!-- 插入图表 p25 D --><h4 name="main_content">字符</h4>
<p name="main_content"><strong>x</strong>命令，有时候你只是想删除一两个字符，不想弄得太大动静，那么使用r命令来做替换也不太适用，那么使用x命令，可以删除一个字符，且只删除当前光标所在处的一个字符。假如有下面的行:</p>
<blockquote name="main_content">zYou can move text by deleting text and then</blockquote>
<p name="main_content">你可以用x命令删除字母‘z’,另外一个特别的命令<strong>X</strong>（大写x），可以删除光标以前的那个字符。而在命令前假如数字前缀，则等价于运行命令多次，如5x，可以向右删除5个字符。</p>
<h4 name="main_content">你可能会碰到的问题</h4>
<div name="main_content">
<ul>
<li>你删错了东西，想要恢复回来</li>
<p>如果你用删除命令，删掉了你不想删的东西，那么你可以输入<strong>u</strong>命令来撤销你的修改，因为u命令就是undo，你可以恢复到以前的修改。如果你做的是最后一次修改，想要恢复过来，尝试一下p命令，因为你删除的东西会保存到p所维护的空间，然后按下p就可以将那些误删的粘贴回去。vi缓存最近9个删除的内容，可以用如3p的命令恢复前删除的三行。</p>
</ul>
</div>
<h3 id="changeText">移动文本</h3>
<p>在vi中，通过删除文本然后在别处粘贴来移动文本，每次你删除了一个文本块，被删除的文本将会临时存储在一个特别的缓冲区中，然后移动光标到你想要放置文本的地方，然后用p ( put)命令来将文本放置到该处。你可以移动任何一块文本，尽管移动行比移动单词要有用的多。</p>
<p>p，<strong>p</strong>命令将缓存区中的内容粘贴到光标后面区域，如果你删除了一或多行，p将会把你所删除的文本粘贴到光标所在行的下一行。假设你有如下的文本：</p>
<blockquote>You can move text by deleting it and then,<br />
<span style="color:red;font-size:small;">l</span>ike a "cut and paste,"<br />
placing the deleted text elsewhere in the file.<br />
each time you delete a text block.<br />
</blockquote>
<p>然后你想把第二行移动到第三行的后面，先使用d命令删除，然后用p命令放置。如下所示：</p>
<p align="center"><a href="/content/plugins/kl_album/upload/201209/bfe6511d37d1934b04e1f2c067fc159e2012092123202728866.png" target="_blank"><img border="0" alt="点击查看原图" src="/content/plugins/kl_album/upload/201209/bfe6511d37d1934b04e1f2c067fc159e2012092123202728866.png" width="480" height="183" /></a></p>
<!-- 图片  p26 --><p><i>一旦你删除了文本，你需要在下面的修改或者删除之前保存一下，如果你同时在编辑其他文件，会影响缓冲区的话，你删除的文本可能会丢失。你可以重复多次p命令，只要你没有进行进行新的编辑。在第四章，你将会学习怎样保存一个命名了的缓冲区中被你删除的文本，所以你可以恢复你的数据。</i></p>
<h4>一个有用的小技巧——转置文本</h4>
<p>你可以使用<strong>xp</strong>命令（想象一下，删除一个字符，然后插在下一个字符的后面，不就将相邻的两个字符换位了吗？）来交换两个字符的位置。例如，在单词mvoe中，vo两个单词位置反了，所以要修改回来，只需要将vo的位置调转过来即可，所以先x，删除掉字符‘v’，然后将‘v’放到（p）字符‘o’的后面，这样就调整了vo的位置为ov。</p>
<h3 id="deleteAndCopy">拷贝文本</h3>
<p><strong>y</strong>命令，很多时候你可以使用拷贝命令来节省编辑的时间，使同一段文本在多处重复。使用两个组合使用的命令：一个y命令，一个p命令就可以实现了。你可以拷贝任意长度的文本，然后放置在其他的任何位置。一个（急抽）拷贝命令可以复制所选的文本到一个特殊的缓冲区中（可以一直保持直到下一个y命令覆盖），然后就可以讲所复制的内容用p命令粘贴了。</p>
<p>就像修改和删除命令，拷贝命令可以和任何移动命令结合（如yw，y$，4yy）。y命令经常使用在拷贝一行内容的情况，因为拷贝命令往往要在距离更远的其他行粘贴文本，而更少修改行内文本。假设practice有下面的文本：</p>
<blockquote>With a screen editor you can<br />
scroll the page.<br />
move the cursor.<br />
delete lines.<br />
</blockquote>
<p>你想要造出三个完整的句子，每句都用“With a screen editor you can”开头，你可以使用拷贝命令y，来完成这项简单的工作。</p>
<p align="center"><a href="/content/plugins/kl_album/upload/201209/9b6dface1672a5aa6d013e0e2ed4bb362012092123202820179.png" target="_blank"><img border="0" alt="点击查看原图" src="/content/plugins/kl_album/upload/201209/9b6dface1672a5aa6d013e0e2ed4bb362012092123202820179.png" width="480" height="211" /></a></p>
<p align="center"><a href="/content/plugins/kl_album/upload/201209/f0260e63606f28822ae8dabfc1ffc93a201209212320292576.png" target="_blank"><img border="0" alt="点击查看原图" src="/content/plugins/kl_album/upload/201209/f0260e63606f28822ae8dabfc1ffc93a201209212320292576.png" width="480" height="160" /></a></p>
<!-- 图 p27 --><p>y命令和删除命令使用的是同一个缓冲区，每次最近的删除或者拷贝都会取代之前的缓冲内容，我们将会在第四章看到，大概有9个拷贝或者删除内容块被放在buffer里面，他们都可以用p命令来粘贴。你也可以将它们删除或者粘贴到26个不同的缓冲区中（复制粘贴缓冲区），这允许你像玩杂耍一样摆弄文本块。</p>
<h3>重复或者撤销你的最后一条命令</h3>
<p>每个编辑命令都缓存在一个临时缓冲区里面，直到你的下一个命令输入时才消失。例如你在一个单词后插入了一个"the"，插入文本的命令以及你做的操作，都被保存起来了以用于撤销。</p>
<h4>重复命令</h4>
<p><strong>.</strong>命令，每次你想重复上次使用过的命令，你可以重复多次该命令，点符号（.）可以让你重复命令。看下面的例子：</p>
<blockquote>With a screen editor you can<br />
scroll the page.<br />
With a screen editor you can<br />
move the cursor.<br />
</blockquote>
<p>你可以删除一个行，然后删除另外一行，只需要输入一个点命令即可。</p>
<p align="center"><a href="/content/plugins/kl_album/upload/201209/63ca5ffe6d93c6fa89e9249073275af52012092123203017207.png" target="_blank"><img border="0" alt="点击查看原图" src="/content/plugins/kl_album/upload/201209/63ca5ffe6d93c6fa89e9249073275af52012092123203017207.png" width="373" height="169" /></a></p>
<!-- 图片 p28 --><p>老版本的vi在重复命令的时候有问题，例如，在插入一个很长的文本时，如果设置了wrapmargin（换行对齐），则会有困难。如果你有这样的老版本，这个bug将迟早会折腾到你。你能做的不多，只是提前警告一下。（现代版本的vi不见得有这样的问题）你有两种方法来解决这样的问题，当重复多次长文本插入时，你可以在重复下一次命令之前保存一次文档( : w)，也可以讲wrapmargin设置为0.即如下所示:</p>
<blockquote>: set wm=0</blockquote>
<p>在后面的章节“更多映射键的例子” 中，我将会向你展示一种使用wrapmargin的简单解决方案。在一些vi版本中，命令 CTRL+@ 可以重复最近的插入操作（我在vim上试了一下，听到的却是嘟嘟声，原来是没有进入到插入模式）。进入插入模式，可以执行CTRL+@命令来重复插入，插入后将带你回到命令模式。</p>
<h4>回退-撤销</h4>
<p><strong>u</strong>命令，早之前已经提到过了undo命令，在你操作错误的时候可以撤销你的命令。只需简单地按下u键。这时候光标在哪都无所谓。继续之前的例子，下图展示了删除后的practice文件:</p>
<p align="center"><a href="/content/plugins/kl_album/upload/201209/d025ebcec8e5f50f5248e4cb74b3704c2012092123203022793.png" target="_blank"><img border="0" alt="点击查看原图" src="/content/plugins/kl_album/upload/201209/d025ebcec8e5f50f5248e4cb74b3704c2012092123203022793.png" width="473" height="109" /></a></p>
<!-- 图表 p29 --><p><strong>U</strong>,大写u，可以撤销在一个行的所有修改。只要光标保持在该行，当你从该行移走后，你就不能继续使用U命令了。注意你不能撤销你最近做的撤销（撤销动作）,在两个文本修改版本之间切换。（设想一下，如果可以撤销你的撤销动作，那么撤销一个编辑，然后撤销你的撤销，就是恢复，所以是在里两个版本里切换，这做没有多大意义）但是u命令可以撤销U命令，而U命令将会撤销所有在本行的修改，包括哪些u所做的修改。（恢复到该行做任何修改之前的状态——创建状态）</p>
<blockquote>小技巧：u命令可以撤销它本身的操作将会导致一个很调皮的循环。如果你只是想要撤销你最后的编辑修改，那么简单地撤销它，你将会被弹回原来的行。当你撤销你的撤销操作时，你仍呆在本行。 </blockquote>
<p>vim 可以让你使用 CTRL+R键来重做一个未完成的命令，和无限重做结合在一起，你可以向前或者向后你的编辑历史，可以查看稍后章节“撤销撤销操作”。</p>
<h3 id="moreInsertion">更多插入的方法</h3>
<p>你可以在光标前插入一段话，按下如此的键队列：<br />
itext to be inserted ESC键 <br />
然后你就向里插入了“text to be inserted”,并且回到了命令行模式。这里还有其他的一些插入命令，在光标前后不同位置进行插入：</p>
<blockquote>A 向行尾追加文本 <br />
I 向行首作插入操作<br />
o (小写o)，向下创建一个新行，然后插入文本<br />
O (大写O), 向上创建一个新行，然后插入 <br />
s 删除光标所在的或者替换文本<br />
S 删除本行或替换本行 <br />
R 用新值覆盖原有文本，会一直向右边移动，且可以添加新文本。<br />
</blockquote>
<p>所有的这些命令可以让你进入到插入模式，完成插入后，记得按下ESC键退回到命令模式。</p>
<p>A (append) 和 I(insert) 可以让你避免在编辑前移到行尾或者行首。(A命令比$a好，因为少按一次键，尽管算起来还是一样多的键，但是更快了不是吗？只有你越懒，那么你可能学会更多命令让计算机来帮你做哪些无聊的重复工作。)</p>
<p>o和O命令，在下一行或者上一行新开一行，也不用再换行然后光标退回了。你可以在当前行任意位置敲入。</p>
<p>s和S命令（substitute）允许你删除一个字符或者一整行，然后接入你要输入的任意长度文本。s等价于 c + 空格符，表示用空格符来代替一个字符。S命令呢，和cc命令是一样的功效的。s的最佳用处是修改一个单词为若干个单词。</p>
<p>R命令（replace）是很有用的，当你想修改文本，但是不知道要修改多少个字符的时候，例如，你不知道要修改几个单词（估计用3cw或者4cw），但是这些都没有R那么好，因为R是改到哪就是哪逐个替换的。改完了，退出插入模式就行了。</p>
<h4>插入命令的数字参数</h4>
<p>除了o和O命令之外，以上列出的插入命令（加上i和a），可以使用数字前缀做参数。有了数字前缀，你可能会用i,I或a命令来插入一行下划线或者交替的符号，例如，你可以输入50i* ESC键 来输出一行“**********************************”，而用25a*- ESC键来输出这样一行“*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-”（貌似是程序员编程时候的装饰性分隔线，有这个东西爽爆了），这比重复地输入一个字符或者几个字符要有意思的多（很讽刺的是，我使用的不是vi编辑器，结果我输入上面的符号的时候就是用手工重复的方法，实在是没有vi那么高效啊！）</p>
<p>有了数字前缀，r命令可以一次替换一片的字符（例如输入个5r，再输个a，你会发现五个字符被替换为a了，你将看到“aaaaa”整整齐齐地站在你的屏幕上。），在C或者C++中，要将|| 换成 &amp;&amp;，只需输入一个2r&amp;即可，无比省事。（越来越崇拜开发vi的神人了，感觉vi就是为程序员打造的，程序员又懒又聪明，才会让计算机来提高我们工作的效率）</p>
<p>你可以在大S命令前加上数字参数，这样你就可以一下替换掉好几行了，这相当地迅速且很灵活，和用c 命令和移动命令结合起来用一样爽。</p>
<p>一个很好的例子是，用s命令前面加数字参数可以一次替换掉好几个字符，这些字符往往在单词的中间，输入r不好，输入cw会改掉太多，那就用s命令吧，它的效果和R差不多，但其实还是有所不同的。</p>
<p>还有其他的完美结合可以让你的编辑变得自然，例如ea命令（其实和A命令一样）也是一个很有用的组合，可以在本行末尾添加文本。你将会被这些聪明的命令所导引，向着一个自动化的美好的世界而去。</p>
<h3>将两行连在一起</h3>
<p>J 命令，有时候你要将一些看起来很丑的短行连接在一起，只需要将光标移到第一行，然后用J命令就可以将两行合并了。假设你有如下的practice文件：</p>
<blockquote>With a <br />
screen editor<br />
you can<br />
scroll the page, move the cursor<br />
<!-- 插入图片p31 --></blockquote>
<p align="center"><a href="/content/plugins/kl_album/upload/201209/96113e0a014deaa14a1c208526a5d7d0201209212320314260.png" target="_blank"><img border="0" alt="点击查看原图" src="/content/plugins/kl_album/upload/201209/96113e0a014deaa14a1c208526a5d7d0201209212320314260.png" width="480" height="206" /></a></p>
<p>在J之前加上数字参数会让你惊喜地发现，一下子可以将好几个行合并。但是合并后你会发现每行之间会留下痕迹——一个空格。（感觉这个功能也是为程序员造的，合并几条语句在一行里面。）</p>
<h4>问题清单</h4>
<ul>
<li>当你输入命令时，文本在你的屏幕上跳来跳去四处游走，而且不知道它在干嘛</li>
<p>当你想按<strong>j</strong>的时候,不要 错误滴按下J命令，你可能无意中按下了大写转换键 Caps Lock，vi是大小写敏感的，这个不用啰嗦了。当发现caps lock 灯亮的时候，再按一次回到原来的状态。记住按下ESC命令，回到命令模式。无需多言!</p>
</ul>
<h3>回顾学过的命令</h3>
<p>下面的图表，展示了c，d，y命令的一些结合移动命令的使用，都是一些基础命令，本章介绍的命令就这些，记住一定要勤加练习才能熟能生巧。掌握这些命令，你已经入门了，但是要真正体会到<b>vi</b>的强大，你还得看下面的高级章节。</p>
<p>&nbsp;</p>
<p align="left"><a href="/content/plugins/kl_album/upload/201209/49c649f71554b5690cefadcd74b72d172012092123203215885.png" target="_blank"><img border="0" alt="点击查看原图" src="/content/plugins/kl_album/upload/201209/49c649f71554b5690cefadcd74b72d172012092123203215885.png" width="480" height="345" /></a></p>
<p align="left"><a href="/content/plugins/kl_album/upload/201209/b3622841321ef1d4c9803f93607956522012092123203422286.png" target="_blank"><img border="0" alt="点击查看原图" src="/content/plugins/kl_album/upload/201209/b3622841321ef1d4c9803f93607956522012092123203422286.png" width="310" height="360" /></a></p>
<p>translated by <a href="/admin">bibodeng</a>&nbsp; 如有错误，欢迎斧正&nbsp; 2012-09-22&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;谢绝转载</p>
<p>&nbsp;今后将不再翻译了，而是以笔记的形式记录一些，因为已经有一本还不错的中译本《学习vi和vim编辑器》&nbsp; 不重复发明轮子。</p>
<!-- 插入图片p32 --><!-- main_content end--><p></p>
<style type="text/css">
body{
font-size: 15px;
letter-spacing: 1px;
line-height: 1.3em;
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
background-color:#99FF33;
padding: 10px;
}

.example{
background-color:#CCCCCC;
font-size:1.2em;
-webkit-border-radius: 5px;
}

.small_title{
font:italic;
padding: 5px;
}
</style>{% endraw %}

<div id="table-of-contents">
<h2>Table of Contents</h2>
<div id="text-table-of-contents">
<ul>
<li><a href="#sec-1">1. Taskjuggler基本概念</a></li>
<li><a href="#sec-2">2. TJP文件结构</a>
<ul>
<li><a href="#sec-2-1">2.1. 主要关键字清单</a></li>
<li><a href="#sec-2-2">2.2. 项目定义</a></li>
<li><a href="#sec-2-3">2.3. 宏变量</a></li>
<li><a href="#sec-2-4">2.4. 标签</a></li>
<li><a href="#sec-2-5">2.5. 账户</a></li>
<li><a href="#sec-2-6">2.6. 资源借用</a></li>
<li><a href="#sec-2-7">2.7. 假期设置</a></li>
<li><a href="#sec-2-8">2.8. 资源池配置</a></li>
<li><a href="#sec-2-9">2.9. 任务列表</a></li>
<li><a href="#sec-2-10">2.10. 项目成本报告</a></li>
<li><a href="#sec-2-11">2.11. 项目资源报告</a></li>
<li><a href="#sec-2-12">2.12. 项目任务报告</a></li>
<li><a href="#sec-2-13">2.13. 文本报告</a></li>
<li><a href="#sec-2-14">2.14. 项目导出</a></li>
</ul>
</li>
</ul>
</div>
</div>


# Taskjuggler基本概念<a id="sec-1" name="sec-1"></a>

Taskjuggler使用一个或多个文本文件来描述一个项目，当一个项目被拆分为多个文件时，最主要的文件名称的后缀必须为 **.tjp** ，而这个主要文件内，可以引入其它多个文件，被引入的文件必须采用 **.tji** 后缀。在主要项目文件中，可以采用如 \*include "inner.tji"\* 的方式引入一个或多个文件。
目前最新的3.5版本中，只能采用命令行的方式使用，因此需要我们选择一个自己习惯使用的编辑器来编写项目即可，然后通过简单的命令来编译完成的项目文件，最终可以生成其它的格式以查看相应的项目报告。
说到编译，实际我们在完成项目文件后，即完成一个 **.tjp** 和其它多个 **.tji** 文件后，可以在当前目录下，打开 **cmd** 或终端，执行一下编译命令。比如我们的项目文件名称叫 **main.tjp** ,因此编译命令则为：

    tj3 main.tjp

以上编译命令，会让taskjuggler来自动对多个文件进行合并计算，Taskjuggler会自动安排所有任务的特殊条件，遇到错误后会提示编译失败的原因，并最终在编译通过后，成功输出文件，如HTML格式的项目报告。文件会最终输出在 **tjp** 所在的相同目录下。

# TJP文件结构<a id="sec-2" name="sec-2"></a>

## 主要关键字清单<a id="sec-2-1" name="sec-2-1"></a>

-   project
-   macros
-   flags
-   accounts
-   shifts
-   vacations
-   resources
-   tasks
-   accountreports
-   resourcereports
-   taskreports
-   textreports
-   exports

本章我们将先从了解Taskjuggler的主要关键词开始逐一展开 。

## 项目定义<a id="sec-2-2" name="sec-2-2"></a>

一个项目首先开始的，是定义它的项目属性，所用到的关键字为 **project** 。这里我们从一个例子开始：

    语法：
    project <Project Name> Start-Date End-Date {
      <Attributes>
    }
    例子：
    project "Example Project" 2015-11-18 +2m {
      timezone "China/Shanghai"
    }

通过 **project** 关键字，我们需要定义项目的名称，项目的开始时间，结束时间，其中结束时间可以采用一个时间段的格式来定义，后面我们会专门有一节对多种时间格式定义来说明。Fn请查看第n节。
项目大括号中可以对项目的时间格式、数字格式、货币格式、时区、假期、工作日、工作日中工作时间等等属性进行预定义，以满足不同的需求，当然当涉及到多个跨时区或跨国家团队共同工作时，这里也可以针对某一个团队或者某一些任务进行分别定义。给项目团队的管理带来及大的灵活性，从而满足各种项目背影下的管理需求。
本书后面章节会逐一讲到针对不同的项目场景列举到的不同例子，以提供大家理解及实际应用。

## 宏变量<a id="sec-2-3" name="sec-2-3"></a>

宏变量macros用于定义一些类似常量的值，定义一段可以被重复引用的文本段，它的定义格式为：

    语法： macros <Specific ID> <MACROS>
    例子： macros allocateGroupID [ allocate John, Real ]
    引用： ${allocateGroupID}

在项目之前定义好宏变量后，可以在项目的任何合适的位置，通过以 **${allcateGroupID}** 来引用这个宏变量，在编译项目文档时，宏变量将会被定义在中括号中的内容替换掉。
宏变量的另一种方式可以对其内容主体输入参数，以满足不同变量场景的情况下的引用。它的定义格式为：

    语法： macros <Specific ID> <MACROS>
    例子： macros allocateGroup2 [ allocate ${1}, ${2}, Tim]
    引用： ${allocateGroup2 "John" "Real"}

这样宏变量将会在引用的时候，通过动态输入参数来替换宏变量中定义的变量值。
另外，宏变量可以中可以引用其它的宏变量，比如

    macros devGroup [ John, Tim, Tex]
    macros testGroup [ Jean, Oreal, Rubean]
    macros allocateGroup3 [ allocate ${?devGroup} ${?testGroup} ]

可以看到必须将被引用的宏变量定义在引用之前；且在引用的变量前需要有一个问号。当其中的变量发现未被提前定义时，此变量将不被引用。
宏变量及大的方便了我们定义项目中的各种资源、任务、文本等内容，可以简化项目定义时的重复内容，也更方便在项目运行期时，其中的某些内容的变化的及时更新。

## 标签<a id="sec-2-4" name="sec-2-4"></a>

标签flags关键词，主要用于定义任务、资源、或其它属性时用于特殊标识，以至于我们可以利用它来过滤我们想要的内容，从而生成不同需求的项目报告。

    语法： flag <ID> [, <IDs>...]
    例子： flag devTasks

如上面的例子，我们在 **task** 任务中定义一个类似的 **flag** , 这样我们可以在项目报告中，统计所有 **devTasks** 的任务相关属性，如任务的完成情况。后面在讲解项目报告时，会结合 **flag** 标签来完成一定目标的项目报告。

## 账户<a id="sec-2-5" name="sec-2-5"></a>

## 资源借用<a id="sec-2-6" name="sec-2-6"></a>

## 假期设置<a id="sec-2-7" name="sec-2-7"></a>

## 资源池配置<a id="sec-2-8" name="sec-2-8"></a>

## 任务列表<a id="sec-2-9" name="sec-2-9"></a>

## 项目成本报告<a id="sec-2-10" name="sec-2-10"></a>

## 项目资源报告<a id="sec-2-11" name="sec-2-11"></a>

## 项目任务报告<a id="sec-2-12" name="sec-2-12"></a>

## 文本报告<a id="sec-2-13" name="sec-2-13"></a>

## 项目导出<a id="sec-2-14" name="sec-2-14"></a>

<div id="footnotes">
<h2 class="footnotes">Footnotes: </h2>
<div id="text-footnotes">

<div class="footdef"><sup><a id="fn.1" name="fn.1" class="footnum" href="#fnr.1">1</a></sup> <p>DEFINITION NOT FOUND.</p></div>


</div>
</div>

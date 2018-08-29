<div id="table-of-contents">
<h2>Table of Contents</h2>
<div id="text-table-of-contents">
<ul>
<li><a href="#sec-1">1. Taskjuggler介绍</a></li>
<li><a href="#sec-2">2. Taskjuggler重点特性一览</a>
<ul>
<li><a href="#sec-2-1">2.1. 基础属性</a></li>
<li><a href="#sec-2-2">2.2. 高级计划安排</a></li>
<li><a href="#sec-2-3">2.3. 成本管理</a></li>
<li><a href="#sec-2-4">2.4. 项目报告</a></li>
<li><a href="#sec-2-5">2.5. 缩放及企业特性</a></li>
<li><a href="#sec-2-6">2.6. Web发布及组件功能</a></li>
</ul>
</li>
<li><a href="#sec-3">3. 为什么是Taskjuggler</a>
<ul>
<li><a href="#sec-3-1">3.1. 资源池管理</a></li>
<li><a href="#sec-3-2">3.2. 自动资源分配计算及资源冲突管理</a></li>
<li><a href="#sec-3-3">3.3. 任意自定义的项目状态报告</a></li>
<li><a href="#sec-3-4">3.4. 支持多项目整合管理及拆分管理</a></li>
<li><a href="#sec-3-5">3.5. 与Git结合分布式管理</a></li>
</ul>
</li>
<li><a href="#sec-4">4. Taskjuggler安装</a>
<ul>
<li><a href="#sec-4-1">4.1. Ruby安装</a>
<ul>
<li><a href="#sec-4-1-1">4.1.1. 软件安装</a></li>
<li><a href="#sec-4-1-2">4.1.2. 安装完成验证</a></li>
<li><a href="#sec-4-1-3">4.1.3. 配置Ruby的gem环境</a></li>
</ul>
</li>
<li><a href="#sec-4-2">4.2. Taskjuggler安装</a></li>
</ul>
</li>
</ul>
</div>
</div>


# Taskjuggler介绍<a id="sec-1" name="sec-1"></a>

Taskjuggler是一个现代的、功能强大的项目管理工具。它的功能要远远优秀于类似使用甘特图管理项目的工具，它已经成功用于大量的大中型项目，这些项目可以包含成百上千的资源、成千上万的任务列表。
Taskjuggler是一个开源工具，针对各种各样的项目管理、项目集管理。使用Taskjuggler可以对一个项目从它的项目点子开始，到项目最终完成所涉及的所有工作任务的管理，并且不需要有特殊的工作流程及方法论的支持。它帮助你在项目范围，资源分配，成本和收入计划，风险管理和沟通，项目进度跟踪和各种需求的报告上，提供最大化、最方便的管理的分析，为项目过程管理提供真实、详细的自动分析。
Taskjuggler基于项目任务安排、资源分配、时间安排等内容自动计算及优化调度项目的时间线执行及资源分配的合理性。内置的资源平衡及约束检查将使你不再需要关注无关紧要的细节，并在项目失控时提供及时的报警。灵活的“尽可能多的必要细节”使你依然可以按计划执行你的项目，并符合新的项目管理策略，如极限编程、敏捷项目管理。
不论你是在盖一栋摩天大楼，还是只是对你的开源项目管理做一些管理上的辅助，Taskjuggler都将适合你。但如果你仅仅想做一个漂亮的甘特图给你的老板或者投资者，Taskjuggler可能会不适合你，因为它可以做的比甘特图更多。当然，学习Taskjuggler将需要你花费一些时间和精力，它比可视化界面的学习起来更困难，然而当你掌握它后，它将会是你工作上的最佳伙伴。
Taskjuggler工作在命令行上，因此在编写你的项目计划时，你需要的工具仅仅是：你最喜欢的编辑器、你喜欢的浏览器即可。本书我将带领大家来学习和使用Taskjuggler，并提供一些常用在我的实际工作中经常遇到的项目管理的问题，使用Taskjuggler如何进行管理及更方便快捷的避免资源分配、资源冲突、项目工期拖延、成本计算等内容。

# Taskjuggler重点特性一览<a id="sec-2" name="sec-2"></a>

## 基础属性<a id="sec-2-1" name="sec-2-1"></a>

-   管理项目的任务、资源、账户
-   功能强大的TODO清单管理
-   详细的使用说明
-   安装简单
-   成功运行于Windows, Linux, Macos, Unix等其它操作系统
-   完整支持Vim编辑器
-   支持Emacs Orgmode之间转换

## 高级计划安排<a id="sec-2-2" name="sec-2-2"></a>

-   自动资源平衡及任务冲突管理
-   相同项目无限制的场景设置，用于做假设分析
-   灵活的工作时间配置、资源的退出管理
-   支持工作转换
-   多种时区支持

## 成本管理<a id="sec-2-3" name="sec-2-3"></a>

-   对任务配置初使化成本、并支持分析最终成本
-   对资源配置使用成本
-   任务及资源都基于成本模型
-   支持投入产出分析

## 项目报告<a id="sec-2-4" name="sec-2-4"></a>

-   全面且灵活的报告，提供给你你想要的项目信息
-   功能强大的过滤功能，能给不同的查看对象以信息查看
-   基于时间及工作状态的报告
-   项目跟踪及状态报告驾驶仓报告

## 缩放及企业特性<a id="sec-2-5" name="sec-2-5"></a>

-   支持对多个项目进行合并为一个大项目
-   支持集中式资源池分配数据库
-   强大的项目描述语言及宏支持
-   可支持多核及多CPU系统
-   可导出为Microsoft Project和计算机辅助分析

## Web发布及组件功能<a id="sec-2-6" name="sec-2-6"></a>

-   支持发布为HTML格式
-   可以导出CSV格式，以便支持多种流行的项目办公工具
-   可以导出iCalendar
-   内置Web Server，以支持动态更新及互动报告
-   基于服务端时间表做状态和实际运行报告

# 为什么是Taskjuggler<a id="sec-3" name="sec-3"></a>

以上是Taskjuggler的搜索评价，不了解的人可能会觉得，已经有了像MS Project这样的工具，应对项目进度、资源管理已经足够了，因此不需要其它的项目管理工具。是的，确实类似的项目管理工具太多了。收费的、免费的工具网上问一问度娘可以发现很多，而为什么我要花时间去专门用一本书去学习一个多余的工具？稍做了解的人可能会发现，Taskjuggler和其它的项目管理工具不同，因为它是基于文本的项目管理工具，初接触起来会发现它很难掌控，要写很多的英文单词去写各种任务，而且它没有提供一个很好的可视化编辑界面来提供一个方便快捷的用户界面，因此它的学习成本会比较高；那为什么我要推荐使用Taskjuggler？

## 资源池管理<a id="sec-3-1" name="sec-3-1"></a>

Taskjuggler对于资源采用资源池的配置方式，可以通过按单位人来设置资源，可以按多人进行配置一个团队资源。当其中某一项资源的出场时间不同，比如采用每天只有4小时的兼职参与的方式，或者某一项资源的工作时间不同（四日工作制），工作之间请假的配置，都将通过对资源的统一管理，来达到满足不同资源应用场景的需求。
具体我们会在后面详细讲解一项资源的配置方式，并结合不同的应用场景来通过合理配置资源，达到合理安排资源、最大化资源利用率。

## 自动资源分配计算及资源冲突管理<a id="sec-3-2" name="sec-3-2"></a>

在使用Taskjuggler配置任务时，我们需要设置的是资源，及任务的开始、相关依赖、任务的耗时，Taskjuggler会自动对任务进行资源分配，计算资源的合理出场时间，在组合利用的基础上能够自动计算资源的占用时间线，合理分配资源的占用时间。
并且基于任务之间的关系，避免多任务或者多项目同资源的资源冲突问题。

## 任意自定义的项目状态报告<a id="sec-3-3" name="sec-3-3"></a>

## 支持多项目整合管理及拆分管理<a id="sec-3-4" name="sec-3-4"></a>

## 与Git结合分布式管理<a id="sec-3-5" name="sec-3-5"></a>

# Taskjuggler安装<a id="sec-4" name="sec-4"></a>

本书以Taskjuggler3.5.0版本为基础，它使用Ruby进行开发，因此安装它之前需要先安装Ruby环境，需要的Ruby为至少2.0以上。

## Ruby安装<a id="sec-4-1" name="sec-4-1"></a>

### 软件安装<a id="sec-4-1-1" name="sec-4-1-1"></a>

-   Windows
    打开下载地址：<http://dl.bintray.com/oneclick/rubyinstaller/rubyinstaller-2.2.3.exe>， 下载最新的ruby安装包，这里下载的是
-   Linux
    在Linux上不同的软件管理都有不同的安装命令，这里给出几种常用的在线安装方式

    // Archlinux
    sudo pacman -S ruby
    // Fedora, Redhat
    sudo yum install ruby
    // Ubuntu, Debain
    sudo apt-get install ruby

-   MacOS
    MacOS中可以使用brew来进行安装，而对于brew的安装，用户可以网上搜索找到相关的信息，安装完成brew后，可以在终端内，用以下命令则可以安装：

    brew install ruby

-   编译安装
    另外可以直接在除Windows平台上，采用源码编译安装的方式。
    首先先下载源码包：<https://cache.ruby-lang.org/pub/ruby/2.2/ruby-2.2.3.tar.gz>， 然后解压进入编译安装，Linux和MacOS的编译安装方式命令都相同：

    tar xvf ruby-2.2.3.tar.gz
    cd ruby-2.2.3
    ./configure
    make && make install

### 安装完成验证<a id="sec-4-1-2" name="sec-4-1-2"></a>

安装完成后，需要对Ruby进行一下安装成功与否的验证，验证方法如下：
Windows打开cmd，Linux和MacOS可以打开终端，执行如下命令：

    ruby -version

如果正常打印出如下版本信息，则说明Ruby安装成功。
![img](./images/ruby-version.png)

### 配置Ruby的gem环境<a id="sec-4-1-3" name="sec-4-1-3"></a>

由于ruby的在线安装源在国内访问不了，因此需要将软件源更新为国内的，我们选择使用Taobao的Ruby软件源，因此需要在安装完成Ruby后，修改掉官方提供的软件更新源，具体更新办法如下：（Windows打开cmd, Linux和MacOS打开终端）

    gem sources --remove https://rubygems.org/
    gem sources -a https://ruby.taobao.org/
    gem sources -l

## Taskjuggler安装<a id="sec-4-2" name="sec-4-2"></a>

安装完成Ruby后，则可以直接使用gem进行在线安装最新版本的Taskjuggler，依然是Windows打开cmd, Linux和MacOS打开终端：

    gem install taskjuggler

安装完成后，使用如下命令验证是否安装成功：

    tj3 -version

打印出如下taskjuggler的版本信息，则说明安装成功。
![img](./images/taskjuggler-version.png)

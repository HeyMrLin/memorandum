<u>什么是前端布局基础？</u>

前端布局方案主要有三种：

+ 传统布局(借助浮动、定位等手段)
+ flex布局方案(弹性布局)
+ grid布局方案(网格布局)

传统布局学习成本高，代码复杂，基于css2，兼容性好，对用户友好。

flex布局学习成本低，代码优雅，兼容性不好，IE10才支持，且需使用-ms-前缀。

grid布局是一种二维布局方案，兼容性也不好，同样IE10才指出，也需要使用-ms-前缀。

总的来说，这三类方案都能基本解决日常的前端布局问题，且从易用性、灵活性和强大性来说，flex布局和grid布局更是未来的趋势。但是从当前各版本浏览器在用户市场上的使用情况和各方案的浏览器兼容性来看，传统布局方案对用户最友好，具有一定的不可替代性，所以我觉得，**<u>传统布局方案是最应该先掌握好的，尤其是对于在to B企业工作的前端同学来说</u>**。

所以本文将详细介绍的“前端布局基础”，指的是围绕着“传统布局方案”的众多CSS知识，其主要内容来源于CSS2规范。

<u>量化布局方案的合理性</u>

学好前端布局基础，其目的是为了在面对不同场景的布局问题时，能够提出一种合理的布局方案：既能<u>解决问题</u>，又能最大程度地<u>拥抱变化</u>。

要想量化“拥抱变化”这个目标，我们首先得清楚“变化”有哪些。笔者根据过往的开发经验，将变化分为两大类：<u>一是布局需求的变化</u>，二是<u>运行环境的变化</u>。

1. 对于布局需求的变化，可以做到：
   + 方便快速定位需修改的位置
   + 能够不花或用最少的修改成本应对变化
2. 对于运行环境的变化，可以做到：
   + 在不同浏览器均有正确或良好的显示

如果一个方案能够体现以上几点原则，我认为可以称得上是一个合理的方案。最后，我将布局实现方案的合理性归纳为：方案在满足正确性的前提下，其实现逻辑规范、实现职责分明且拥有良好的浏览器兼容性。

下面我们正式开始介绍与“传统布局方案”相关的布局基础知识。

<u>布局基础要点</u>

1. CSS标准盒模型(或W3C盒模型)

2. box-sizing（CSS3属性）（content-box、padding-box、border-box、margin-box）

   + box-sizing的作用

     简单来说，box-sizing的作用就是告诉浏览器：CSS属性width和height是用于设置哪一种box的尺寸，在W3C标准中,box-sizing的值仅有content-box和border-box（firefox则额外支持padding-box）。

   + box-sizing的浏览器兼容性

     box-sizing是CSS3属性，在IE8+（包含IE8）开始支持，然而在IE8，box-sizing的值为border-box时，不能与min-width, max-width, min-height或max-height的一起使用，因为IE8对min-和max-的解析，仍是作用于content-box，不受box-sizing属性控制。

<u>元素的分类及其布局特性</u>

从元素的布局特性来分，主要可以分为三类元素：block-level（块级）元素、inline-level（行内级）元素和inline-block-level（行内块级）元素，我们可以对其下个定义：
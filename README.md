# `UML`建模之`PowerDesigner`建模


[TOC]  
`Power Designer`是`Sybase`公司的`CASE`工具集，使用它可以方便地对管理信息系统进行分析设计，它几乎包括了数据库模型设计的全过程。利用`PowerDesigner`可以制作数据流程图、概念数据模型、物理数据模型，还可以对数据仓库制作结构模型，也能对团队设计模型进行控制。

可以从这里下载 [PD16.5.zip](https://pan.baidu.com/s/1f85xtxSuIWAiYa8rVqXU4Q) ( yd66 ) 。

## 一、`UML` 之`PowerDesigner`正向工程与逆向工程

`UML`建模的正向工程和逆向工程是相对于`PowerDesigner`而言的，所以从`IDE`导入`PowerDesigner`称为逆向工程，从`PowerDesigner`导出`Java`文件称为正向工程。

### 1.1 逆向工程

![image](https://github.com/tianyalu/NeUml/raw/master/show/reverse_project.png)

#### 1.1.1 逆向工程流程

![image](https://github.com/tianyalu/NeUml/raw/master/show/reverse_process.png)

#### 1.1.2 逆向工程结果

在`IDE`中新建一些类文件，然后按照上述步骤导入类文件，就可以得到下图的结果：

![image](https://github.com/tianyalu/NeUml/raw/master/show/uml_object.png)  

点击 编辑 --> 导出图像 可以得到上图中右侧的`UNL`类图。

### 1.2 正向工程

![image](https://github.com/tianyalu/NeUml/raw/master/show/forward_project.png)  

#### 1.2.1 正向工程流程

![image](https://github.com/tianyalu/NeUml/raw/master/show/forward_process.png)  

#### 1.2.2 正向工程结果

按照上述流程操作后会得到`Java`类文件，但是文件中会有`OID`，如下所示：

```java
package com.sty.ne.uml;

/** @pdOid a6f522b4-8b92-40f4-8d71-4aaa35358bfe */
public class BaseEntity {
   /** @pdOid 80c19dfb-27e2-4550-96e0-4217253771bd */
   private int code;
   /** @pdOid 32768394-b962-4472-8a38-7633a50c7bdb */
   private String message;
   
   /** @pdOid 05de4c6b-f6c9-4d7f-ba65-ea92fd8c830b */
   public int getCode() {
       return code;
   }
   
   /** @param code
    * @pdOid 1a36ce36-6079-4d37-bf25-f1ff417193f5 */
   public void setCode(int code) {
       this.code = code;
   }
   
   /** @pdOid ff6d3091-8b7c-40f0-921e-905e5f630133 */
   public String getMessage() {
       return message;
   }
   
   /** @param message
    * @pdOid 5a136f60-c28e-4006-bca5-75af25906eb4 */
   public void setMessage(String message) {
       this.message = message;
   }

}
```

#### 1.2.3 删除`OID`

删除`oid`步骤如下：

语言--> `Edit Current Object Language` --> `Generation` -->` Options` --> `GenerateOID` ，值改为“否”就可以了。

![image](https://github.com/tianyalu/NeUml/raw/master/show/delete_oid.png)

设置之后重新正向工程就会得到类似如下的`Java`类文件：

```java
package com.sty.ne.uml;

public class BaseEntity {
   private int code;
   private String message;
   
   public int getCode() {
       return code;
   }
   
   /** @param code */
   public void setCode(int code) {
       this.code = code;
   }
   
   public String getMessage() {
       return message;
   }
   
   /** @param message */
   public void setMessage(String message) {
       this.message = message;
   }

```

## 二、关系画法

关系包括：依赖、泛化、关联、实现等。

### 2.1 依赖关系（A持有B的引用）

![image](https://github.com/tianyalu/NeUml/raw/master/show/dependence.png)



### 2.2 泛化关系（继承`extend`）

![image](https://github.com/tianyalu/NeUml/raw/master/show/generalization.png)  

### 2.3 关联关系（单向/双向/自关联）

![image](https://github.com/tianyalu/NeUml/raw/master/show/association.png)

### 2.4 实现关系（`implement`）  

![image](https://github.com/tianyalu/NeUml/raw/master/show/realization.png)  

### 2.5 聚合关系（整体和部分可以分开）  

![image](https://github.com/tianyalu/NeUml/raw/master/show/aggregation.png)  

### 2.6 组合关系（整体和部分不能分开）  

![image](https://github.com/tianyalu/NeUml/raw/master/show/composition.png)  
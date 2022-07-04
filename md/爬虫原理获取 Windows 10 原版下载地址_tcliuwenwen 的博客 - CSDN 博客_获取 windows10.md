> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/tcliuwenwen/article/details/123046950?spm=1001.2014.3001.5501)

#### 博文背景

平时的 Windows 的 ISO 都是从第三方渠道获取的，如何从官方渠道获取 Windows 的正版下载地址呢？

#### 具体操作

[https://www.microsoft.com/en-hk/software-download/windows10ISO](https://www.microsoft.com/en-hk/software-download/windows10ISO)

使用 Mac 系统的 UA 来访问  
![](https://img-blog.csdnimg.cn/7e67b6381c1c4019ac09abe6a0092954.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAdGNsaXV3ZW53ZW4=,size_20,color_FFFFFF,t_70,g_se,x_16)  
然后手动操作，最终可以获取到下载地址

自动化操作流程是：

先自行构造 [session](https://so.csdn.net/so/search?q=session&spm=1001.2101.3001.7020)-id 值，原理如下：  
![](https://img-blog.csdnimg.cn/4197c7e49c3a46179be33d5df3213e26.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAdGNsaXV3ZW53ZW4=,size_20,color_FFFFFF,t_70,g_se,x_16)  
然后访问，注意自行构造并替换 session-id 值  
[https://www.microsoft.com/en-hk/api/controls/contentinclude/html?pageId=a8f8f489-4c7f-463a-9ca6-5cff94d8d041&host=www.microsoft.com&segments=software-download%2cwindows10ISO&query=&action=getskuinformationbyproductedition&sessionId=e6acf1b4-121b-4328-adef-86097d32e295&productEditionId=2084&sdVersion=2](https://www.microsoft.com/en-hk/api/controls/contentinclude/html?pageId=a8f8f489-4c7f-463a-9ca6-5cff94d8d041&host=www.microsoft.com&segments=software-download,windows10ISO&query=&action=getskuinformationbyproductedition&sessionId=e6acf1b4-121b-4328-adef-86097d32e295&productEditionId=2084&sdVersion=2)

然后访问，注意自行构造并替换 session-id 值  
[https://www.microsoft.com/en-hk/api/controls/contentinclude/html?pageId=974edeaf-b345-4caa-a592-12dc92f6cc0a&host=www.microsoft.com&segments=software-download%2cwindows10ISO&query=&action=GetProductDownloadLinksBySku&sessionId=e6acf1b4-121b-4328-adef-86097d32e295&skuId=13372&language=Chinese%20(Simplified)&sdVersion=2](https://www.microsoft.com/en-hk/api/controls/contentinclude/html?pageId=974edeaf-b345-4caa-a592-12dc92f6cc0a&host=www.microsoft.com&segments=software-download,windows10ISO&query=&action=GetProductDownloadLinksBySku&sessionId=e6acf1b4-121b-4328-adef-86097d32e295&skuId=13372&language=Chinese%20%28Simplified%29&sdVersion=2)

最终效果  
![](https://img-blog.csdnimg.cn/ba7f8b184d36409fa0b89e3c0179a465.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAdGNsaXV3ZW53ZW4=,size_20,color_FFFFFF,t_70,g_se,x_16)  
获得下载地址：  
[https://software.download.prss.microsoft.com/sg/Win10_21H2_Chinese(Simplified)_x64.iso](https://software.download.prss.microsoft.com/sg/Win10_21H2_Chinese%28Simplified%29_x64.iso)
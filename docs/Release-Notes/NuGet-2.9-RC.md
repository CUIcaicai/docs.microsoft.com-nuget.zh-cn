---
title: "NuGet 2.9 RC 发行说明 |Microsoft 文档"
author: karann-msft
ms.author: karann-msft
manager: ghogen
ms.date: 11/11/2016
ms.topic: article
ms.prod: nuget
ms.technology: 
ms.assetid: 04d76a22-63b0-41d1-9c27-799f4b35058f
description: "包括已知的问题、 bug 修复、 增加的功能，以及 DCRs NuGet 2.9 RC 的发行说明。"
keywords: "NuGet 2.9 RC 发行说明，bug 修复的已知问题，添加了一些功能，DCRs"
ms.reviewer:
- karann-msft
- unniravindranathan
ms.openlocfilehash: 64b4cd17394ddb902c7101b9117039f381dc8488
ms.sourcegitcommit: d0ba99bfe019b779b75731bafdca8a37e35ef0d9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2017
---
# <a name="nuget-29-rc-release-notes"></a>NuGet 2.9 RC 发行说明

[NuGet 2.8.7 发行说明](../release-notes/nuget-2.8.7.md) | [NuGet 3.0 预览版发行说明](../release-notes/nuget-3.0-preview.md)

NuGet 2.9 发布于 2015 年 9 月 10 日为 2.8.7 的更新 Visual Studio 2012 和 2013 VSIX。

### <a name="updates-in-this-release"></a>在此版本的更新

* 现在跳过处理包，如果其包含`.nuspec`文档格式不正确- [PR8](https://github.com/NuGet/NuGet2/pull/8)
* 更正的 Unix/Linux 方案-\r\n multipartwebrequest 处理[776](https://github.com/NuGet/Home/issues/776)
* 更正与在 Visual Studio 2013 Community 版本-生成事件的集成[1180年](https://github.com/NuGet/Home/issues/1180)


在此版本的修补程序的完整列表可以在 GitHub 上找到[2.8.8 里程碑](https://github.com/NuGet/Home/issues?q=milestone%3A2.8.8+is%3Aclosed)
---
title: 速率限制，NuGet API
description: NuGet Api 将强制实施速率限制以防止滥用行为。
author: cmanu
ms.author: cmanu
manager: skofman
ms.date: 03/20/2018
ms.topic: reference
ms.reviewer:
- skofman
- anangaur
- kraigb
ms.openlocfilehash: e236d685a700d0f47480336cece8edfd44c28863
ms.sourcegitcommit: 68c8a494a11c892ac671fec3170ba7be97fb044d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="rate-limits"></a><span data-ttu-id="af673-103">速率限制</span><span class="sxs-lookup"><span data-stu-id="af673-103">Rate Limits</span></span>

<span data-ttu-id="af673-104">NuGet.org API 强制实施速率限制以防止滥用行为。</span><span class="sxs-lookup"><span data-stu-id="af673-104">The NuGet.org API enforces rate limiting to prevent abuse.</span></span> <span data-ttu-id="af673-105">超过速率限制的请求将返回以下错误：</span><span class="sxs-lookup"><span data-stu-id="af673-105">Requests that exceed the rate limit return the following error:</span></span> 

  ~~~
    {
      "statusCode": 429,
      "message": "Rate limit is exceeded. Try again in 56 seconds."
    }
  ~~~

<span data-ttu-id="af673-106">下表列出 NuGet.org API 速率限制。</span><span class="sxs-lookup"><span data-stu-id="af673-106">The following tables list the rate limits for the NuGet.org API.</span></span>

## <a name="package-search"></a><span data-ttu-id="af673-107">包搜索</span><span class="sxs-lookup"><span data-stu-id="af673-107">Package search</span></span>

> [!Note]
> <span data-ttu-id="af673-108">我们建议使用 NuGet.org 的[V3 Api](https://docs.microsoft.com/nuget/api/search-query-service-resource)搜索高性能且不具有任何将限制当前。</span><span class="sxs-lookup"><span data-stu-id="af673-108">We recommend using NuGet.org's [V3 APIs](https://docs.microsoft.com/nuget/api/search-query-service-resource) for search that are performant and do not have any limit currently.</span></span> <span data-ttu-id="af673-109">V1 和 V2 搜索 Api，followins 限制适用：</span><span class="sxs-lookup"><span data-stu-id="af673-109">For V1 and V2 search APIs, the followins limits apply:</span></span>


| <span data-ttu-id="af673-110">API</span><span class="sxs-lookup"><span data-stu-id="af673-110">API</span></span> | <span data-ttu-id="af673-111">限制类型</span><span class="sxs-lookup"><span data-stu-id="af673-111">Limit Type</span></span> | <span data-ttu-id="af673-112">限制值</span><span class="sxs-lookup"><span data-stu-id="af673-112">Limit Value</span></span> | <span data-ttu-id="af673-113">API 用例</span><span class="sxs-lookup"><span data-stu-id="af673-113">API usecase</span></span> |
|:---|:---|:---|:---|
<span data-ttu-id="af673-114">**获取** `/api/v1/Packages`</span><span class="sxs-lookup"><span data-stu-id="af673-114">**GET** `/api/v1/Packages`</span></span> | <span data-ttu-id="af673-115">IP</span><span class="sxs-lookup"><span data-stu-id="af673-115">IP</span></span> | <span data-ttu-id="af673-116">1000 / 分钟</span><span class="sxs-lookup"><span data-stu-id="af673-116">1000 / minute</span></span> | <span data-ttu-id="af673-117">查询通过 v1 OData 的 NuGet 包元数据`Packages`集合</span><span class="sxs-lookup"><span data-stu-id="af673-117">Query NuGet package metadata via v1 OData `Packages` collection</span></span> |
<span data-ttu-id="af673-118">**获取** `/api/v1/Search()`</span><span class="sxs-lookup"><span data-stu-id="af673-118">**GET** `/api/v1/Search()`</span></span> | <span data-ttu-id="af673-119">IP</span><span class="sxs-lookup"><span data-stu-id="af673-119">IP</span></span> | <span data-ttu-id="af673-120">3000 / 分钟</span><span class="sxs-lookup"><span data-stu-id="af673-120">3000 / minute</span></span> | <span data-ttu-id="af673-121">搜索通过 v1 搜索终结点的 NuGet 包</span><span class="sxs-lookup"><span data-stu-id="af673-121">Search for NuGet packages via v1 Search endpoint</span></span> | 
<span data-ttu-id="af673-122">**获取** `/api/v2/Packages`</span><span class="sxs-lookup"><span data-stu-id="af673-122">**GET** `/api/v2/Packages`</span></span> | <span data-ttu-id="af673-123">IP</span><span class="sxs-lookup"><span data-stu-id="af673-123">IP</span></span> | <span data-ttu-id="af673-124">20000 / 分钟</span><span class="sxs-lookup"><span data-stu-id="af673-124">20000 / minute</span></span> | <span data-ttu-id="af673-125">查询通过 v2 OData 的 NuGet 包元数据`Packages`集合</span><span class="sxs-lookup"><span data-stu-id="af673-125">Query NuGet package metadata via v2 OData `Packages` collection</span></span> | 
<span data-ttu-id="af673-126">**获取** `/api/v2/Packages/$count`</span><span class="sxs-lookup"><span data-stu-id="af673-126">**GET** `/api/v2/Packages/$count`</span></span> | <span data-ttu-id="af673-127">IP</span><span class="sxs-lookup"><span data-stu-id="af673-127">IP</span></span> | <span data-ttu-id="af673-128">100 / 分钟</span><span class="sxs-lookup"><span data-stu-id="af673-128">100 / minute</span></span> | <span data-ttu-id="af673-129">查询通过 v2 OData 的 NuGet 包计数`Packages`集合</span><span class="sxs-lookup"><span data-stu-id="af673-129">Query NuGet package count via v2 OData `Packages` collection</span></span> | 

## <a name="package-push-and-unlist"></a><span data-ttu-id="af673-130">包推送和不列出</span><span class="sxs-lookup"><span data-stu-id="af673-130">Package Push and Unlist</span></span>

| <span data-ttu-id="af673-131">API</span><span class="sxs-lookup"><span data-stu-id="af673-131">API</span></span> | <span data-ttu-id="af673-132">限制类型</span><span class="sxs-lookup"><span data-stu-id="af673-132">Limit Type</span></span> | <span data-ttu-id="af673-133">限制值</span><span class="sxs-lookup"><span data-stu-id="af673-133">Limit Value</span></span> | <span data-ttu-id="af673-134">API 用例</span><span class="sxs-lookup"><span data-stu-id="af673-134">API usecase</span></span> | 
|:---|:---|:---|:--- |
<span data-ttu-id="af673-135">**PUT** `/api/v2/package`</span><span class="sxs-lookup"><span data-stu-id="af673-135">**PUT** `/api/v2/package`</span></span> | <span data-ttu-id="af673-136">API 密钥</span><span class="sxs-lookup"><span data-stu-id="af673-136">API Key</span></span> | <span data-ttu-id="af673-137">100 / 分钟</span><span class="sxs-lookup"><span data-stu-id="af673-137">100 / minute</span></span> | <span data-ttu-id="af673-138">上载新 NuGet 包 （版本） 通过 v2 推送终结点</span><span class="sxs-lookup"><span data-stu-id="af673-138">Upload a new NuGet package (version) via v2 push endpoint</span></span> 
<span data-ttu-id="af673-139">**删除** `/api/v2/package/{id}/{version}`</span><span class="sxs-lookup"><span data-stu-id="af673-139">**DELETE** `/api/v2/package/{id}/{version}`</span></span> | <span data-ttu-id="af673-140">API 密钥</span><span class="sxs-lookup"><span data-stu-id="af673-140">API Key</span></span> | <span data-ttu-id="af673-141">100 / 分钟</span><span class="sxs-lookup"><span data-stu-id="af673-141">100 / minute</span></span> | <span data-ttu-id="af673-142">不列出通过 v2 终结点的 NuGet 包 （版本）</span><span class="sxs-lookup"><span data-stu-id="af673-142">Unlist a NuGet package (version) via v2 endpoint</span></span> 
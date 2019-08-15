---
ms.openlocfilehash: e8949e9964ed19d342df53f08f59bb0f89e5feb0
ms.sourcegitcommit: 5aa49478dc466c67db5c3edda7c6ce8dcd8ae033
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817481"
---
<span data-ttu-id="cf68b-101">包标识符和版本号是项目中最重要的两个值，因为它们唯一标识包中包含的确切代码。</span><span class="sxs-lookup"><span data-stu-id="cf68b-101">The package identifier and the version number are the two most important values in the project because they uniquely identify the exact code that's contained in the package.</span></span>

<span data-ttu-id="cf68b-102">**针对包标识符的最佳做法：**</span><span class="sxs-lookup"><span data-stu-id="cf68b-102">**Best practices for the package identifier:**</span></span>

- <span data-ttu-id="cf68b-103">**唯一性**：标识符必须在 nuget.org 或托管包的任意库中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="cf68b-103">**Uniqueness**: The identifier must be unique across nuget.org or whatever gallery hosts the package.</span></span> <span data-ttu-id="cf68b-104">确定标识符之前，请搜索适用库以检查该名称是否已使用。</span><span class="sxs-lookup"><span data-stu-id="cf68b-104">Before deciding on an identifier, search the applicable gallery to check if the name is already in use.</span></span> <span data-ttu-id="cf68b-105">为了避免冲突，最好使用公司名作为标识符的第一部分（例如 `Contoso.`）。</span><span class="sxs-lookup"><span data-stu-id="cf68b-105">To avoid conflicts, a good pattern is to use your company name as the first part of the identifier, such as `Contoso.`.</span></span>
- <span data-ttu-id="cf68b-106">**类似于命名空间的名称**：遵循类似于 .NET 中命名空间的模式，使用点表示法（而不是连字符）。</span><span class="sxs-lookup"><span data-stu-id="cf68b-106">**Namespace-like names**: Follow a pattern similar to namespaces in .NET, using dot notation instead of hyphens.</span></span> <span data-ttu-id="cf68b-107">例如，使用 `Contoso.Utility.UsefulStuff` 而不是 `Contoso-Utility-UsefulStuff` 或 `Contoso_Utility_UsefulStuff`。</span><span class="sxs-lookup"><span data-stu-id="cf68b-107">For example, use `Contoso.Utility.UsefulStuff` rather than `Contoso-Utility-UsefulStuff` or `Contoso_Utility_UsefulStuff`.</span></span> <span data-ttu-id="cf68b-108">当包标识符与代码中使用的命名空间相匹配时，这个方法也很有用。</span><span class="sxs-lookup"><span data-stu-id="cf68b-108">Consumers also find it helpful when the package identifier matches the namespaces used in the code.</span></span>
- <span data-ttu-id="cf68b-109">**示例包**：如果生成展示如何使用另一个包的示例代码包，请附加 `.Sample` 作为标识符的后缀，就像 `Contoso.Utility.UsefulStuff.Sample` 中一样。</span><span class="sxs-lookup"><span data-stu-id="cf68b-109">**Sample Packages**: If you produce a package of sample code that demonstrates how to use another package, attach `.Sample` as a suffix to the identifier, as in `Contoso.Utility.UsefulStuff.Sample`.</span></span> <span data-ttu-id="cf68b-110">（当然，示例包会在其他包上有依赖项。）创建示例包时，请在 `<IncludeAssets>` 中使用 `contentFiles` 值。</span><span class="sxs-lookup"><span data-stu-id="cf68b-110">(The sample package would of course have a dependency on the other package.) When creating a sample package, use the `contentFiles` value in `<IncludeAssets>`.</span></span> <span data-ttu-id="cf68b-111">在 `content` 文件夹中，在名为 `\Samples\<identifier>` 的文件夹中排列示例代码，与 `\Samples\Contoso.Utility.UsefulStuff.Sample` 中相似。</span><span class="sxs-lookup"><span data-stu-id="cf68b-111">In the `content` folder, arrange the sample code in a folder called `\Samples\<identifier>` as in `\Samples\Contoso.Utility.UsefulStuff.Sample`.</span></span>

<span data-ttu-id="cf68b-112">**针对包版本的最佳做法：**</span><span class="sxs-lookup"><span data-stu-id="cf68b-112">**Best practices for the package version:**</span></span>

- <span data-ttu-id="cf68b-113">一般情况下，将包的版本设置为与项目（或程序集）相匹配，但这不是必须的。</span><span class="sxs-lookup"><span data-stu-id="cf68b-113">In general, set the version of the package to match the project (or assembly), though this is not strictly required.</span></span> <span data-ttu-id="cf68b-114">如果将包限制为单个程序集，那么这是一个简单的问题。</span><span class="sxs-lookup"><span data-stu-id="cf68b-114">This is a simple matter when you limit a package to a single assembly.</span></span> <span data-ttu-id="cf68b-115">总的来说，请记住解析依赖项时，NuGet 自己处理包版本而不是程序集版本。</span><span class="sxs-lookup"><span data-stu-id="cf68b-115">Overall, remember that NuGet itself deals with package versions when resolving dependencies, not assembly versions.</span></span>
- <span data-ttu-id="cf68b-116">使用非标准版本方案时，请确保考虑使用 NuGet 版本控制规则，如[包版本控制](../../reference/package-versioning.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="cf68b-116">When using a non-standard version scheme, be sure to consider the NuGet versioning rules as explained in [Package versioning](../../reference/package-versioning.md).</span></span> <span data-ttu-id="cf68b-117">NuGet 主要与 [semver 2 兼容](../../reference/package-versioning.md#semantic-versioning-200)。</span><span class="sxs-lookup"><span data-stu-id="cf68b-117">NuGet is mostly [semver 2 compliant](../../reference/package-versioning.md#semantic-versioning-200).</span></span>

> <span data-ttu-id="cf68b-118">有关依赖项解析的信息，请参阅[使用 PackageReference 的依赖项解析](../../consume-packages/dependency-resolution.md#dependency-resolution-with-packagereference)。</span><span class="sxs-lookup"><span data-stu-id="cf68b-118">For information on dependency resolution, see [Dependency resolution with PackageReference](../../consume-packages/dependency-resolution.md#dependency-resolution-with-packagereference).</span></span> <span data-ttu-id="cf68b-119">对于可能有助于更好地理解版本控制的较旧信息，请参阅此系列博客文章。</span><span class="sxs-lookup"><span data-stu-id="cf68b-119">For older information that may also be helpful to better understand versioning, see this series of blog posts.</span></span>
>
> - [<span data-ttu-id="cf68b-120">第 1 部分：解决 DLL 地狱</span><span class="sxs-lookup"><span data-stu-id="cf68b-120">Part 1: Taking on DLL Hell</span></span>](http://blog.davidebbo.com/2011/01/nuget-versioning-part-1-taking-on-dll.html)
> - [<span data-ttu-id="cf68b-121">第 2 部分：核心算法</span><span class="sxs-lookup"><span data-stu-id="cf68b-121">Part 2: The core algorithm</span></span>](http://blog.davidebbo.com/2011/01/nuget-versioning-part-2-core-algorithm.html)
> - [<span data-ttu-id="cf68b-122">第 3 部分：通过绑定重定向实现统一</span><span class="sxs-lookup"><span data-stu-id="cf68b-122">Part 3: Unification via Binding Redirects</span></span>](http://blog.davidebbo.com/2011/01/nuget-versioning-part-3-unification-via.html)
---
ms.openlocfilehash: 6af8e97423c04abca25feb8d77ea9ab6e198a4f0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620331"
---
### <a name="objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a><span data-ttu-id="1e7fd-101">ObjectContext.Translate e ObjectContext.ExecuteStoreQuery ora supportano il tipo enum</span><span class="sxs-lookup"><span data-stu-id="1e7fd-101">ObjectContext.Translate and ObjectContext.ExecuteStoreQuery now support enum type</span></span>

#### <a name="details"></a><span data-ttu-id="1e7fd-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1e7fd-102">Details</span></span>

<span data-ttu-id="1e7fd-103">In .NET Framework 4.0 il parametro generico <code>T</code> dei metodi <code>ObjectContext.Translate</code> e <code>ObjectContext.ExecuteStoreQuery</code> non può essere un tipo enum.</span><span class="sxs-lookup"><span data-stu-id="1e7fd-103">In .NET Framework 4.0, the generic parameter <code>T</code> of <code>ObjectContext.Translate</code> and <code>ObjectContext.ExecuteStoreQuery</code> methods could not be an enum.</span></span> <span data-ttu-id="1e7fd-104">Questo scenario è ora supportato.</span><span class="sxs-lookup"><span data-stu-id="1e7fd-104">That scenario is now supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1e7fd-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="1e7fd-105">Suggestion</span></span>

<span data-ttu-id="1e7fd-106">Se si chiama Translate o ExecuteStoreQuery su un tipo enum in .NET Framework 4.0, viene restituito '0'.</span><span class="sxs-lookup"><span data-stu-id="1e7fd-106">If Translate or ExecuteStoreQuery was called on an enum type in .NET Framework 4.0, '0' was returned.</span></span> <span data-ttu-id="1e7fd-107">Se tale comportamento è quello desiderabile, le chiamate devono essere sostituite con una costante 0 (o l'enum equivalente).</span><span class="sxs-lookup"><span data-stu-id="1e7fd-107">If that behavior was desirable, the calls should be replaced with a constant 0 (or the enum equivalent of it).</span></span>

| <span data-ttu-id="1e7fd-108">Nome</span><span class="sxs-lookup"><span data-stu-id="1e7fd-108">Name</span></span>    | <span data-ttu-id="1e7fd-109">Valore</span><span class="sxs-lookup"><span data-stu-id="1e7fd-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1e7fd-110">Scope</span><span class="sxs-lookup"><span data-stu-id="1e7fd-110">Scope</span></span>   |<span data-ttu-id="1e7fd-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1e7fd-111">Edge</span></span>|
|<span data-ttu-id="1e7fd-112">Version</span><span class="sxs-lookup"><span data-stu-id="1e7fd-112">Version</span></span>|<span data-ttu-id="1e7fd-113">4.5</span><span class="sxs-lookup"><span data-stu-id="1e7fd-113">4.5</span></span>|
|<span data-ttu-id="1e7fd-114">Type</span><span class="sxs-lookup"><span data-stu-id="1e7fd-114">Type</span></span>|<span data-ttu-id="1e7fd-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="1e7fd-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="1e7fd-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="1e7fd-116">Affected APIs</span></span>

-<xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])?displayProperty=nameWithType></li></ul>|

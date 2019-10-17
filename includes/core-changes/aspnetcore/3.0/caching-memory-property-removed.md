---
ms.openlocfilehash: 7d40324e6b0bc4afab9dd39b236f0909f360cc9b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394137"
---
### <a name="caching-compactonmemorypressure-property-removed"></a><span data-ttu-id="e0e98-101">Caching: la proprietà CompactOnMemoryPressure è stata rimossa</span><span class="sxs-lookup"><span data-stu-id="e0e98-101">Caching: CompactOnMemoryPressure property removed</span></span>

<span data-ttu-id="e0e98-102">La versione di ASP.NET Core 3,0 ha rimosso le [API MemoryCacheOptions obsolete](https://github.com/aspnet/Extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18).</span><span class="sxs-lookup"><span data-stu-id="e0e98-102">The ASP.NET Core 3.0 release removed the [obsolete MemoryCacheOptions APIs](https://github.com/aspnet/Extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18).</span></span>

#### <a name="change-description"></a><span data-ttu-id="e0e98-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="e0e98-103">Change description</span></span>

<span data-ttu-id="e0e98-104">Questa modifica è un completamento di [ASPNET/Caching # 221](https://github.com/aspnet/Caching/issues/221).</span><span class="sxs-lookup"><span data-stu-id="e0e98-104">This change is a follow-up to [aspnet/Caching#221](https://github.com/aspnet/Caching/issues/221).</span></span> <span data-ttu-id="e0e98-105">Per informazioni, vedere [ASPNET/Extensions # 1062](https://github.com/aspnet/Extensions/issues/1062).</span><span class="sxs-lookup"><span data-stu-id="e0e98-105">For discussion, see [aspnet/Extensions#1062](https://github.com/aspnet/Extensions/issues/1062).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e0e98-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="e0e98-106">Version introduced</span></span>

<span data-ttu-id="e0e98-107">3.0</span><span class="sxs-lookup"><span data-stu-id="e0e98-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="e0e98-108">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="e0e98-108">Old behavior</span></span>

<span data-ttu-id="e0e98-109">la proprietà `MemoryCacheOptions.CompactOnMemoryPressure` era disponibile.</span><span class="sxs-lookup"><span data-stu-id="e0e98-109">`MemoryCacheOptions.CompactOnMemoryPressure` property was available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="e0e98-110">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="e0e98-110">New behavior</span></span>

<span data-ttu-id="e0e98-111">La proprietà `MemoryCacheOptions.CompactOnMemoryPressure` è stata rimossa.</span><span class="sxs-lookup"><span data-stu-id="e0e98-111">The `MemoryCacheOptions.CompactOnMemoryPressure` property has been removed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e0e98-112">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="e0e98-112">Reason for change</span></span>

<span data-ttu-id="e0e98-113">La compattazione automatica della cache ha causato problemi.</span><span class="sxs-lookup"><span data-stu-id="e0e98-113">Automatically compacting the cache caused problems.</span></span> <span data-ttu-id="e0e98-114">Per evitare comportamenti imprevisti, la cache deve essere compattata solo quando è necessario.</span><span class="sxs-lookup"><span data-stu-id="e0e98-114">To avoid unexpected behavior, the cache should only be compacted when needed.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e0e98-115">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="e0e98-115">Recommended action</span></span>

<span data-ttu-id="e0e98-116">Per compattare la cache, abbreviata in `MemoryCache` e chiamare `Compact` quando necessario.</span><span class="sxs-lookup"><span data-stu-id="e0e98-116">To compact the cache, downcast to `MemoryCache` and call `Compact` when needed.</span></span>

#### <a name="category"></a><span data-ttu-id="e0e98-117">Category</span><span class="sxs-lookup"><span data-stu-id="e0e98-117">Category</span></span>

<span data-ttu-id="e0e98-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e0e98-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e0e98-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="e0e98-119">Affected APIs</span></span>

<xref:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure`

-->

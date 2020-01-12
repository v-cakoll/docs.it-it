---
ms.openlocfilehash: 2c1362d6982206b14475f77700add0bae61da173
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901960"
---
### <a name="caching-compactonmemorypressure-property-removed"></a><span data-ttu-id="28d36-101">Caching: la proprietà CompactOnMemoryPressure è stata rimossa</span><span class="sxs-lookup"><span data-stu-id="28d36-101">Caching: CompactOnMemoryPressure property removed</span></span>

<span data-ttu-id="28d36-102">La versione di ASP.NET Core 3,0 ha rimosso le [API MemoryCacheOptions obsolete](https://github.com/dotnet/extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18).</span><span class="sxs-lookup"><span data-stu-id="28d36-102">The ASP.NET Core 3.0 release removed the [obsolete MemoryCacheOptions APIs](https://github.com/dotnet/extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18).</span></span>

#### <a name="change-description"></a><span data-ttu-id="28d36-103">Descrizione delle modifiche</span><span class="sxs-lookup"><span data-stu-id="28d36-103">Change description</span></span>

<span data-ttu-id="28d36-104">Questa modifica è un completamento di [ASPNET/Caching # 221](https://github.com/aspnet/Caching/issues/221).</span><span class="sxs-lookup"><span data-stu-id="28d36-104">This change is a follow-up to [aspnet/Caching#221](https://github.com/aspnet/Caching/issues/221).</span></span> <span data-ttu-id="28d36-105">Per informazioni, vedere [DotNet/Extensions # 1062](https://github.com/dotnet/extensions/issues/1062).</span><span class="sxs-lookup"><span data-stu-id="28d36-105">For discussion, see [dotnet/extensions#1062](https://github.com/dotnet/extensions/issues/1062).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="28d36-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="28d36-106">Version introduced</span></span>

<span data-ttu-id="28d36-107">3.0</span><span class="sxs-lookup"><span data-stu-id="28d36-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="28d36-108">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="28d36-108">Old behavior</span></span>

<span data-ttu-id="28d36-109">Proprietà `MemoryCacheOptions.CompactOnMemoryPressure` disponibile.</span><span class="sxs-lookup"><span data-stu-id="28d36-109">`MemoryCacheOptions.CompactOnMemoryPressure` property was available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="28d36-110">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="28d36-110">New behavior</span></span>

<span data-ttu-id="28d36-111">La proprietà `MemoryCacheOptions.CompactOnMemoryPressure` è stata rimossa.</span><span class="sxs-lookup"><span data-stu-id="28d36-111">The `MemoryCacheOptions.CompactOnMemoryPressure` property has been removed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="28d36-112">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="28d36-112">Reason for change</span></span>

<span data-ttu-id="28d36-113">La compattazione automatica della cache ha causato problemi.</span><span class="sxs-lookup"><span data-stu-id="28d36-113">Automatically compacting the cache caused problems.</span></span> <span data-ttu-id="28d36-114">Per evitare comportamenti imprevisti, la cache deve essere compattata solo quando è necessario.</span><span class="sxs-lookup"><span data-stu-id="28d36-114">To avoid unexpected behavior, the cache should only be compacted when needed.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="28d36-115">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="28d36-115">Recommended action</span></span>

<span data-ttu-id="28d36-116">Per compattare la cache, abbreviata per `MemoryCache` e chiamare `Compact` quando necessario.</span><span class="sxs-lookup"><span data-stu-id="28d36-116">To compact the cache, downcast to `MemoryCache` and call `Compact` when needed.</span></span>

#### <a name="category"></a><span data-ttu-id="28d36-117">Categoria</span><span class="sxs-lookup"><span data-stu-id="28d36-117">Category</span></span>

<span data-ttu-id="28d36-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="28d36-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="28d36-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="28d36-119">Affected APIs</span></span>

<xref:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure`

-->

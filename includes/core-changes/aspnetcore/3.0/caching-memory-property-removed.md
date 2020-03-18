---
ms.openlocfilehash: 2c1362d6982206b14475f77700add0bae61da173
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901960"
---
### <a name="caching-compactonmemorypressure-property-removed"></a><span data-ttu-id="4ff1e-101">Memorizzazione nella cache: proprietà CompactOnMemoryPressure rimossaCaching: CompactOnMemoryPressure property removed</span><span class="sxs-lookup"><span data-stu-id="4ff1e-101">Caching: CompactOnMemoryPressure property removed</span></span>

<span data-ttu-id="4ff1e-102">La versione ASP.NET Core 3.0 ha rimosso le [API MemoryCacheOptions obsolete.](https://github.com/dotnet/extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18)</span><span class="sxs-lookup"><span data-stu-id="4ff1e-102">The ASP.NET Core 3.0 release removed the [obsolete MemoryCacheOptions APIs](https://github.com/dotnet/extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18).</span></span>

#### <a name="change-description"></a><span data-ttu-id="4ff1e-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="4ff1e-103">Change description</span></span>

<span data-ttu-id="4ff1e-104">Questa modifica è un follow-up di [aspnet/Caching-221](https://github.com/aspnet/Caching/issues/221).</span><span class="sxs-lookup"><span data-stu-id="4ff1e-104">This change is a follow-up to [aspnet/Caching#221](https://github.com/aspnet/Caching/issues/221).</span></span> <span data-ttu-id="4ff1e-105">Per una discussione, vedere [dotnet/extensions.](https://github.com/dotnet/extensions/issues/1062)</span><span class="sxs-lookup"><span data-stu-id="4ff1e-105">For discussion, see [dotnet/extensions#1062](https://github.com/dotnet/extensions/issues/1062).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4ff1e-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="4ff1e-106">Version introduced</span></span>

<span data-ttu-id="4ff1e-107">3.0</span><span class="sxs-lookup"><span data-stu-id="4ff1e-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="4ff1e-108">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="4ff1e-108">Old behavior</span></span>

<span data-ttu-id="4ff1e-109">`MemoryCacheOptions.CompactOnMemoryPressure`proprietà era disponibile.</span><span class="sxs-lookup"><span data-stu-id="4ff1e-109">`MemoryCacheOptions.CompactOnMemoryPressure` property was available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="4ff1e-110">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="4ff1e-110">New behavior</span></span>

<span data-ttu-id="4ff1e-111">La `MemoryCacheOptions.CompactOnMemoryPressure` proprietà è stata rimossa.</span><span class="sxs-lookup"><span data-stu-id="4ff1e-111">The `MemoryCacheOptions.CompactOnMemoryPressure` property has been removed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="4ff1e-112">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="4ff1e-112">Reason for change</span></span>

<span data-ttu-id="4ff1e-113">La compattazione automatica della cache ha causato problemi.</span><span class="sxs-lookup"><span data-stu-id="4ff1e-113">Automatically compacting the cache caused problems.</span></span> <span data-ttu-id="4ff1e-114">Per evitare comportamenti imprevisti, la cache deve essere compattata solo quando necessario.</span><span class="sxs-lookup"><span data-stu-id="4ff1e-114">To avoid unexpected behavior, the cache should only be compacted when needed.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4ff1e-115">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="4ff1e-115">Recommended action</span></span>

<span data-ttu-id="4ff1e-116">Per compattare la cache, eseguire il downcast `MemoryCache` e chiamare `Compact` quando necessario.</span><span class="sxs-lookup"><span data-stu-id="4ff1e-116">To compact the cache, downcast to `MemoryCache` and call `Compact` when needed.</span></span>

#### <a name="category"></a><span data-ttu-id="4ff1e-117">Category</span><span class="sxs-lookup"><span data-stu-id="4ff1e-117">Category</span></span>

<span data-ttu-id="4ff1e-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4ff1e-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4ff1e-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="4ff1e-119">Affected APIs</span></span>

<xref:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure`

-->

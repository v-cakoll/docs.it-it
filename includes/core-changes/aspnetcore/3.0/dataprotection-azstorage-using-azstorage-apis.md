---
ms.openlocfilehash: db70596552ffd699156e1b7a55cb1e944596f077
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901692"
---
### <a name="data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis"></a><span data-ttu-id="91723-101">Protezione dei dati: DataProtection.AzureStorage usa le nuove API di Archiviazione di AzureData Protection: DataProtection.AzureStorage uses new Azure Storage APIs</span><span class="sxs-lookup"><span data-stu-id="91723-101">Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs</span></span>

<span data-ttu-id="91723-102"><xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName>dipende dalle [librerie di Archiviazione di Azure](https://github.com/Azure/azure-storage-net).</span><span class="sxs-lookup"><span data-stu-id="91723-102"><xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName> depends on the [Azure Storage libraries](https://github.com/Azure/azure-storage-net).</span></span> <span data-ttu-id="91723-103">Queste librerie hanno rinominato i relativi assembly, pacchetti e spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="91723-103">These libraries renamed their assemblies, packages, and namespaces.</span></span> <span data-ttu-id="91723-104">A partire da ASP.NET `Microsoft.AspNetCore.DataProtection.AzureStorage` Core 3.0, usa le nuove `Microsoft.Azure.Storage.`API e i pacchetti con prefisso.</span><span class="sxs-lookup"><span data-stu-id="91723-104">Starting in ASP.NET Core 3.0, `Microsoft.AspNetCore.DataProtection.AzureStorage` uses the new `Microsoft.Azure.Storage.`-prefixed APIs and packages.</span></span>

<span data-ttu-id="91723-105">Per domande sulle API di Archiviazione <https://github.com/Azure/azure-storage-net>di Azure, usare .</span><span class="sxs-lookup"><span data-stu-id="91723-105">For questions about the Azure Storage APIs, use <https://github.com/Azure/azure-storage-net>.</span></span> <span data-ttu-id="91723-106">Per una discussione su questo problema, vedere [dotnet/aspnetcore-8472](https://github.com/dotnet/aspnetcore/issues/8472).</span><span class="sxs-lookup"><span data-stu-id="91723-106">For discussion on this issue, see [dotnet/aspnetcore#8472](https://github.com/dotnet/aspnetcore/issues/8472).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="91723-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="91723-107">Version introduced</span></span>

<span data-ttu-id="91723-108">3.0</span><span class="sxs-lookup"><span data-stu-id="91723-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="91723-109">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="91723-109">Old behavior</span></span>

<span data-ttu-id="91723-110">Il pacchetto fa `WindowsAzure.Storage` riferimento al pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="91723-110">The package referenced the `WindowsAzure.Storage` NuGet package.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="91723-111">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="91723-111">New behavior</span></span>

<span data-ttu-id="91723-112">Il pacchetto `Microsoft.Azure.Storage.Blob` fa riferimento al pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="91723-112">The package references the `Microsoft.Azure.Storage.Blob` NuGet package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="91723-113">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="91723-113">Reason for change</span></span>

<span data-ttu-id="91723-114">Questa modifica `Microsoft.AspNetCore.DataProtection.AzureStorage` consente di eseguire la migrazione ai pacchetti di Archiviazione di Azure consigliati.</span><span class="sxs-lookup"><span data-stu-id="91723-114">This change allows `Microsoft.AspNetCore.DataProtection.AzureStorage` to migrate to the recommended Azure Storage packages.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="91723-115">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="91723-115">Recommended action</span></span>

<span data-ttu-id="91723-116">Se è ancora necessario usare le API di Archiviazione di Azure precedenti con ASP.NET Core 3.0, aggiungere una dipendenza diretta al pacchetto [WindowsAzure.Storage.If](https://www.nuget.org/packages/WindowsAzure.Storage/) you still need to use the older Azure Storage APIs with ASP.NET Core 3.0, add a direct dependency to the WindowsAzure.Storage package.</span><span class="sxs-lookup"><span data-stu-id="91723-116">If you still need to use the older Azure Storage APIs with ASP.NET Core 3.0, add a direct dependency to the [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) package.</span></span> <span data-ttu-id="91723-117">Questo pacchetto può essere `Microsoft.Azure.Storage` installato insieme alle nuove API.</span><span class="sxs-lookup"><span data-stu-id="91723-117">This package can be installed alongside the new `Microsoft.Azure.Storage` APIs.</span></span>

<span data-ttu-id="91723-118">In molti casi, l'aggiornamento `using` comporta solo la modifica delle istruzioni per utilizzare i nuovi spazi dei nomi:In many cases, the upgrade only involves changing the statements to use the new namespaces:</span><span class="sxs-lookup"><span data-stu-id="91723-118">In many cases, the upgrade only involves changing the `using` statements to use the new namespaces:</span></span>

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
+ using Microsoft.Azure.Storage;
+ using Microsoft.Azure.Storage.Blob;
```

#### <a name="category"></a><span data-ttu-id="91723-119">Category</span><span class="sxs-lookup"><span data-stu-id="91723-119">Category</span></span>

<span data-ttu-id="91723-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="91723-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="91723-121">API interessate</span><span class="sxs-lookup"><span data-stu-id="91723-121">Affected APIs</span></span>

<span data-ttu-id="91723-122">nessuno</span><span class="sxs-lookup"><span data-stu-id="91723-122">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->

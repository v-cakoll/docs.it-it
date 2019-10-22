---
ms.openlocfilehash: f103c96588bae167216d09a82973a4a7abfb5cc3
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394300"
---
### <a name="data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis"></a><span data-ttu-id="77300-101">Protezione dei dati: dataprotection. AzureStorage usa le nuove API di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="77300-101">Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs</span></span>

<span data-ttu-id="77300-102"><xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName> dipende dalle librerie di [archiviazione di Azure](https://github.com/Azure/azure-storage-net).</span><span class="sxs-lookup"><span data-stu-id="77300-102"><xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName> depends on the [Azure Storage libraries](https://github.com/Azure/azure-storage-net).</span></span> <span data-ttu-id="77300-103">Queste librerie hanno rinominato gli assembly, i pacchetti e gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="77300-103">These libraries renamed their assemblies, packages, and namespaces.</span></span> <span data-ttu-id="77300-104">A partire da ASP.NET Core 3,0, `Microsoft.AspNetCore.DataProtection.AzureStorage` usa le nuove API e i pacchetti con prefisso @no__t 1.</span><span class="sxs-lookup"><span data-stu-id="77300-104">Starting in ASP.NET Core 3.0, `Microsoft.AspNetCore.DataProtection.AzureStorage` uses the new `Microsoft.Azure.Storage.`-prefixed APIs and packages.</span></span>

<span data-ttu-id="77300-105">Per domande sulle API di archiviazione di Azure, usare <https://github.com/Azure/azure-storage-net>.</span><span class="sxs-lookup"><span data-stu-id="77300-105">For questions about the Azure Storage APIs, use <https://github.com/Azure/azure-storage-net>.</span></span> <span data-ttu-id="77300-106">Per informazioni su questo problema, vedere [ASPNET/AspNetCore # 8472](https://github.com/aspnet/AspNetCore/issues/8472).</span><span class="sxs-lookup"><span data-stu-id="77300-106">For discussion on this issue, see [aspnet/AspNetCore#8472](https://github.com/aspnet/AspNetCore/issues/8472).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="77300-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="77300-107">Version introduced</span></span>

<span data-ttu-id="77300-108">3.0</span><span class="sxs-lookup"><span data-stu-id="77300-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="77300-109">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="77300-109">Old behavior</span></span>

<span data-ttu-id="77300-110">Il pacchetto fa riferimento al pacchetto NuGet `WindowsAzure.Storage`.</span><span class="sxs-lookup"><span data-stu-id="77300-110">The package referenced the `WindowsAzure.Storage` NuGet package.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="77300-111">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="77300-111">New behavior</span></span>

<span data-ttu-id="77300-112">Il pacchetto fa riferimento al pacchetto NuGet `Microsoft.Azure.Storage.Blob`.</span><span class="sxs-lookup"><span data-stu-id="77300-112">The package references the `Microsoft.Azure.Storage.Blob` NuGet package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="77300-113">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="77300-113">Reason for change</span></span>

<span data-ttu-id="77300-114">Questa modifica consente la migrazione di `Microsoft.AspNetCore.DataProtection.AzureStorage` ai pacchetti di archiviazione di Azure consigliati.</span><span class="sxs-lookup"><span data-stu-id="77300-114">This change allows `Microsoft.AspNetCore.DataProtection.AzureStorage` to migrate to the recommended Azure Storage packages.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="77300-115">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="77300-115">Recommended action</span></span>

<span data-ttu-id="77300-116">Se è ancora necessario usare le API di archiviazione di Azure meno recenti con ASP.NET Core 3,0, aggiungere una dipendenza diretta al pacchetto [WindowsAzure. storage](https://www.nuget.org/packages/WindowsAzure.Storage/) .</span><span class="sxs-lookup"><span data-stu-id="77300-116">If you still need to use the older Azure Storage APIs with ASP.NET Core 3.0, add a direct dependency to the [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) package.</span></span> <span data-ttu-id="77300-117">Questo pacchetto può essere installato insieme alle nuove API `Microsoft.Azure.Storage`.</span><span class="sxs-lookup"><span data-stu-id="77300-117">This package can be installed alongside the new `Microsoft.Azure.Storage` APIs.</span></span>

<span data-ttu-id="77300-118">In molti casi, l'aggiornamento comporta solo la modifica delle istruzioni `using` per l'uso dei nuovi spazi dei nomi:</span><span class="sxs-lookup"><span data-stu-id="77300-118">In many cases, the upgrade only involves changing the `using` statements to use the new namespaces:</span></span>

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
+ using Microsoft.Azure.Storage;
+ using Microsoft.Azure.Storage.Blob;
```

#### <a name="category"></a><span data-ttu-id="77300-119">Category</span><span class="sxs-lookup"><span data-stu-id="77300-119">Category</span></span>

<span data-ttu-id="77300-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="77300-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="77300-121">API interessate</span><span class="sxs-lookup"><span data-stu-id="77300-121">Affected APIs</span></span>

<span data-ttu-id="77300-122">Nessuno</span><span class="sxs-lookup"><span data-stu-id="77300-122">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
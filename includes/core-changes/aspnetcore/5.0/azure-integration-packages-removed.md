---
ms.openlocfilehash: 19ccdb634d4e53ea66c032502f2adb70423ab121
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416249"
---
### <a name="azure-microsoft-prefixed-azure-integration-packages-removed"></a><span data-ttu-id="9de98-101">Azure: pacchetti di integrazione di Azure con prefisso Microsoft rimossi</span><span class="sxs-lookup"><span data-stu-id="9de98-101">Azure: Microsoft-prefixed Azure integration packages removed</span></span>

<span data-ttu-id="9de98-102">I `Microsoft.*` pacchetti seguenti che forniscono l'integrazione tra ASP.NET Core e Azure SDK non sono inclusi nella ASP.NET Core 5,0:</span><span class="sxs-lookup"><span data-stu-id="9de98-102">The following `Microsoft.*` packages that provide integration between ASP.NET Core and Azure SDKs aren't included in ASP.NET Core 5.0:</span></span>

* <span data-ttu-id="9de98-103">[Microsoft.Extensions.Configuration. AzureKeyVault](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.AzureKeyVault/), che integra [Azure Key Vault](/azure/key-vault/) nel sistema di [configurazione](/aspnet/core/fundamentals/configuration/).</span><span class="sxs-lookup"><span data-stu-id="9de98-103">[Microsoft.Extensions.Configuration.AzureKeyVault](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.AzureKeyVault/), which integrates [Azure Key Vault](/azure/key-vault/) into the [Configuration system](/aspnet/core/fundamentals/configuration/).</span></span>
* <span data-ttu-id="9de98-104">[Microsoft. AspNetCore. dataprotection. AzureKeyVault](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureKeyVault/), che integra Azure Key Vault nel sistema di [protezione dei dati ASP.NET Core](/aspnet/core/security/data-protection/introduction).</span><span class="sxs-lookup"><span data-stu-id="9de98-104">[Microsoft.AspNetCore.DataProtection.AzureKeyVault](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureKeyVault/), which integrates Azure Key Vault into the [ASP.NET Core Data Protection system](/aspnet/core/security/data-protection/introduction).</span></span>
* <span data-ttu-id="9de98-105">[Microsoft. AspNetCore. dataprotection. AzureStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureStorage/), che integra l' [archiviazione BLOB di Azure](/azure/storage/blobs/) nel sistema di protezione dei dati ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="9de98-105">[Microsoft.AspNetCore.DataProtection.AzureStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureStorage/), which integrates [Azure Blob Storage](/azure/storage/blobs/) into the ASP.NET Core Data Protection system.</span></span>

<span data-ttu-id="9de98-106">Per informazioni su questo problema, vedere [DotNet/aspnetcore # 19570](https://github.com/dotnet/aspnetcore/issues/19570).</span><span class="sxs-lookup"><span data-stu-id="9de98-106">For discussion on this issue, see [dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9de98-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="9de98-107">Version introduced</span></span>

<span data-ttu-id="9de98-108">5,0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="9de98-108">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="9de98-109">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="9de98-109">Old behavior</span></span>

<span data-ttu-id="9de98-110">I `Microsoft.*` pacchetti integrano i servizi di Azure con le API di configurazione e protezione dei dati.</span><span class="sxs-lookup"><span data-stu-id="9de98-110">The `Microsoft.*` packages integrated Azure services with the Configuration and Data Protection APIs.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="9de98-111">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="9de98-111">New behavior</span></span>

<span data-ttu-id="9de98-112">`Azure.*`I nuovi pacchetti integrano i servizi di Azure con le API di configurazione e protezione dei dati.</span><span class="sxs-lookup"><span data-stu-id="9de98-112">New `Azure.*` packages integrate Azure services with the Configuration and Data Protection APIs.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="9de98-113">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="9de98-113">Reason for change</span></span>

<span data-ttu-id="9de98-114">La modifica è stata apportata perché i `Microsoft.*` pacchetti sono:</span><span class="sxs-lookup"><span data-stu-id="9de98-114">The change was made because the `Microsoft.*` packages were:</span></span>

* <span data-ttu-id="9de98-115">Uso di versioni obsolete di Azure SDK.</span><span class="sxs-lookup"><span data-stu-id="9de98-115">Using outdated versions of the Azure SDK.</span></span> <span data-ttu-id="9de98-116">Gli aggiornamenti semplici non erano possibili perché le nuove versioni di Azure SDK includevano modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="9de98-116">Simple updates weren't possible because the new versions of the Azure SDK included breaking changes.</span></span>
* <span data-ttu-id="9de98-117">Associato alla pianificazione delle versioni di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9de98-117">Tied to the .NET Core release schedule.</span></span> <span data-ttu-id="9de98-118">Il trasferimento della proprietà dei pacchetti al team di Azure SDK Abilita gli aggiornamenti dei pacchetti durante l'aggiornamento di Azure SDK.</span><span class="sxs-lookup"><span data-stu-id="9de98-118">Transferring ownership of the packages to the Azure SDK team enables package updates as the Azure SDK is updated.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9de98-119">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="9de98-119">Recommended action</span></span>

<span data-ttu-id="9de98-120">Nei progetti ASP.NET Core 2,1 o versioni successive sostituire il vecchio `Microsoft.*` con i nuovi `Azure.*` pacchetti.</span><span class="sxs-lookup"><span data-stu-id="9de98-120">In ASP.NET Core 2.1 or later projects, replace the old `Microsoft.*` with the new `Azure.*` packages.</span></span>

| <span data-ttu-id="9de98-121">Precedente</span><span class="sxs-lookup"><span data-stu-id="9de98-121">Old</span></span> | <span data-ttu-id="9de98-122">Nuovo</span><span class="sxs-lookup"><span data-stu-id="9de98-122">New</span></span> |
|--|--|
| `Microsoft.AspNetCore.DataProtection.AzureKeyVault` | [<span data-ttu-id="9de98-123">Azure. Extensions. AspNetCore. dataprotection. Keys</span><span class="sxs-lookup"><span data-stu-id="9de98-123">Azure.Extensions.AspNetCore.DataProtection.Keys</span></span>](https://www.nuget.org/packages/Azure.Extensions.AspNetCore.DataProtection.Keys) |
| `Microsoft.AspNetCore.DataProtection.AzureStorage` | [<span data-ttu-id="9de98-124">Azure. Extensions. AspNetCore. dataprotection. blob</span><span class="sxs-lookup"><span data-stu-id="9de98-124">Azure.Extensions.AspNetCore.DataProtection.Blobs</span></span>](https://www.nuget.org/packages/Azure.Extensions.AspNetCore.DataProtection.Blobs) |
| `Microsoft.Extensions.Configuration.AzureKeyVault` | [<span data-ttu-id="9de98-125">Azure.Extensions.AspNetCore.Configuration. Segreti</span><span class="sxs-lookup"><span data-stu-id="9de98-125">Azure.Extensions.AspNetCore.Configuration.Secrets</span></span>](https://www.nuget.org/packages/Azure.Extensions.AspNetCore.Configuration.Secrets) |

<span data-ttu-id="9de98-126">I nuovi pacchetti usano una nuova versione di Azure SDK che include modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="9de98-126">The new packages use a new version of the Azure SDK that includes breaking changes.</span></span> <span data-ttu-id="9de98-127">I modelli di utilizzo generali sono rimasti invariati.</span><span class="sxs-lookup"><span data-stu-id="9de98-127">The general usage patterns are unchanged.</span></span> <span data-ttu-id="9de98-128">Alcuni overload e opzioni possono essere diversi per adattarsi alle modifiche nelle API di Azure SDK sottostanti.</span><span class="sxs-lookup"><span data-stu-id="9de98-128">Some overloads and options may differ to adapt to changes in the underlying Azure SDK APIs.</span></span>

<span data-ttu-id="9de98-129">I pacchetti precedenti:</span><span class="sxs-lookup"><span data-stu-id="9de98-129">The old packages will:</span></span>

* <span data-ttu-id="9de98-130">Essere supportato dal team di ASP.NET Core per la durata di .NET Core 2,1 e 3,1.</span><span class="sxs-lookup"><span data-stu-id="9de98-130">Be supported by the ASP.NET Core team for the lifetime of .NET Core 2.1 and 3.1.</span></span>
* <span data-ttu-id="9de98-131">Non essere incluso in .NET 5.</span><span class="sxs-lookup"><span data-stu-id="9de98-131">Not be included in .NET 5.</span></span>

<span data-ttu-id="9de98-132">Quando si aggiorna il progetto a .NET 5, passare ai `Azure.*` pacchetti per mantenere il supporto.</span><span class="sxs-lookup"><span data-stu-id="9de98-132">When upgrading your project to .NET 5, transition to the `Azure.*` packages to maintain support.</span></span>

#### <a name="category"></a><span data-ttu-id="9de98-133">Categoria</span><span class="sxs-lookup"><span data-stu-id="9de98-133">Category</span></span>

<span data-ttu-id="9de98-134">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9de98-134">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9de98-135">API interessate</span><span class="sxs-lookup"><span data-stu-id="9de98-135">Affected APIs</span></span>

- <xref:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.ProtectKeysWithAzureKeyVault%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.PersistKeysToAzureBlobStorage%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault`
- `Overload:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.ProtectKeysWithAzureKeyVault`
- `Overload:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.PersistKeysToAzureBlobStorage`

-->

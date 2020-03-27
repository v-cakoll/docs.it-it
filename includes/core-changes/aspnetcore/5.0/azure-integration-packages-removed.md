---
ms.openlocfilehash: d8506893f5b3eefa6f46dc9f773e43b125ee5210
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291652"
---
### <a name="azure-microsoft-prefixed-azure-integration-packages-removed"></a><span data-ttu-id="1a997-101">Azure: rimossi i pacchetti di integrazione di Azure con prefisso MicrosoftAzure: Microsoft-prefixed Azure integration packages removed</span><span class="sxs-lookup"><span data-stu-id="1a997-101">Azure: Microsoft-prefixed Azure integration packages removed</span></span>

<span data-ttu-id="1a997-102">I `Microsoft.*` pacchetti seguenti che forniscono l'integrazione tra ASP.NET Core e gli SDK di Azure non sono inclusi in ASP.NET Core 5.0:The following packages that provide integration between ASP.NET Core and Azure SDKs aren't included in ASP.NET Core 5.0:</span><span class="sxs-lookup"><span data-stu-id="1a997-102">The following `Microsoft.*` packages that provide integration between ASP.NET Core and Azure SDKs aren't included in ASP.NET Core 5.0:</span></span>

* <span data-ttu-id="1a997-103">[Microsoft.Extensions.Configuration.AzureKeyVault](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.AzureKeyVault/), che integra [l'insieme](/azure/key-vault/) di credenziali delle chiavi di Azure nel sistema di [configurazione.](/aspnet/core/fundamentals/configuration/)</span><span class="sxs-lookup"><span data-stu-id="1a997-103">[Microsoft.Extensions.Configuration.AzureKeyVault](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.AzureKeyVault/), which integrates [Azure Key Vault](/azure/key-vault/) into the [Configuration system](/aspnet/core/fundamentals/configuration/).</span></span>
* <span data-ttu-id="1a997-104">[Microsoft.AspNetCore.DataProtection.AzureKeyVault](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureKeyVault/), che integra l'insieme di credenziali delle chiavi di Azure nel [sistema di protezione dei dati di ASP.NET core](/aspnet/core/security/data-protection/introduction).</span><span class="sxs-lookup"><span data-stu-id="1a997-104">[Microsoft.AspNetCore.DataProtection.AzureKeyVault](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureKeyVault/), which integrates Azure Key Vault into the [ASP.NET Core Data Protection system](/aspnet/core/security/data-protection/introduction).</span></span>
* <span data-ttu-id="1a997-105">[Microsoft.AspNetCore.DataProtection.AzureStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureStorage/), che integra [Archiviazione BLOB](/azure/storage/blobs/) di Azure nel sistema di protezione dei dati di ASP.NET core.</span><span class="sxs-lookup"><span data-stu-id="1a997-105">[Microsoft.AspNetCore.DataProtection.AzureStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureStorage/), which integrates [Azure Blob Storage](/azure/storage/blobs/) into the ASP.NET Core Data Protection system.</span></span>

<span data-ttu-id="1a997-106">Per una discussione su questo problema, vedere [dotnet/aspnetcore-19570](https://github.com/dotnet/aspnetcore/issues/19570).</span><span class="sxs-lookup"><span data-stu-id="1a997-106">For discussion on this issue, see [dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1a997-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="1a997-107">Version introduced</span></span>

<span data-ttu-id="1a997-108">5.0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="1a997-108">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="1a997-109">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="1a997-109">Old behavior</span></span>

<span data-ttu-id="1a997-110">I `Microsoft.*` pacchetti sono stati integrati con le API di configurazione e protezione dei dati.</span><span class="sxs-lookup"><span data-stu-id="1a997-110">The `Microsoft.*` packages integrated Azure services with the Configuration and Data Protection APIs.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="1a997-111">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="1a997-111">New behavior</span></span>

<span data-ttu-id="1a997-112">I `Azure.*` nuovi pacchetti integrano i servizi di Azure con le API di configurazione e protezione dei dati.</span><span class="sxs-lookup"><span data-stu-id="1a997-112">New `Azure.*` packages integrate Azure services with the Configuration and Data Protection APIs.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="1a997-113">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="1a997-113">Reason for change</span></span>

<span data-ttu-id="1a997-114">La modifica è `Microsoft.*` stata apportata perché i pacchetti erano:</span><span class="sxs-lookup"><span data-stu-id="1a997-114">The change was made because the `Microsoft.*` packages were:</span></span>

* <span data-ttu-id="1a997-115">Utilizzo di versioni obsolete di Azure SDK.</span><span class="sxs-lookup"><span data-stu-id="1a997-115">Using outdated versions of the Azure SDK.</span></span> <span data-ttu-id="1a997-116">Semplici aggiornamenti non erano possibili perché le nuove versioni di Azure SDK includevano modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="1a997-116">Simple updates weren't possible because the new versions of the Azure SDK included breaking changes.</span></span>
* <span data-ttu-id="1a997-117">Legato alla pianificazione del rilascio di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1a997-117">Tied to the .NET Core release schedule.</span></span> <span data-ttu-id="1a997-118">Il trasferimento della proprietà dei pacchetti al team di Azure SDK abilita gli aggiornamenti dei pacchetti durante l'aggiornamento di Azure SDK.</span><span class="sxs-lookup"><span data-stu-id="1a997-118">Transferring ownership of the packages to the Azure SDK team enables package updates as the Azure SDK is updated.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1a997-119">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="1a997-119">Recommended action</span></span>

<span data-ttu-id="1a997-120">In ASP.NET Core 2.1 o progetti `Microsoft.*` successivi, `Azure.*` sostituire il vecchio con i nuovi pacchetti.</span><span class="sxs-lookup"><span data-stu-id="1a997-120">In ASP.NET Core 2.1 or later projects, replace the old `Microsoft.*` with the new `Azure.*` packages.</span></span>

| <span data-ttu-id="1a997-121">Vecchio</span><span class="sxs-lookup"><span data-stu-id="1a997-121">Old</span></span> | <span data-ttu-id="1a997-122">Nuovo</span><span class="sxs-lookup"><span data-stu-id="1a997-122">New</span></span> |
|--|--|
| `Microsoft.AspNetCore.DataProtection.AzureKeyVault` | [<span data-ttu-id="1a997-123">Azure.AspNetCore.DataProtection.Keys</span><span class="sxs-lookup"><span data-stu-id="1a997-123">Azure.AspNetCore.DataProtection.Keys</span></span>](https://www.nuget.org/packages/Azure.AspNetCore.DataProtection.Keys) |
| `Microsoft.AspNetCore.DataProtection.AzureStorage` | [<span data-ttu-id="1a997-124">Azure.AspNetCore.DataProtection.Blobs</span><span class="sxs-lookup"><span data-stu-id="1a997-124">Azure.AspNetCore.DataProtection.Blobs</span></span>](https://www.nuget.org/packages/Azure.AspNetCore.DataProtection.Blobs) |
| `Microsoft.Extensions.Configuration.AzureKeyVault` | [<span data-ttu-id="1a997-125">Azure.Extensions.Configuration.Secrets</span><span class="sxs-lookup"><span data-stu-id="1a997-125">Azure.Extensions.Configuration.Secrets</span></span>](https://www.nuget.org/packages/Azure.Extensions.Configuration.Secrets) |

<span data-ttu-id="1a997-126">I nuovi pacchetti usano una nuova versione di Azure SDK che include modifiche di rilievo.</span><span class="sxs-lookup"><span data-stu-id="1a997-126">The new packages use a new version of the Azure SDK that includes breaking changes.</span></span> <span data-ttu-id="1a997-127">I modelli di utilizzo generale sono invariati.</span><span class="sxs-lookup"><span data-stu-id="1a997-127">The general usage patterns are unchanged.</span></span> <span data-ttu-id="1a997-128">Alcuni overload e opzioni possono differire per adattarsi alle modifiche nelle API di Azure SDK sottostanti.</span><span class="sxs-lookup"><span data-stu-id="1a997-128">Some overloads and options may differ to adapt to changes in the underlying Azure SDK APIs.</span></span>

<span data-ttu-id="1a997-129">I vecchi pacchetti:</span><span class="sxs-lookup"><span data-stu-id="1a997-129">The old packages will:</span></span>

* <span data-ttu-id="1a997-130">Essere supportato dal team di ASP.NET Core per la durata di .NET Core 2.1 e 3.1.</span><span class="sxs-lookup"><span data-stu-id="1a997-130">Be supported by the ASP.NET Core team for the lifetime of .NET Core 2.1 and 3.1.</span></span>
* <span data-ttu-id="1a997-131">Non essere incluso in .NET 5.</span><span class="sxs-lookup"><span data-stu-id="1a997-131">Not be included in .NET 5.</span></span>

<span data-ttu-id="1a997-132">Quando si aggiorna il progetto a `Azure.*` .NET 5, eseguire la transizione ai pacchetti per mantenere il supporto.</span><span class="sxs-lookup"><span data-stu-id="1a997-132">When upgrading your project to .NET 5, transition to the `Azure.*` packages to maintain support.</span></span>

#### <a name="category"></a><span data-ttu-id="1a997-133">Category</span><span class="sxs-lookup"><span data-stu-id="1a997-133">Category</span></span>

<span data-ttu-id="1a997-134">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1a997-134">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1a997-135">API interessate</span><span class="sxs-lookup"><span data-stu-id="1a997-135">Affected APIs</span></span>

- <xref:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.ProtectKeysWithAzureKeyVault%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.PersistKeysToAzureBlobStorage%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault`
- `Overload:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.ProtectKeysWithAzureKeyVault`
- `Overload:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.PersistKeysToAzureBlobStorage`

-->
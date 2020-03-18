---
ms.openlocfilehash: 82103d82a6f68c62f3532608718bc71b0ba126bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901737"
---
### <a name="hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle"></a><span data-ttu-id="6a0a7-101">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span><span class="sxs-lookup"><span data-stu-id="6a0a7-101">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span></span>

<span data-ttu-id="6a0a7-102">A partire da ASP.NET Core 3.0, il pacchetto di hosting di Windows non conterrà AspNetCoreModule (ANCM) V1.</span><span class="sxs-lookup"><span data-stu-id="6a0a7-102">Starting with ASP.NET Core 3.0, the Windows Hosting Bundle won't contain AspNetCoreModule (ANCM) V1.</span></span>

<span data-ttu-id="6a0a7-103">ANCM V2 è compatibile con le versioni precedenti di ANCM OutOfProcess ed è consigliato per l'uso con le app ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="6a0a7-103">ANCM V2 is backwards compatible with ANCM OutOfProcess and is recommended for use with ASP.NET Core 3.0 apps.</span></span>

<span data-ttu-id="6a0a7-104">Per una discussione, vedere [dotnet/aspnetcore-7095](https://github.com/dotnet/aspnetcore/issues/7095).</span><span class="sxs-lookup"><span data-stu-id="6a0a7-104">For discussion, see [dotnet/aspnetcore#7095](https://github.com/dotnet/aspnetcore/issues/7095).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6a0a7-105">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6a0a7-105">Version introduced</span></span>

<span data-ttu-id="6a0a7-106">3.0</span><span class="sxs-lookup"><span data-stu-id="6a0a7-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="6a0a7-107">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="6a0a7-107">Old behavior</span></span>

<span data-ttu-id="6a0a7-108">ANCM V1 è incluso nel pacchetto di hosting di Windows.</span><span class="sxs-lookup"><span data-stu-id="6a0a7-108">ANCM V1 is included in the Windows Hosting Bundle.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="6a0a7-109">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="6a0a7-109">New behavior</span></span>

<span data-ttu-id="6a0a7-110">ANCM V1 non è incluso nel pacchetto di hosting di Windows.</span><span class="sxs-lookup"><span data-stu-id="6a0a7-110">ANCM V1 isn't included in the Windows Hosting Bundle.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="6a0a7-111">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="6a0a7-111">Reason for change</span></span>

<span data-ttu-id="6a0a7-112">ANCM V2 è compatibile con le versioni precedenti di ANCM OutOfProcess ed è consigliato per l'uso con le app ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="6a0a7-112">ANCM V2 is backwards compatible with ANCM OutOfProcess and is recommended for use with ASP.NET Core 3.0 apps.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6a0a7-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="6a0a7-113">Recommended action</span></span>

<span data-ttu-id="6a0a7-114">Usa ANCM V2 con ASP.NET app Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="6a0a7-114">Use ANCM V2 with ASP.NET Core 3.0 apps.</span></span>

<span data-ttu-id="6a0a7-115">Se è richiesto ANCM V1, può essere installato utilizzando il ASP.NET Core 2.1 o 2.2 Windows Hosting Bundle.</span><span class="sxs-lookup"><span data-stu-id="6a0a7-115">If ANCM V1 is required, it can be installed using the ASP.NET Core 2.1 or 2.2 Windows Hosting Bundle.</span></span>

<span data-ttu-id="6a0a7-116">Questa modifica interromperà ASP.NET le app Core 3.0 che:This change will break ASP.NET Core 3.0 apps that:</span><span class="sxs-lookup"><span data-stu-id="6a0a7-116">This change will break ASP.NET Core 3.0 apps that:</span></span>

- <span data-ttu-id="6a0a7-117">Esplicitamente optato per `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`l'utilizzo di ANCM V1 con .</span><span class="sxs-lookup"><span data-stu-id="6a0a7-117">Explicitly opted into using ANCM V1 with `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`.</span></span>
- <span data-ttu-id="6a0a7-118">Disporre di un file `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />` *web.config* personalizzato con .</span><span class="sxs-lookup"><span data-stu-id="6a0a7-118">Have a custom *web.config* file with `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />`.</span></span>

#### <a name="category"></a><span data-ttu-id="6a0a7-119">Category</span><span class="sxs-lookup"><span data-stu-id="6a0a7-119">Category</span></span>

<span data-ttu-id="6a0a7-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6a0a7-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6a0a7-121">API interessate</span><span class="sxs-lookup"><span data-stu-id="6a0a7-121">Affected APIs</span></span>

<span data-ttu-id="6a0a7-122">nessuno</span><span class="sxs-lookup"><span data-stu-id="6a0a7-122">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->

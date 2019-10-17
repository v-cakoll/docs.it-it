---
ms.openlocfilehash: 04e5ca41374fc333a31f0422bc2e89f54b3cb049
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394093"
---
### <a name="hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle"></a><span data-ttu-id="ae168-101">Hosting: AspNetCoreModule V1 rimosso dal bundle di hosting di Windows</span><span class="sxs-lookup"><span data-stu-id="ae168-101">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span></span>

<span data-ttu-id="ae168-102">A partire da ASP.NET Core 3,0, il bundle di hosting di Windows non conterrà AspNetCoreModule (modulo ASP.NET Core) V1.</span><span class="sxs-lookup"><span data-stu-id="ae168-102">Starting with ASP.NET Core 3.0, the Windows Hosting Bundle won't contain AspNetCoreModule (ANCM) V1.</span></span>

<span data-ttu-id="ae168-103">MODULO ASP.net core V2 è compatibile con le versioni precedenti di modulo ASP.NET Core OutOfProcess ed è consigliato per l'uso con app ASP.NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="ae168-103">ANCM V2 is backwards compatible with ANCM OutOfProcess and is recommended for use with ASP.NET Core 3.0 apps.</span></span>

<span data-ttu-id="ae168-104">Per informazioni, vedere [ASPNET/AspNetCore # 7095](https://github.com/aspnet/AspNetCore/issues/7095).</span><span class="sxs-lookup"><span data-stu-id="ae168-104">For discussion, see [aspnet/AspNetCore#7095](https://github.com/aspnet/AspNetCore/issues/7095).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ae168-105">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="ae168-105">Version introduced</span></span>

<span data-ttu-id="ae168-106">3.0</span><span class="sxs-lookup"><span data-stu-id="ae168-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="ae168-107">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="ae168-107">Old behavior</span></span>

<span data-ttu-id="ae168-108">MODULO ASP.NET Core V1 è incluso nel bundle di hosting di Windows.</span><span class="sxs-lookup"><span data-stu-id="ae168-108">ANCM V1 is included in the Windows Hosting Bundle.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="ae168-109">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="ae168-109">New behavior</span></span>

<span data-ttu-id="ae168-110">MODULO ASP.NET Core V1 non è incluso nel bundle di hosting di Windows.</span><span class="sxs-lookup"><span data-stu-id="ae168-110">ANCM V1 isn't included in the Windows Hosting Bundle.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ae168-111">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="ae168-111">Reason for change</span></span>

<span data-ttu-id="ae168-112">MODULO ASP.net core V2 è compatibile con le versioni precedenti di modulo ASP.NET Core OutOfProcess ed è consigliato per l'uso con app ASP.NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="ae168-112">ANCM V2 is backwards compatible with ANCM OutOfProcess and is recommended for use with ASP.NET Core 3.0 apps.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ae168-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="ae168-113">Recommended action</span></span>

<span data-ttu-id="ae168-114">Usare modulo ASP.net core V2 con app ASP.NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="ae168-114">Use ANCM V2 with ASP.NET Core 3.0 apps.</span></span>

<span data-ttu-id="ae168-115">Se è necessario modulo ASP.NET Core V1, può essere installato usando il bundle di hosting di Windows ASP.NET Core 2,1 o 2,2.</span><span class="sxs-lookup"><span data-stu-id="ae168-115">If ANCM V1 is required, it can be installed using the ASP.NET Core 2.1 or 2.2 Windows Hosting Bundle.</span></span>

<span data-ttu-id="ae168-116">Questa modifica interrompe ASP.NET Core app 3,0 che:</span><span class="sxs-lookup"><span data-stu-id="ae168-116">This change will break ASP.NET Core 3.0 apps that:</span></span>

- <span data-ttu-id="ae168-117">È stato esplicitamente accettato l'uso di modulo ASP.NET Core V1 con `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`.</span><span class="sxs-lookup"><span data-stu-id="ae168-117">Explicitly opted into using ANCM V1 with `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`.</span></span>
- <span data-ttu-id="ae168-118">Disporre di un file *Web. config* personalizzato con `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />`.</span><span class="sxs-lookup"><span data-stu-id="ae168-118">Have a custom *web.config* file with `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />`.</span></span>

#### <a name="category"></a><span data-ttu-id="ae168-119">Category</span><span class="sxs-lookup"><span data-stu-id="ae168-119">Category</span></span>

<span data-ttu-id="ae168-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ae168-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ae168-121">API interessate</span><span class="sxs-lookup"><span data-stu-id="ae168-121">Affected APIs</span></span>

<span data-ttu-id="ae168-122">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ae168-122">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->

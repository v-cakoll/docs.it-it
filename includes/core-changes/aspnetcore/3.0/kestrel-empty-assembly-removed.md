---
ms.openlocfilehash: 1c9c899d77dd69e185281d98bfec18ce73d80815
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394003"
---
### <a name="kestrel-empty-https-assembly-removed"></a><span data-ttu-id="2a39c-101">Gheppio: assembly HTTPS vuoto rimosso</span><span class="sxs-lookup"><span data-stu-id="2a39c-101">Kestrel: Empty HTTPS assembly removed</span></span>

<span data-ttu-id="2a39c-102">L'assembly <xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName> è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="2a39c-102">The assembly <xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName> has been removed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2a39c-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="2a39c-103">Version introduced</span></span>

<span data-ttu-id="2a39c-104">3.0</span><span class="sxs-lookup"><span data-stu-id="2a39c-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2a39c-105">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="2a39c-105">Reason for change</span></span>

<span data-ttu-id="2a39c-106">In ASP.NET Core 2,1 il contenuto di `Microsoft.AspNetCore.Server.Kestrel.Https` è stato spostato in <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="2a39c-106">In ASP.NET Core 2.1, the contents of `Microsoft.AspNetCore.Server.Kestrel.Https` were moved to <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName>.</span></span> <span data-ttu-id="2a39c-107">Questa modifica è stata eseguita in modo non sostanziale usando gli attributi `[TypeForwardedTo]`.</span><span class="sxs-lookup"><span data-stu-id="2a39c-107">This change was done in a non-breaking way using `[TypeForwardedTo]` attributes.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2a39c-108">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="2a39c-108">Recommended action</span></span>

- <span data-ttu-id="2a39c-109">Le librerie che fanno riferimento a `Microsoft.AspNetCore.Server.Kestrel.Https` 2,0 devono aggiornare tutte le dipendenze ASP.NET Core a 2,1 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="2a39c-109">Libraries referencing `Microsoft.AspNetCore.Server.Kestrel.Https` 2.0 should update all ASP.NET Core dependencies to 2.1 or later.</span></span> <span data-ttu-id="2a39c-110">In caso contrario, potrebbero interrompersi quando vengono caricati in un'app ASP.NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="2a39c-110">Otherwise, they may break when loaded into an ASP.NET Core 3.0 app.</span></span>
- <span data-ttu-id="2a39c-111">Le app e le librerie destinate a ASP.NET Core 2,1 e versioni successive dovrebbero rimuovere tutti i riferimenti diretti al pacchetto NuGet `Microsoft.AspNetCore.Server.Kestrel.Https`.</span><span class="sxs-lookup"><span data-stu-id="2a39c-111">Apps and libraries targeting ASP.NET Core 2.1 and later should remove any direct references to the `Microsoft.AspNetCore.Server.Kestrel.Https` NuGet package.</span></span>

#### <a name="category"></a><span data-ttu-id="2a39c-112">Category</span><span class="sxs-lookup"><span data-stu-id="2a39c-112">Category</span></span>

<span data-ttu-id="2a39c-113">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2a39c-113">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2a39c-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="2a39c-114">Affected APIs</span></span>

<span data-ttu-id="2a39c-115">Nessuno</span><span class="sxs-lookup"><span data-stu-id="2a39c-115">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->

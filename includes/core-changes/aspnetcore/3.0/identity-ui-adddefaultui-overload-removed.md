---
ms.openlocfilehash: 806722ea9aec1c828786525e3155b7f624159ac1
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522702"
---
### <a name="identity-adddefaultui-method-overload-removed"></a><span data-ttu-id="65a3a-101">Identità: overload del metodo AddDefaultUI rimosso</span><span class="sxs-lookup"><span data-stu-id="65a3a-101">Identity: AddDefaultUI method overload removed</span></span>

<span data-ttu-id="65a3a-102">A partire da ASP.NET Core 3,0, l'overload del metodo <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType> non esiste più.</span><span class="sxs-lookup"><span data-stu-id="65a3a-102">Starting with ASP.NET Core 3.0, the <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType> method overload no longer exists.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="65a3a-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="65a3a-103">Version introduced</span></span>

<span data-ttu-id="65a3a-104">3.0</span><span class="sxs-lookup"><span data-stu-id="65a3a-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="65a3a-105">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="65a3a-105">Reason for change</span></span>

<span data-ttu-id="65a3a-106">Questa modifica è stata il risultato dell'adozione della funzionalità di asset Web statici.</span><span class="sxs-lookup"><span data-stu-id="65a3a-106">This change was a result of adoption of the static web assets feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="65a3a-107">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="65a3a-107">Recommended action</span></span>

<span data-ttu-id="65a3a-108">Chiamare <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> anziché l'overload.</span><span class="sxs-lookup"><span data-stu-id="65a3a-108">Call <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> instead of the overload.</span></span> <span data-ttu-id="65a3a-109">Se si usa bootstrap 3, aggiungere anche la riga seguente a un elemento `<PropertyGroup>` nel file di progetto:</span><span class="sxs-lookup"><span data-stu-id="65a3a-109">If you're using Bootstrap 3, also add the following line to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="65a3a-110">Category</span><span class="sxs-lookup"><span data-stu-id="65a3a-110">Category</span></span>

<span data-ttu-id="65a3a-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="65a3a-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="65a3a-112">API interessate</span><span class="sxs-lookup"><span data-stu-id="65a3a-112">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->

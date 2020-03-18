---
ms.openlocfilehash: 806722ea9aec1c828786525e3155b7f624159ac1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522702"
---
### <a name="identity-adddefaultui-method-overload-removed"></a><span data-ttu-id="f8af7-101">Identità: AddDefaultUI method overload removed</span><span class="sxs-lookup"><span data-stu-id="f8af7-101">Identity: AddDefaultUI method overload removed</span></span>

<span data-ttu-id="f8af7-102">A partire da ASP.NET Core <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType> 3.0, l'overload del metodo non esiste più.</span><span class="sxs-lookup"><span data-stu-id="f8af7-102">Starting with ASP.NET Core 3.0, the <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType> method overload no longer exists.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f8af7-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="f8af7-103">Version introduced</span></span>

<span data-ttu-id="f8af7-104">3.0</span><span class="sxs-lookup"><span data-stu-id="f8af7-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="f8af7-105">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="f8af7-105">Reason for change</span></span>

<span data-ttu-id="f8af7-106">Questa modifica è il risultato dell'adozione della funzionalità delle risorse Web statiche.</span><span class="sxs-lookup"><span data-stu-id="f8af7-106">This change was a result of adoption of the static web assets feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f8af7-107">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="f8af7-107">Recommended action</span></span>

<span data-ttu-id="f8af7-108">Chiamare <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> invece dell'overload.</span><span class="sxs-lookup"><span data-stu-id="f8af7-108">Call <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> instead of the overload.</span></span> <span data-ttu-id="f8af7-109">Se si utilizza Bootstrap 3, aggiungere anche `<PropertyGroup>` la riga seguente a un elemento nel file di progetto:</span><span class="sxs-lookup"><span data-stu-id="f8af7-109">If you're using Bootstrap 3, also add the following line to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="f8af7-110">Category</span><span class="sxs-lookup"><span data-stu-id="f8af7-110">Category</span></span>

<span data-ttu-id="f8af7-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f8af7-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f8af7-112">API interessate</span><span class="sxs-lookup"><span data-stu-id="f8af7-112">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->

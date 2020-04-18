---
ms.openlocfilehash: 474f039cf00cb48761bfe7b7c4a0a9c6300cd820
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2020
ms.locfileid: "81637197"
---
### <a name="identity-adddefaultui-method-overload-removed"></a><span data-ttu-id="70e7d-101">Identità: AddDefaultUI method overload removed</span><span class="sxs-lookup"><span data-stu-id="70e7d-101">Identity: AddDefaultUI method overload removed</span></span>

<span data-ttu-id="70e7d-102">A partire da ASP.NET Core 3.0, l'overload del metodo [IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_) non esiste più.</span><span class="sxs-lookup"><span data-stu-id="70e7d-102">Starting with ASP.NET Core 3.0, the [IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_) method overload no longer exists.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="70e7d-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="70e7d-103">Version introduced</span></span>

<span data-ttu-id="70e7d-104">3.0</span><span class="sxs-lookup"><span data-stu-id="70e7d-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="70e7d-105">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="70e7d-105">Reason for change</span></span>

<span data-ttu-id="70e7d-106">Questa modifica è il risultato dell'adozione della funzionalità delle risorse Web statiche.</span><span class="sxs-lookup"><span data-stu-id="70e7d-106">This change was a result of adoption of the static web assets feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="70e7d-107">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="70e7d-107">Recommended action</span></span>

<span data-ttu-id="70e7d-108">Chiamare <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> anziché l'overload che accetta due argomenti.</span><span class="sxs-lookup"><span data-stu-id="70e7d-108">Call <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> instead of the overload that takes two arguments.</span></span> <span data-ttu-id="70e7d-109">Se si utilizza Bootstrap 3, aggiungere anche `<PropertyGroup>` la riga seguente a un elemento nel file di progetto:</span><span class="sxs-lookup"><span data-stu-id="70e7d-109">If you're using Bootstrap 3, also add the following line to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="70e7d-110">Category</span><span class="sxs-lookup"><span data-stu-id="70e7d-110">Category</span></span>

<span data-ttu-id="70e7d-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="70e7d-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="70e7d-112">API interessate</span><span class="sxs-lookup"><span data-stu-id="70e7d-112">Affected APIs</span></span>

[<span data-ttu-id="70e7d-113">IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)</span><span class="sxs-lookup"><span data-stu-id="70e7d-113">IdentityBuilderUIExtensions.AddDefaultUI(IdentityBuilder,UIFramework)</span></span>](https://docs.microsoft.com/dotnet/api/microsoft.aspnetcore.identity.identitybuilderuiextensions.adddefaultui?view=aspnetcore-2.2#Microsoft_AspNetCore_Identity_IdentityBuilderUIExtensions_AddDefaultUI_Microsoft_AspNetCore_Identity_IdentityBuilder_Microsoft_AspNetCore_Identity_UI_UIFramework_)

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->

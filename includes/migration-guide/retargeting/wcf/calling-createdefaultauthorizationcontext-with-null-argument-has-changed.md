---
ms.openlocfilehash: c5a061dffa1deb66e1769d6ec70dfa2155ac6a31
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615708"
---
### <a name="calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a><span data-ttu-id="1b939-101">Modifica della chiamata di CreateDefaultAuthorizationContext con un argomento Null</span><span class="sxs-lookup"><span data-stu-id="1b939-101">Calling CreateDefaultAuthorizationContext with a null argument has changed</span></span>

#### <a name="details"></a><span data-ttu-id="1b939-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1b939-102">Details</span></span>

<span data-ttu-id="1b939-103">L'implementazione di <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=fullName> restituito da una chiamata a <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=fullName> con un argomento authorizationPolicies Null è cambiata in .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="1b939-103">The implementation of the <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=fullName> returned by a call to the <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=fullName> with a null authorizationPolicies argument has changed its implementation in the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1b939-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="1b939-104">Suggestion</span></span>

<span data-ttu-id="1b939-105">In rari casi, le app WCF che usano l'autenticazione personalizzata possono riscontrare differenze di comportamento.</span><span class="sxs-lookup"><span data-stu-id="1b939-105">In rare cases, WCF apps that use custom authentication may see behavioral differences.</span></span> <span data-ttu-id="1b939-106">In questi casi è possibile ripristinare il comportamento precedente in due modi diversi:</span><span class="sxs-lookup"><span data-stu-id="1b939-106">In such cases, the previous behavior can be restored in either of two ways:</span></span>

- <span data-ttu-id="1b939-107">Ricompilare l'app per destinarla a una versione precedente rispetto a .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="1b939-107">Recompile your app to target an earlier version of the .NET Framework than 4.6.</span></span> <span data-ttu-id="1b939-108">Per i servizi ospitati in IIS, usare l'elemento `<httpRuntime targetFramework="x.x">` per destinare l'app a una versione precedente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1b939-108">For IIS-hosted services, use the `<httpRuntime targetFramework="x.x">` element to target an earlier version of the .NET Framework.</span></span>
- <span data-ttu-id="1b939-109">Aggiungere la riga seguente alla sezione `<appSettings>` del file app.config:</span><span class="sxs-lookup"><span data-stu-id="1b939-109">Add the following line to the `<appSettings>` section of your app.config file:</span></span>

    ```xml
    <add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />
    ```

| <span data-ttu-id="1b939-110">Nome</span><span class="sxs-lookup"><span data-stu-id="1b939-110">Name</span></span>    | <span data-ttu-id="1b939-111">Valore</span><span class="sxs-lookup"><span data-stu-id="1b939-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1b939-112">Scope</span><span class="sxs-lookup"><span data-stu-id="1b939-112">Scope</span></span>   | <span data-ttu-id="1b939-113">Minorenne</span><span class="sxs-lookup"><span data-stu-id="1b939-113">Minor</span></span>       |
| <span data-ttu-id="1b939-114">Version</span><span class="sxs-lookup"><span data-stu-id="1b939-114">Version</span></span> | <span data-ttu-id="1b939-115">4.6</span><span class="sxs-lookup"><span data-stu-id="1b939-115">4.6</span></span>         |
| <span data-ttu-id="1b939-116">Type</span><span class="sxs-lookup"><span data-stu-id="1b939-116">Type</span></span>    | <span data-ttu-id="1b939-117">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="1b939-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="1b939-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="1b939-118">Affected APIs</span></span>

- <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=nameWithType>

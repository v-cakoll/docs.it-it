---
ms.openlocfilehash: b88f7d4a17f885b687d99ab9410a56039e176080
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614432"
---
### <a name="calls-to-claimsidentity-constructors"></a><span data-ttu-id="4a219-101">Chiamate dei costruttori ClaimsIdentity</span><span class="sxs-lookup"><span data-stu-id="4a219-101">Calls to ClaimsIdentity constructors</span></span>

#### <a name="details"></a><span data-ttu-id="4a219-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4a219-102">Details</span></span>

<span data-ttu-id="4a219-103">A partire da .NET Framework 4.6.2 è stata introdotta una modifica al modo in cui i costruttori <xref:System.Security.Claims.ClaimsIdentity> con un parametro <xref:System.Security.Principal.IIdentity?displayProperty=fullName> impostano la proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="4a219-103">Starting with the .NET Framework 4.6.2, there is a change in how <xref:System.Security.Claims.ClaimsIdentity> constructors with an <xref:System.Security.Principal.IIdentity?displayProperty=fullName> parameter set the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property.</span></span> <span data-ttu-id="4a219-104">Se l'argomento <xref:System.Security.Principal.IIdentity?displayProperty=fullName> è un oggetto <xref:System.Security.Claims.ClaimsIdentity> e la proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> di tale oggetto <xref:System.Security.Claims.ClaimsIdentity> non è `null`, la proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> viene allegata usando il metodo <xref:System.Security.Claims.ClaimsIdentity.Clone>.</span><span class="sxs-lookup"><span data-stu-id="4a219-104">If the <xref:System.Security.Principal.IIdentity?displayProperty=fullName> argument is a <xref:System.Security.Claims.ClaimsIdentity> object, and the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property of that <xref:System.Security.Claims.ClaimsIdentity> object is not `null`, the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property is attached by using the <xref:System.Security.Claims.ClaimsIdentity.Clone> method.</span></span> <span data-ttu-id="4a219-105">In .NET Framework 4.6.1 e versioni precedenti, la proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> viene associata come riferimento esistente. In seguito a questa modifica, a partire da .NET Framework 4.6.2, la proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> del nuovo oggetto <xref:System.Security.Claims.ClaimsIdentity> non è uguale alla proprietà <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> dell'argomento <xref:System.Security.Principal.IIdentity?displayProperty=fullName> del costruttore.</span><span class="sxs-lookup"><span data-stu-id="4a219-105">In the Framework 4.6.1 and earlier versions, the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property is attached as an existing reference.Because of this change, starting with the .NET Framework 4.6.2, the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property of the new <xref:System.Security.Claims.ClaimsIdentity> object is not equal to the <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> property of the constructor's <xref:System.Security.Principal.IIdentity?displayProperty=fullName> argument.</span></span> <span data-ttu-id="4a219-106">In .NET Framework 4.6.1 e versioni precedenti è uguale.</span><span class="sxs-lookup"><span data-stu-id="4a219-106">In the .NET Framework 4.6.1 and earlier versions, it is equal.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4a219-107">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="4a219-107">Suggestion</span></span>

<span data-ttu-id="4a219-108">Se questo comportamento è inaccettabile, è possibile ripristinare il comportamento precedente impostando il commutatore `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` nel file di configurazione dell'applicazione su `true`.</span><span class="sxs-lookup"><span data-stu-id="4a219-108">If this behavior is undesirable, you can restore the previous behavior by setting the `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` switch in your application configuration file to `true`.</span></span> <span data-ttu-id="4a219-109">A questo scopo è necessario aggiungere il codice seguente alla sezione `<runtime>` del file web.config:</span><span class="sxs-lookup"><span data-stu-id="4a219-109">This requires that you add the following to the `<runtime>` section of your web.config file:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="4a219-110">Nome</span><span class="sxs-lookup"><span data-stu-id="4a219-110">Name</span></span>    | <span data-ttu-id="4a219-111">Valore</span><span class="sxs-lookup"><span data-stu-id="4a219-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4a219-112">Scope</span><span class="sxs-lookup"><span data-stu-id="4a219-112">Scope</span></span>   | <span data-ttu-id="4a219-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="4a219-113">Edge</span></span>        |
| <span data-ttu-id="4a219-114">Version</span><span class="sxs-lookup"><span data-stu-id="4a219-114">Version</span></span> | <span data-ttu-id="4a219-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="4a219-115">4.6.2</span></span>       |
| <span data-ttu-id="4a219-116">Type</span><span class="sxs-lookup"><span data-stu-id="4a219-116">Type</span></span>    | <span data-ttu-id="4a219-117">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="4a219-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="4a219-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="4a219-118">Affected APIs</span></span>

- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity)>
- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim})>
- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim},System.String,System.String,System.String)>

---
ms.openlocfilehash: 4f2ace670884d154b219d2146a242d2cee098831
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344292"
---
### <a name="mvc-jsonresult-moved-to-microsoftaspnetcoremvccore"></a><span data-ttu-id="2630e-101">MVC: JsonResult spostato in Microsoft. AspNetCore. Mvc. Core</span><span class="sxs-lookup"><span data-stu-id="2630e-101">MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core</span></span>

<span data-ttu-id="2630e-102">`JsonResult` è stato spostato nell'assembly `Microsoft.AspNetCore.Mvc.Core`.</span><span class="sxs-lookup"><span data-stu-id="2630e-102">`JsonResult` has moved to the `Microsoft.AspNetCore.Mvc.Core` assembly.</span></span> <span data-ttu-id="2630e-103">Questo tipo è stato usato per essere definito in [Microsoft. AspNetCore. Mvc. Formatters. JSON](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json).</span><span class="sxs-lookup"><span data-stu-id="2630e-103">This type used to be defined in [Microsoft.AspNetCore.Mvc.Formatters.Json](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json).</span></span> <span data-ttu-id="2630e-104">Un attributo a livello di assembly [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) è stato aggiunto al `Microsoft.AspNetCore.Mvc.Formatters.Json` per risolvere questo problema per la maggior parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="2630e-104">An assembly-level [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) attribute was added to `Microsoft.AspNetCore.Mvc.Formatters.Json` to address this issue for the majority of users.</span></span> <span data-ttu-id="2630e-105">È possibile che si verifichino problemi nelle app che usano librerie di terze parti.</span><span class="sxs-lookup"><span data-stu-id="2630e-105">Apps that use third-party libraries may encounter issues.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2630e-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="2630e-106">Version introduced</span></span>

<span data-ttu-id="2630e-107">3,0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="2630e-107">3.0 Preview 6</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="2630e-108">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="2630e-108">Old behavior</span></span>

<span data-ttu-id="2630e-109">Un'app che usa una libreria basata su 2,2 è stata compilata correttamente.</span><span class="sxs-lookup"><span data-stu-id="2630e-109">An app using a 2.2-based library builds successfully.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="2630e-110">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="2630e-110">New behavior</span></span>

<span data-ttu-id="2630e-111">Un'app che usa una libreria basata su 2,2 non riesce a compilare.</span><span class="sxs-lookup"><span data-stu-id="2630e-111">An app using a 2.2-based library fails compilation.</span></span> <span data-ttu-id="2630e-112">Viene fornito un errore contenente una variante del testo seguente:</span><span class="sxs-lookup"><span data-stu-id="2630e-112">An error containing a variation of the following text is provided:</span></span>

```
The type 'JsonResult' exists in both 'Microsoft.AspNetCore.Mvc.Core, Version=3.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60' and 'Microsoft.AspNetCore.Mvc.Formatters.Json, Version=2.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60'
```

<span data-ttu-id="2630e-113">Per un esempio di questo problema, vedere [ASPNET/AspNetCore # 7220](https://github.com/aspnet/AspNetCore/issues/7220).</span><span class="sxs-lookup"><span data-stu-id="2630e-113">For an example of such an issue, see [aspnet/AspNetCore#7220](https://github.com/aspnet/AspNetCore/issues/7220).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2630e-114">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="2630e-114">Reason for change</span></span>

<span data-ttu-id="2630e-115">Modifiche a livello di piattaforma per la composizione di ASP.NET Core come descritto in [ASPNET/annunciations # 325](https://github.com/aspnet/Announcements/issues/325).</span><span class="sxs-lookup"><span data-stu-id="2630e-115">Platform-level changes to the composition of ASP.NET Core as described at [aspnet/Announcements#325](https://github.com/aspnet/Announcements/issues/325).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2630e-116">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="2630e-116">Recommended action</span></span>

<span data-ttu-id="2630e-117">Per risolvere il problema relativo a tutti i consumer, potrebbe essere necessario ricompilare le librerie compilate con la versione 2,2 di `Microsoft.AspNetCore.Mvc.Formatters.Json`.</span><span class="sxs-lookup"><span data-stu-id="2630e-117">Libraries compiled against the 2.2 version of `Microsoft.AspNetCore.Mvc.Formatters.Json` may need to recompile to address the problem for all consumers.</span></span> <span data-ttu-id="2630e-118">Se interessato, contattare l'autore della libreria.</span><span class="sxs-lookup"><span data-stu-id="2630e-118">If affected, contact the library author.</span></span> <span data-ttu-id="2630e-119">Richiedere la ricompilazione della libreria come destinazione ASP.NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="2630e-119">Request recompilation of the library to target ASP.NET Core 3.0.</span></span>

#### <a name="category"></a><span data-ttu-id="2630e-120">Categoria</span><span class="sxs-lookup"><span data-stu-id="2630e-120">Category</span></span>

<span data-ttu-id="2630e-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2630e-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2630e-122">API interessate</span><span class="sxs-lookup"><span data-stu-id="2630e-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.JsonResult?displayProperty=nameWithType>

<!-- 

### Affected APIs

`T:Microsoft.AspNetCore.Mvc.JsonResult`

-->

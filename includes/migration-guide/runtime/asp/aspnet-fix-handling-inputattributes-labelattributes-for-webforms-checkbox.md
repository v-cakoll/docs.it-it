---
ms.openlocfilehash: ae557ce57557d027dba35b7da213c08aee85f2c7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621974"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a><span data-ttu-id="c87ad-101">Gestione delle correzioni ASP.NET di InputAttributes e LabelAttributes per il controllo CheckBox di WebForms</span><span class="sxs-lookup"><span data-stu-id="c87ad-101">ASP.NET Fix handling of InputAttributes and LabelAttributes for WebForms CheckBox control</span></span>

#### <a name="details"></a><span data-ttu-id="c87ad-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c87ad-102">Details</span></span>

<span data-ttu-id="c87ad-103">Per le applicazioni destinate a .NET Framework 4.7.2 e versioni precedenti, le proprietà <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> e <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> aggiunte a livello di codice a un controllo <xref:System.Web.UI.WebControls.CheckBox> di WebForms vengono perse dopo il postback.</span><span class="sxs-lookup"><span data-stu-id="c87ad-103">For applications that target .NET Framework 4.7.2 and earlier versions, <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> that are programmatically added to a WebForms <xref:System.Web.UI.WebControls.CheckBox> control are lost after postback.</span></span> <span data-ttu-id="c87ad-104">Per le applicazioni destinate a .NET Framework 4.8 o versioni successive, vengono mantenute dopo il postback.</span><span class="sxs-lookup"><span data-stu-id="c87ad-104">For applications that target .NET Framework 4.8 or later versions, they are preserved after postback.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c87ad-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="c87ad-105">Suggestion</span></span>

<span data-ttu-id="c87ad-106">Per il comportamento corretto per il ripristino degli attributi durante il postback, impostare <code>targetFrameworkVersion</code> sulla versione 4.8 o successiva.</span><span class="sxs-lookup"><span data-stu-id="c87ad-106">For the correct behavior for restoring attributes on postback, set the <code>targetFrameworkVersion</code> to 4.8 or higher.</span></span> <span data-ttu-id="c87ad-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c87ad-107">For example:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><span data-ttu-id="c87ad-108">Se viene impostata una versione precedente o se non viene impostata alcuna versione, viene riprodotto il comportamento errato.</span><span class="sxs-lookup"><span data-stu-id="c87ad-108">Setting it lower, or not at all, preserves the old incorrect behavior.</span></span>

| <span data-ttu-id="c87ad-109">Nome</span><span class="sxs-lookup"><span data-stu-id="c87ad-109">Name</span></span>    | <span data-ttu-id="c87ad-110">Valore</span><span class="sxs-lookup"><span data-stu-id="c87ad-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c87ad-111">Scope</span><span class="sxs-lookup"><span data-stu-id="c87ad-111">Scope</span></span>   |<span data-ttu-id="c87ad-112">Sconosciuto</span><span class="sxs-lookup"><span data-stu-id="c87ad-112">Unknown</span></span>|
|<span data-ttu-id="c87ad-113">Version</span><span class="sxs-lookup"><span data-stu-id="c87ad-113">Version</span></span>|<span data-ttu-id="c87ad-114">4.8</span><span class="sxs-lookup"><span data-stu-id="c87ad-114">4.8</span></span>|
|<span data-ttu-id="c87ad-115">Type</span><span class="sxs-lookup"><span data-stu-id="c87ad-115">Type</span></span>|<span data-ttu-id="c87ad-116">Runtime</span><span class="sxs-lookup"><span data-stu-id="c87ad-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c87ad-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="c87ad-117">Affected APIs</span></span>

-<xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType></li></ul>|

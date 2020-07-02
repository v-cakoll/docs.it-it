---
ms.openlocfilehash: 3b329bf5ba2af4d3ab9c3e203e99daba8ca0d0c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620140"
---
### <a name="gridviews-with-allowcustompaging-set-to-true-may-fire-the-pageindexchanging-event-when-leaving-the-final-page-of-the-view"></a><span data-ttu-id="47acd-101">GridViews con AllowCustomPaging impostato su true può generare l'evento PageIndexChanging quando si esce dalla pagina finale della visualizzazione</span><span class="sxs-lookup"><span data-stu-id="47acd-101">GridViews with AllowCustomPaging set to true may fire the PageIndexChanging event when leaving the final page of the view</span></span>

#### <a name="details"></a><span data-ttu-id="47acd-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="47acd-102">Details</span></span>

<span data-ttu-id="47acd-103">A causa di un bug in .NET Framework 4.5, <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName> a volte non viene generato per le classi <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> che hanno abilitato la proprietà <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="47acd-103">A bug in the .NET Framework 4.5 causes <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName> to sometimes not fire for <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName>s that have enabled <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="47acd-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="47acd-104">Suggestion</span></span>

<span data-ttu-id="47acd-105">Questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="47acd-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span> <span data-ttu-id="47acd-106">Come soluzione alternativa, l'app può eseguire un'operazione BindGrid esplicita su qualsiasi <code>Page_Load</code> che soddisfi queste condizioni (la classe <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> è nell'ultima pagina e la proprietà Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> è diversa da <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="47acd-106">As a work-around, the app can do an explicit BindGrid on any <code>Page_Load</code> that would hit these conditions (the <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> is on the last page and Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> is different from <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>).</span></span> <span data-ttu-id="47acd-107">Oppure è possibile modificare l'app in modo da consentire il paging (anziché il paging personalizzato), poiché in questo scenario il problema non si verifica.</span><span class="sxs-lookup"><span data-stu-id="47acd-107">Alternatively, the app can be modified to allow paging (instead of custom paging), as that scenario does not demonstrate the problem.</span></span>

| <span data-ttu-id="47acd-108">Nome</span><span class="sxs-lookup"><span data-stu-id="47acd-108">Name</span></span>    | <span data-ttu-id="47acd-109">Valore</span><span class="sxs-lookup"><span data-stu-id="47acd-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="47acd-110">Scope</span><span class="sxs-lookup"><span data-stu-id="47acd-110">Scope</span></span>   |<span data-ttu-id="47acd-111">Minorenne</span><span class="sxs-lookup"><span data-stu-id="47acd-111">Minor</span></span>|
|<span data-ttu-id="47acd-112">Version</span><span class="sxs-lookup"><span data-stu-id="47acd-112">Version</span></span>|<span data-ttu-id="47acd-113">4.5</span><span class="sxs-lookup"><span data-stu-id="47acd-113">4.5</span></span>|
|<span data-ttu-id="47acd-114">Type</span><span class="sxs-lookup"><span data-stu-id="47acd-114">Type</span></span>|<span data-ttu-id="47acd-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="47acd-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="47acd-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="47acd-116">Affected APIs</span></span>

-<xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=nameWithType></li></ul>|

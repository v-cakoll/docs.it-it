---
ms.openlocfilehash: 8f03e5166e7f1f598e9bba7fb8c550809f287b82
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615649"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a><span data-ttu-id="80b88-101">HtmlTextWriter non esegue correttamente il rendering dell'elemento `<br/>`</span><span class="sxs-lookup"><span data-stu-id="80b88-101">HtmlTextWriter does not render `<br/>` element correctly</span></span>

#### <a name="details"></a><span data-ttu-id="80b88-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="80b88-102">Details</span></span>

<span data-ttu-id="80b88-103">A partire da .NET Framework 4.6, la chiamata di <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> e <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> con un elemento `<BR />` inserirà correttamente solo un `<BR />` (invece di due)</span><span class="sxs-lookup"><span data-stu-id="80b88-103">Beginning in the .NET Framework 4.6, calling <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> and <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> with a `<BR />` element will correctly insert only one `<BR />` (instead of two)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="80b88-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="80b88-104">Suggestion</span></span>

<span data-ttu-id="80b88-105">Se un'app dipende dal tag `<BR />` aggiuntivo, il metodo <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> deve essere chiamato una seconda volta.</span><span class="sxs-lookup"><span data-stu-id="80b88-105">If an app depended on the extra `<BR />` tag, <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> should be called a second time.</span></span> <span data-ttu-id="80b88-106">Si noti che questa modifica di comportamento influisce solo sulle app destinate a .NET Framework 4.6 o versioni successive, quindi è possibile in alternativa selezionare una versione precedente di .NET Framework come destinazione per ottenere il comportamento precedente.</span><span class="sxs-lookup"><span data-stu-id="80b88-106">Note that this behavior change only affects apps that target the .NET Framework 4.6 or later, so another option is to target a previous version of the .NET Framework in order to get the old behavior.</span></span>

| <span data-ttu-id="80b88-107">Nome</span><span class="sxs-lookup"><span data-stu-id="80b88-107">Name</span></span>    | <span data-ttu-id="80b88-108">Valore</span><span class="sxs-lookup"><span data-stu-id="80b88-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="80b88-109">Scope</span><span class="sxs-lookup"><span data-stu-id="80b88-109">Scope</span></span>   | <span data-ttu-id="80b88-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="80b88-110">Edge</span></span>        |
| <span data-ttu-id="80b88-111">Version</span><span class="sxs-lookup"><span data-stu-id="80b88-111">Version</span></span> | <span data-ttu-id="80b88-112">4.6</span><span class="sxs-lookup"><span data-stu-id="80b88-112">4.6</span></span>         |
| <span data-ttu-id="80b88-113">Type</span><span class="sxs-lookup"><span data-stu-id="80b88-113">Type</span></span>    | <span data-ttu-id="80b88-114">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="80b88-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="80b88-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="80b88-115">Affected APIs</span></span>

- <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType>
- <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType>

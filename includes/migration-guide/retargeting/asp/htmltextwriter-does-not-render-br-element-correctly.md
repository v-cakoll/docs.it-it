---
ms.openlocfilehash: e600b8249096eecb13f63ea00343a771a8c12b60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804413"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a><span data-ttu-id="0d627-101">HtmlTextWriter non esegue correttamente il rendering dell'elemento `<br/>`</span><span class="sxs-lookup"><span data-stu-id="0d627-101">HtmlTextWriter does not render `<br/>` element correctly</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0d627-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0d627-102">Details</span></span>|<span data-ttu-id="0d627-103">A partire da .NET Framework 4.6, la chiamata di <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> e <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> con un elemento <code>&lt;BR /&gt;</code> inserirà correttamente solo un <code>&lt;BR /&gt;</code> (invece di due)</span><span class="sxs-lookup"><span data-stu-id="0d627-103">Beginning in the .NET Framework 4.6, calling <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> and <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> with a <code>&lt;BR /&gt;</code> element will correctly insert only one <code>&lt;BR /&gt;</code> (instead of two)</span></span>|
|<span data-ttu-id="0d627-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="0d627-104">Suggestion</span></span>|<span data-ttu-id="0d627-105">Se un'app dipende dal tag <code>&lt;BR /&gt;</code> aggiuntivo, il metodo <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> deve essere chiamato una seconda volta.</span><span class="sxs-lookup"><span data-stu-id="0d627-105">If an app depended on the extra <code>&lt;BR /&gt;</code> tag, <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> should be called a second time.</span></span> <span data-ttu-id="0d627-106">Si noti che questa modifica di comportamento influisce solo sulle app destinate a .NET Framework 4.6 o versioni successive, quindi è possibile in alternativa selezionare una versione precedente di .NET Framework come destinazione per ottenere il comportamento precedente.</span><span class="sxs-lookup"><span data-stu-id="0d627-106">Note that this behavior change only affects apps that target the .NET Framework 4.6 or later, so another option is to target a previous version of the .NET Framework in order to get the old behavior.</span></span>|
|<span data-ttu-id="0d627-107">Scope</span><span class="sxs-lookup"><span data-stu-id="0d627-107">Scope</span></span>|<span data-ttu-id="0d627-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0d627-108">Edge</span></span>|
|<span data-ttu-id="0d627-109">Versione</span><span class="sxs-lookup"><span data-stu-id="0d627-109">Version</span></span>|<span data-ttu-id="0d627-110">4.6</span><span class="sxs-lookup"><span data-stu-id="0d627-110">4.6</span></span>|
|<span data-ttu-id="0d627-111">Type</span><span class="sxs-lookup"><span data-stu-id="0d627-111">Type</span></span>|<span data-ttu-id="0d627-112">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="0d627-112">Retargeting</span></span>|
|<span data-ttu-id="0d627-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="0d627-113">Affected APIs</span></span>|<ul><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType></li></ul>|

---
ms.openlocfilehash: 0ab6be6f2c6d8ebbe67051e4e3f967a325e654c8
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804413"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a><span data-ttu-id="a6c48-101">HtmlTextWriter non esegue correttamente il rendering dell'elemento `<br/>`</span><span class="sxs-lookup"><span data-stu-id="a6c48-101">HtmlTextWriter does not render `<br/>` element correctly</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a6c48-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a6c48-102">Details</span></span>|<span data-ttu-id="a6c48-103">A partire da .NET Framework 4.6, la chiamata di <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> e <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> con un elemento <code>&lt;BR /&gt;</code> inserirà correttamente solo un <code>&lt;BR /&gt;</code> (invece di due)</span><span class="sxs-lookup"><span data-stu-id="a6c48-103">Beginning in the .NET Framework 4.6, calling <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> and <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> with a <code>&lt;BR /&gt;</code> element will correctly insert only one <code>&lt;BR /&gt;</code> (instead of two)</span></span>|
|<span data-ttu-id="a6c48-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="a6c48-104">Suggestion</span></span>|<span data-ttu-id="a6c48-105">Se un'app dipende dal tag <code>&lt;BR /&gt;</code> aggiuntivo, il metodo <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> deve essere chiamato una seconda volta.</span><span class="sxs-lookup"><span data-stu-id="a6c48-105">If an app depended on the extra <code>&lt;BR /&gt;</code> tag, <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> should be called a second time.</span></span> <span data-ttu-id="a6c48-106">Si noti che questa modifica di comportamento influisce solo sulle app destinate a .NET Framework 4.6 o versioni successive, quindi è possibile in alternativa selezionare una versione precedente di .NET Framework come destinazione per ottenere il comportamento precedente.</span><span class="sxs-lookup"><span data-stu-id="a6c48-106">Note that this behavior change only affects apps that target the .NET Framework 4.6 or later, so another option is to target a previous version of the .NET Framework in order to get the old behavior.</span></span>|
|<span data-ttu-id="a6c48-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="a6c48-107">Scope</span></span>|<span data-ttu-id="a6c48-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a6c48-108">Edge</span></span>|
|<span data-ttu-id="a6c48-109">Versione</span><span class="sxs-lookup"><span data-stu-id="a6c48-109">Version</span></span>|<span data-ttu-id="a6c48-110">4.6</span><span class="sxs-lookup"><span data-stu-id="a6c48-110">4.6</span></span>|
|<span data-ttu-id="a6c48-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="a6c48-111">Type</span></span>|<span data-ttu-id="a6c48-112">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="a6c48-112">Retargeting</span></span>|
|<span data-ttu-id="a6c48-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="a6c48-113">Affected APIs</span></span>|<ul><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType></li></ul>|


---
ms.openlocfilehash: 0470cefc05fb5da6a6195ee0a96f04feef01fd10
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620434"
---
### <a name="flowdocument-may-show-an-extra-line-of-text"></a><span data-ttu-id="2685a-101">FlowDocument può visualizzare una riga di testo aggiuntiva</span><span class="sxs-lookup"><span data-stu-id="2685a-101">FlowDocument may show an extra line of text</span></span>

#### <a name="details"></a><span data-ttu-id="2685a-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2685a-102">Details</span></span>

<span data-ttu-id="2685a-103">In alcuni casi, un elemento <xref:System.Windows.Documents.FlowDocument> visualizzerà una riga di testo aggiuntiva quando è in esecuzione in .NET Framework 4.5 rispetto a quanto viene visualizzato quando è in esecuzione in .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="2685a-103">In some cases, a <xref:System.Windows.Documents.FlowDocument> element will display an extra line of text when running on the .NET Framework 4.5 compared to how it displayed when run on the .NET Framework 4.0.</span></span> <span data-ttu-id="2685a-104">Non esistono casi noti del fatto che la modifica causi la visualizzazione non chiara o non leggibile del testo, ma potrebbe determinare la visualizzazione di testo in precedenza omesso dalla visualizzazione di <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="2685a-104">There are no known cases of the change causing any text to be displayed poorly or illegibly, but it could cause text to appear that previously was omitted from a <xref:System.Windows.Documents.FlowDocument>'s view.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2685a-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="2685a-105">Suggestion</span></span>

<span data-ttu-id="2685a-106">In alcuni casi, la riduzione della proprietà PageHeight dell'elemento visualizzato di una unità può ripristinare il numero di righe visualizzate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2685a-106">In some cases, decreasing the display element's PageHeight property by one can restore the previous number of displayed lines.</span></span>

| <span data-ttu-id="2685a-107">Nome</span><span class="sxs-lookup"><span data-stu-id="2685a-107">Name</span></span>    | <span data-ttu-id="2685a-108">Valore</span><span class="sxs-lookup"><span data-stu-id="2685a-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2685a-109">Scope</span><span class="sxs-lookup"><span data-stu-id="2685a-109">Scope</span></span>   |<span data-ttu-id="2685a-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2685a-110">Edge</span></span>|
|<span data-ttu-id="2685a-111">Version</span><span class="sxs-lookup"><span data-stu-id="2685a-111">Version</span></span>|<span data-ttu-id="2685a-112">4.5</span><span class="sxs-lookup"><span data-stu-id="2685a-112">4.5</span></span>|
|<span data-ttu-id="2685a-113">Type</span><span class="sxs-lookup"><span data-stu-id="2685a-113">Type</span></span>|<span data-ttu-id="2685a-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="2685a-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2685a-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="2685a-115">Affected APIs</span></span>

-<xref:System.Windows.Documents.FlowDocument.%23ctor></li><li><xref:System.Windows.Documents.FlowDocument.%23ctor(System.Windows.Documents.Block)></li><li><xref:System.Windows.Controls.FlowDocumentReader.%23ctor></li><li><xref:System.Windows.Controls.FlowDocumentPageViewer.%23ctor></li><li><xref:System.Windows.Controls.Primitives.DocumentPageView.%23ctor></li></ul>|

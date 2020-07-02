---
ms.openlocfilehash: 00ffc782c9a15c0d88f797f52372b4658706b350
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620425"
---
### <a name="glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-framework-45"></a><span data-ttu-id="b5d78-101">A partire da .NET Framework 4.5, GlyphRun.ComputeInkBoundingBox() e FormattedText.Extent restituiscono valori diversi</span><span class="sxs-lookup"><span data-stu-id="b5d78-101">GlyphRun.ComputeInkBoundingBox() and FormattedText.Extent return different values beginning in .NET Framework 4.5</span></span>

#### <a name="details"></a><span data-ttu-id="b5d78-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b5d78-102">Details</span></span>

<span data-ttu-id="b5d78-103">Sono stati apportati miglioramenti a <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> e <xref:System.Windows.Media.FormattedText.Extent> in .NET Framework 4.5 per risolvere i problemi a causa dei quali i rettangoli di selezione sono troppo piccoli per i glifi contenuti in alcuni casi in .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="b5d78-103">Improvements were made to <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> and <xref:System.Windows.Media.FormattedText.Extent> in the .NET Framework 4.5 to address issues where the boxes were too small for the contained glyphs in some cases in the .NET Framework 4.0.</span></span> <span data-ttu-id="b5d78-104">Ne consegue che alcuni rettangoli di selezione sono più grandi a partire da .NET Framework 4.5 e quindi si noteranno alcune piccole differenze nel layout dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="b5d78-104">As a result of this, some bounding boxes will be larger beginning in the .NET Framework 4.5, resulting in subtle differences in UI layout.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b5d78-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="b5d78-105">Suggestion</span></span>

<span data-ttu-id="b5d78-106">Tenere presente che le dimensioni di alcuni rettangoli di selezione con glifi sono aumentate.</span><span class="sxs-lookup"><span data-stu-id="b5d78-106">Be aware that some glyph bounding box sizes have increased.</span></span> <span data-ttu-id="b5d78-107">Queste modifiche consentiranno in genere di migliorare la presentazione e l'hit testing per i rettangoli, ma se si preferisce il comportamento precedente alla versione .NET 4.5, è possibile sceglierlo in modo esplicito aggiungendo la voce seguente al file app.config:</span><span class="sxs-lookup"><span data-stu-id="b5d78-107">These changes will usually improve presentation and hit box testing, but if the older (pre-.NET 4.5) behavior is desired, it can be opted into by adding the following entry to the app.config file:</span></span><pre><code class="lang-xml">&lt;appsettings&gt;&#13;&#10;&lt;add key=&quot;IncludeAllInkInBoundingBox&quot; value=&quot;false&quot;&gt;&#13;&#10;&lt;/appsettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="b5d78-108">Nome</span><span class="sxs-lookup"><span data-stu-id="b5d78-108">Name</span></span>    | <span data-ttu-id="b5d78-109">Valore</span><span class="sxs-lookup"><span data-stu-id="b5d78-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b5d78-110">Scope</span><span class="sxs-lookup"><span data-stu-id="b5d78-110">Scope</span></span>   |<span data-ttu-id="b5d78-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b5d78-111">Edge</span></span>|
|<span data-ttu-id="b5d78-112">Version</span><span class="sxs-lookup"><span data-stu-id="b5d78-112">Version</span></span>|<span data-ttu-id="b5d78-113">4.5</span><span class="sxs-lookup"><span data-stu-id="b5d78-113">4.5</span></span>|
|<span data-ttu-id="b5d78-114">Type</span><span class="sxs-lookup"><span data-stu-id="b5d78-114">Type</span></span>|<span data-ttu-id="b5d78-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="b5d78-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b5d78-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="b5d78-116">Affected APIs</span></span>

-<xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=nameWithType></li><li><xref:System.Windows.Media.FormattedText.Extent?displayProperty=nameWithType></li></ul>|

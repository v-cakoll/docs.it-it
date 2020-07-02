---
ms.openlocfilehash: 00ffc782c9a15c0d88f797f52372b4658706b350
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620425"
---
### <a name="glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-framework-45"></a>A partire da .NET Framework 4.5, GlyphRun.ComputeInkBoundingBox() e FormattedText.Extent restituiscono valori diversi

#### <a name="details"></a>Dettagli

Sono stati apportati miglioramenti a <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> e <xref:System.Windows.Media.FormattedText.Extent> in .NET Framework 4.5 per risolvere i problemi a causa dei quali i rettangoli di selezione sono troppo piccoli per i glifi contenuti in alcuni casi in .NET Framework 4.0. Ne consegue che alcuni rettangoli di selezione sono più grandi a partire da .NET Framework 4.5 e quindi si noteranno alcune piccole differenze nel layout dell'interfaccia utente.

#### <a name="suggestion"></a>Suggerimento

Tenere presente che le dimensioni di alcuni rettangoli di selezione con glifi sono aumentate. Queste modifiche consentiranno in genere di migliorare la presentazione e l'hit testing per i rettangoli, ma se si preferisce il comportamento precedente alla versione .NET 4.5, è possibile sceglierlo in modo esplicito aggiungendo la voce seguente al file app.config:<pre><code class="lang-xml">&lt;appsettings&gt;&#13;&#10;&lt;add key=&quot;IncludeAllInkInBoundingBox&quot; value=&quot;false&quot;&gt;&#13;&#10;&lt;/appsettings&gt;&#13;&#10;</code></pre>

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=nameWithType></li><li><xref:System.Windows.Media.FormattedText.Extent?displayProperty=nameWithType></li></ul>|

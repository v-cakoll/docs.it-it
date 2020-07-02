---
ms.openlocfilehash: 0470cefc05fb5da6a6195ee0a96f04feef01fd10
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620434"
---
### <a name="flowdocument-may-show-an-extra-line-of-text"></a>FlowDocument può visualizzare una riga di testo aggiuntiva

#### <a name="details"></a>Dettagli

In alcuni casi, un elemento <xref:System.Windows.Documents.FlowDocument> visualizzerà una riga di testo aggiuntiva quando è in esecuzione in .NET Framework 4.5 rispetto a quanto viene visualizzato quando è in esecuzione in .NET Framework 4.0. Non esistono casi noti del fatto che la modifica causi la visualizzazione non chiara o non leggibile del testo, ma potrebbe determinare la visualizzazione di testo in precedenza omesso dalla visualizzazione di <xref:System.Windows.Documents.FlowDocument>.

#### <a name="suggestion"></a>Suggerimento

In alcuni casi, la riduzione della proprietà PageHeight dell'elemento visualizzato di una unità può ripristinare il numero di righe visualizzate in precedenza.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Windows.Documents.FlowDocument.%23ctor></li><li><xref:System.Windows.Documents.FlowDocument.%23ctor(System.Windows.Documents.Block)></li><li><xref:System.Windows.Controls.FlowDocumentReader.%23ctor></li><li><xref:System.Windows.Controls.FlowDocumentPageViewer.%23ctor></li><li><xref:System.Windows.Controls.Primitives.DocumentPageView.%23ctor></li></ul>|

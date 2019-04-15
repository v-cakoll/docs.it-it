---
ms.openlocfilehash: 6c1740df66ead271afa5f97dc125587810946bc6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235445"
---
### <a name="flowdocument-may-show-an-extra-line-of-text"></a>FlowDocument può visualizzare una riga di testo aggiuntiva

|   |   |
|---|---|
|Dettagli|In alcuni casi, un elemento <xref:System.Windows.Documents.FlowDocument> visualizzerà una riga di testo aggiuntiva quando è in esecuzione in .NET Framework 4.5 rispetto a quanto viene visualizzato quando è in esecuzione in .NET Framework 4.0. Non esistono casi noti del fatto che la modifica causi la visualizzazione non chiara o non leggibile del testo, ma potrebbe determinare la visualizzazione di testo in precedenza omesso dalla visualizzazione di <xref:System.Windows.Documents.FlowDocument>.|
|Suggerimento|In alcuni casi, la riduzione della proprietà PageHeight dell'elemento visualizzato di una unità può ripristinare il numero di righe visualizzate in precedenza.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Windows.Documents.FlowDocument.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Documents.FlowDocument.%23ctor(System.Windows.Documents.Block)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.FlowDocumentReader.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.FlowDocumentPageViewer.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.DocumentPageView.%23ctor?displayProperty=nameWithType></li></ul>|

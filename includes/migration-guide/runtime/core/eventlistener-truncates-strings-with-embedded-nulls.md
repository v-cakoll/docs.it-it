---
ms.openlocfilehash: 9084c135769f595491d645e49d24cf507f5f6070
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235634"
---
### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a>EventListener tronca le stringhe con valori Null incorporati

|   |   |
|---|---|
|Dettagli|<xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> tronca le stringhe con valori null incorporati. I caratteri null non sono supportati dalla classe <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name>. La modifica influisce solo sulle app che usano <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> per leggere i dati <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> in-process e che usano i caratteri null come delimitatori.|
|Suggerimento|<xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> I dati EventSource devono essere aggiornati, se possibile, in modo da non usare caratteri Null incorporati.|
|Ambito|Microsoft Edge|
|Versione|4.5.1|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Diagnostics.Tracing.EventListener.%23ctor?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType></li></ul>|

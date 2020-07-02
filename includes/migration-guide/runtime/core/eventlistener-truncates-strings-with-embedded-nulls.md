---
ms.openlocfilehash: 6f5c1ecead4e2f74e621354058aab70bfa1cccb6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620224"
---
### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a>EventListener tronca le stringhe con valori Null incorporati

#### <a name="details"></a>Dettagli

<xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> tronca le stringhe con valori null incorporati. I caratteri null non sono supportati dalla classe <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>. La modifica influisce solo sulle app che usano <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> per leggere i dati <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> in-process e che usano i caratteri null come delimitatori.

#### <a name="suggestion"></a>Suggerimento

I dati <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> devono essere aggiornati, se possibile, in modo da non usare caratteri Null incorporati.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5.1|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Diagnostics.Tracing.EventListener.%23ctor></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType></li></ul>|

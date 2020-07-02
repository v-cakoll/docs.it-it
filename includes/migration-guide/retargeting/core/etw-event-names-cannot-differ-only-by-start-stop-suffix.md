---
ms.openlocfilehash: 0e25d5d9b545e5cb400cbf701fb13da572fadf10
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614456"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a>I nomi di eventi ETW non possono essere diversi solo per il suffisso "Start" o "Stop"

#### <a name="details"></a>Dettagli

Nel .NET Framework 4,6 e 4.6.1, il runtime genera un'eccezione <xref:System.ArgumentException> quando due Event Tracing for Windows (ETW) si differenziano solo per un suffisso "Start" o "Stop", ad esempio quando un evento è denominato `LogUser` e un altro è denominato `LogUserStart` . In questo caso, il runtime non può creare l'origine dell'evento, quindi non viene generata alcuna registrazione.

#### <a name="suggestion"></a>Suggerimento

Per evitare l'eccezione, assicurarsi che non siano presenti due nomi di evento diversi solo per il suffisso "Start" o "Stop". Questo requisito viene rimosso a partire da .NET Framework 4.6.2; il runtime può evitare ambiguità tra i nomi di evento che differiscono solo per il suffisso "Start" e "Stop".

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.6         |
| Type    | Ridestinazione |

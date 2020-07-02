---
ms.openlocfilehash: 662c140f019add66ff6605d47ad1f32c3f50d711
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620241"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>EventSource.WriteEvent impls deve passare a WriteEvent gli stessi parametri che ha ricevuto (oltre all'ID)

#### <a name="details"></a>Dettagli

Il runtime applica ora il contratto che specifica quanto segue: Una classe derivata da <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> che definisce un metodo di eventi ETW deve chiamare il metodo <code>EventSource.WriteEvent</code> della classe di base con l'ID evento seguito dagli stessi argomenti passati al metodo eventi ETW.

#### <a name="suggestion"></a>Suggerimento

Viene generata un'eccezione <xref:System.IndexOutOfRangeException?displayProperty=fullName> se un <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> legge i dati <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> in-process per un'origine evento che viola questo contratto.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5.1|
|Type|Runtime|

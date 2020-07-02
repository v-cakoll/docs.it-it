---
ms.openlocfilehash: f7dcf9c4c3dc7ea536ddc847769a1a30f1298bb2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617214"
---
### <a name="systemuriiswellformeduristring-method-returns-false-for-relative-uris-with-a-colon-char-in-first-segment"></a>Il metodo System.Uri.IsWellFormedUriString restituisce false per gli URI relativi con un carattere due punti nel primo segmento

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.5, <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)> tratterà gli URI relativi con `:` nella primo segmento come non ben formati. Si tratta di una modifica rispetto al comportamento di <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> in .NET Framework 4.0, introdotta per conformarsi a RFC3986.

#### <a name="suggestion"></a>Suggerimento

Questa modifica (come molte altre modifiche relative agli URI) influirà solo sulle applicazioni destinate a .NET Framework 4.5 o versioni successive. Per continuare a usare il comportamento precedente, scegliere .NET Framework 4.0 come destinazione dell'app. In alternativa, analizzare l'URI prima di chiamare <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> per cercare caratteri `:` che è possibile rimuovere ai fini della convalida, se si desidera mantenere il comportamento precedente.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.5         |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=nameWithType>

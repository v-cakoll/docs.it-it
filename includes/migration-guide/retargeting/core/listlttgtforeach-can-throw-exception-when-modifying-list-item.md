---
ms.openlocfilehash: 3300a74b81fc9eeba670ee0ceb2c2615fd3925bd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617219"
---
### <a name="listlttgtforeach-can-throw-exception-when-modifying-list-item"></a>List&lt;T&gt;.ForEach può generare un'eccezione quando si modifica una voce di elenco

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.5, un enumeratore <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> genera un'eccezione <xref:System.InvalidOperationException?displayProperty=fullName> in caso di modifica di un elemento nella raccolta chiamante. Nelle versioni precedenti questa condizione non genera un'eccezione ma può causare situazioni di race condition.

#### <a name="suggestion"></a>Suggerimento

Idealmente, il codice dovrebbe essere corretto per evitare la modifica degli elenchi durante l'enumerazione dei relativi elementi, perché questa non è mai un'operazione sicura. Per ripristinare il comportamento precedente, tuttavia, un'app può essere destinata a .NET Framework 4.0.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.5         |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType>

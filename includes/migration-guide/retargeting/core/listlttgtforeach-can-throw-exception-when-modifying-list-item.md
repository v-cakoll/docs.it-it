---
ms.openlocfilehash: 4e81087431091dfa4d5432d5ea5e2b665be2b130
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234745"
---
### <a name="listtforeach-can-throw-exception-when-modifying-list-item"></a>List\<T>.ForEach può generare un'eccezione quando si modifica una voce di elenco

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.5, un enumeratore <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> genera un'eccezione <xref:System.InvalidOperationException?displayProperty=name> in caso di modifica di un elemento nella raccolta chiamante. Nelle versioni precedenti questa condizione non genera un'eccezione ma può causare situazioni di race condition.|
|Suggerimento|Idealmente, il codice dovrebbe essere corretto per evitare la modifica degli elenchi durante l'enumerazione dei relativi elementi, perché questa non è mai un'operazione sicura. Per ripristinare il comportamento precedente, tuttavia, un'app può essere destinata a .NET Framework 4.0.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType></li></ul>|

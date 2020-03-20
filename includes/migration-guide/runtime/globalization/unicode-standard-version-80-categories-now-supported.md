---
ms.openlocfilehash: efa0efaf40e2e432d477f1659d7bde3abc98241d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857588"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a>Le categorie dello standard Unicode versione 8.0 sono ora supportate

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.6.2 i dati Unicode sono stati aggiornati dallo standard Unicode versione 6.3 alla versione 8.0.  Quando si richiedono le categorie di caratteri Unicode in .NET Framework 4.6.2, alcuni risultati potrebbero non corrispondere ai risultati ottenuti nelle versioni precedenti di .NET Framework.  Questa modifica interessa principalmente le sillabe Cherokee e i simboli delle vocali e dei toni di Tai Lue semplificato.|
|Suggerimento|Esaminare il codice e rimuovere o modificare la logica che dipende dalle categorie di caratteri Unicode hardcoded.|
|Scope|Minorenne|
|Versione|4.6.2|
|Type|Runtime|
|API interessate|<ul><li><xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|

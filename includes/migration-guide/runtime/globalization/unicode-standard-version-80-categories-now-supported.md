---
ms.openlocfilehash: a20fad5f9c95e59c14ffd91f4921cf8bfab443cd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621187"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a>Le categorie dello standard Unicode versione 8.0 sono ora supportate

#### <a name="details"></a>Dettagli

In .NET Framework 4.6.2 i dati Unicode sono stati aggiornati dallo standard Unicode versione 6.3 alla versione 8.0.  Quando si richiedono le categorie di caratteri Unicode in .NET Framework 4.6.2, alcuni risultati potrebbero non corrispondere ai risultati ottenuti nelle versioni precedenti di .NET Framework.  Questa modifica interessa principalmente le sillabe Cherokee e i simboli delle vocali e dei toni di Tai Lue semplificato.

#### <a name="suggestion"></a>Suggerimento

Esaminare il codice e rimuovere o modificare la logica che dipende dalle categorie di caratteri Unicode hardcoded.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.6.2|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|

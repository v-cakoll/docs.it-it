---
ms.openlocfilehash: c103dff320ae30d02c12ea5c585a47b589da8237
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621307"
---
### <a name="contentdisposition-datetimes-returns-slightly-different-string"></a>ContentDisposition DateTimes restituisce una stringa leggermente diversa

#### <a name="details"></a>Dettagli

Le rappresentazioni di stringa di <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName> sono state aggiornate, a partire dalla versione 4.6, in modo da rappresentare sempre il componente dell'ora di un valore <xref:System.DateTime?displayProperty=fullName> con due cifre. Questo comportamento è conforme a [RFC822](https://www.ietf.org/rfc/rfc0822.txt) e [RFC2822](https://www.ietf.org/rfc/rfc2822.txt). Ne consegue che <xref:System.Net.Mime.ContentDisposition.ToString> restituisce una stringa leggermente diversa nella versione 4.6 negli scenari in cui uno degli elementi di tempo della disposizione precede le 10.00. Si noti che i valori di ContentDisposition vengono a volte serializzati convertendoli in stringhe, pertanto è necessario verificare qualsiasi operazione <xref:System.Net.Mime.ContentDisposition.ToString>, la serializzazione o le chiamate di GetHashCode.

#### <a name="suggestion"></a>Suggerimento

Non dare per scontato che le rappresentazioni di stringa di ContentDisposition da versioni diverse di .NET Framework vengano confrontate correttamente. Se possibile, riconvertire le stringhe in ContentDisposition prima di eseguire un confronto.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.6|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=nameWithType></li><li><xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=nameWithType></li></ul>|

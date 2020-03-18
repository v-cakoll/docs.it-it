---
ms.openlocfilehash: d35de48dd22003c851cf5dba9e8517ec48b9217b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74567776"
---
### <a name="c-locale-maps-to-the-invariant-locale"></a>Le impostazioni locali "C" vengono mappate alle impostazioni locali invarianti

.NET Core 2.2 e versioni precedenti dipendono dal comportamento di iCU predefinito, che esegue il mapping delle impostazioni locali "C" alle impostazioni locali en_US_POSIX. Il en_US_POSIX impostazioni locali ha un comportamento di confronto indesiderato, perché non supporta i confronti tra stringhe senza distinzione tra maiuscole e minuscole. Poiché alcune distribuzioni Linux impostano le impostazioni locali "C" come impostazioni locali predefinite, gli utenti riscontravano un comportamento imprevisto.

#### <a name="change-description"></a>Descrizione modifica:

A partire da .NET Core 3.0, il mapping delle impostazioni locali "C" è stato modificato per utilizzare le impostazioni locali invarianti anziché en_US_POSIX. Le impostazioni locali "C" per il mapping invariante vengono applicate anche a Windows per coerenza.

Il mapping di "C" alle impostazioni cultura en_US_POSIX ha causato confusione tra i clienti, poiché en_US_POSIX non supporta le operazioni di ordinamento/ricerca delle stringhe senza distinzione tra maiuscole e minuscole. Poiché le impostazioni locali "C" vengono utilizzate come impostazioni locali predefinite in alcune delle distribuzioni Linux, i clienti hanno sperimentato questo comportamento indesiderato in questi sistemi operativi.

#### <a name="version-introduced"></a>Versione introdotta

3.0

### <a name="recommended-action"></a>Azione consigliata

Niente di più specifico della consapevolezza di questo cambiamento. Questa modifica interessa solo le applicazioni che utilizzano il mapping delle impostazioni locali "C".

### <a name="category"></a>Category

Globalizzazione

### <a name="affected-apis"></a>API interessate

Tutte le regole di confronto e le API delle impostazioni cultura sono interessate da questa modifica.

<!--

-->

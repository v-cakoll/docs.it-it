---
ms.openlocfilehash: d35de48dd22003c851cf5dba9e8517ec48b9217b
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198458"
---
### <a name="c-locale-maps-to-the-invariant-locale"></a>Le impostazioni locali "C" sono mappate alle impostazioni locali invariabili

.NET Core 2,2 e versioni precedenti dipendono dal comportamento ICU predefinito, che esegue il mapping delle impostazioni locali "C" alle impostazioni locali di en_US_POSIX. Le impostazioni locali en_US_POSIX hanno un comportamento indesiderato per le regole di confronto, poiché non supporta confronti tra stringhe senza distinzione tra maiuscole e minuscole. Poiché alcune distribuzioni di Linux impostano le impostazioni locali "C" come impostazioni locali predefinite, si è verificato un comportamento imprevisto per gli utenti.

#### <a name="change-description"></a>Descrizione della modifica

A partire da .NET Core 3,0, il mapping delle impostazioni locali "C" è stato modificato in modo da usare le impostazioni locali invariabili anziché en_US_POSIX. Le impostazioni locali "C" al mapping invariante vengono applicate anche a Windows per coerenza.

Il mapping di "C" alla cultura en_US_POSIX ha causato confusione dei clienti, perché en_US_POSIX non supporta operazioni di ordinamento/ricerca di stringhe senza distinzione tra maiuscole e minuscole. Poiché le impostazioni locali "C" vengono usate come impostazioni locali predefinite in alcune distribuzioni di Linux, i clienti hanno riscontrato questo comportamento indesiderato su questi sistemi operativi.

#### <a name="version-introduced"></a>Versione introdotta

3.0

### <a name="recommended-action"></a>Azione consigliata

Niente di più della conoscenza di questa modifica. Questa modifica interessa solo le applicazioni che usano il mapping delle impostazioni locali "C".

### <a name="category"></a>Category

Globalizzazione

### <a name="affected-apis"></a>API interessate

Questa modifica ha effetto su tutte le API per le regole di confronto e le impostazioni cultura.

<!--

-->

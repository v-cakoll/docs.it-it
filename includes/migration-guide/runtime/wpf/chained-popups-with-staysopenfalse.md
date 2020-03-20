---
ms.openlocfilehash: 22c4b61b293ac2366cae1dc73e0f6805a4a5fb8b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857248"
---
### <a name="chained-popups-with-staysopenfalse"></a>Popup concatenati con StaysOpen=False

|   |   |
|---|---|
|Dettagli|Un popup con StaysOpen=False deve chiudersi quando si fa clic all'esterno del popup. Due o più popup concatenati, ad esempio un popup che ne contiene un altro, causavano molti problemi, tra cui:<ul><li>Apertura di due livelli, clic all'esterno di P2, ma all'interno di P1.  Non accade nulla.</li><li>Apertura di due livelli, clic all'esterno di P1.  Entrambi i popup vengono chiusi.</li><li>Apertura e chiusura di due livelli.  Riapertura di P2.  Non accade nulla.</li><li>Apertura di tre livelli.  L'operazione non risulta possibile.  (Non succede nulla o i primi due livelli si chiudono, a seconda di dove si fa clic.) Questi casi (e altre varianti) ora funzionano come previsto.</li></ul>|
|Scope|Microsoft Edge|
|Versione|4.7.1|
|Type|Runtime|
|API interessate|<ul><li><xref:System.Windows.Controls.Primitives.Popup.StaysOpen?displayProperty=nameWithType></li></ul>|

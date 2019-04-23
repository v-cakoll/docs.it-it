---
ms.openlocfilehash: 22c4b61b293ac2366cae1dc73e0f6805a4a5fb8b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804266"
---
### <a name="chained-popups-with-staysopenfalse"></a>Popup concatenati con StaysOpen=False

|   |   |
|---|---|
|Dettagli|Un popup con StaysOpen=False deve chiudersi quando si fa clic all'esterno del popup. Due o più popup concatenati, ad esempio un popup che ne contiene un altro, causavano molti problemi, tra cui:<ul><li>Apertura di due livelli, clic all'esterno di P2, ma all'interno di P1.  Non accade nulla.</li><li>Apertura di due livelli, clic all'esterno di P1.  Entrambi i popup vengono chiusi.</li><li>Apertura e chiusura di due livelli.  Riapertura di P2.  Non accade nulla.</li><li>Apertura di tre livelli.  L'operazione non risulta possibile.  Non accade nulla o i primi due livelli si chiudono, a seconda del punto in cui si fa clic. Questi casi (e altre varianti) ora funzionano come previsto.</li></ul>|
|Ambito|Microsoft Edge|
|Versione|4.7.1|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Windows.Controls.Primitives.Popup.StaysOpen?displayProperty=nameWithType></li></ul>|

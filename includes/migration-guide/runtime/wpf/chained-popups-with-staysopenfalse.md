---
ms.openlocfilehash: 171b7a3a962f8259e64b88f1ae893e649b5f24bb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621256"
---
### <a name="chained-popups-with-staysopenfalse"></a>Popup concatenati con StaysOpen=False

#### <a name="details"></a>Dettagli

Un popup con StaysOpen=False deve chiudersi quando si fa clic all'esterno del popup. Due o più popup concatenati, ad esempio un popup che ne contiene un altro, causavano molti problemi, tra cui:<ul><li>Apertura di due livelli, clic all'esterno di P2, ma all'interno di P1.  Non accade nulla.</li><li>Apertura di due livelli, clic all'esterno di P1.  Entrambi i popup vengono chiusi.</li><li>Apertura e chiusura di due livelli.  Riapertura di P2.  Non accade nulla.</li><li>Apertura di tre livelli.  Non è possibile.  Non viene eseguita alcuna operazione o i primi due livelli si chiudono, a seconda della posizione in cui si fa clic. Questi casi (e altre varianti) funzionano ora come previsto.</li></ul>

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.7.1|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Windows.Controls.Primitives.Popup.StaysOpen?displayProperty=nameWithType></li></ul>|

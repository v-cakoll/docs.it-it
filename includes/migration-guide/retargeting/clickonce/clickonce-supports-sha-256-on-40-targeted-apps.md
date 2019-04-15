---
ms.openlocfilehash: 0358450024607a985f38564ec9743ba964949e8f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234490"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a>ClickOnce supporta SHA-256 per le app destinate alla versione 4.0

|   |   |
|---|---|
|Dettagli|In precedenza, un'app ClickOnce con certificato firmato con SHA-256 avrebbe richiesto la presenza di .NET Framework 4.5 o versioni successive, anche se l'app era destinata alla versione 4.0. È ora possibile eseguire le app ClickOnce destinate a .NET Framework 4.0 in .NET Framework 4.0, anche se firmate con SHA-256.|
|Suggerimento|Questa modifica rimuove tale dipendenza e consente di usare i certificati SHA-256 per firmare le app ClickOnce destinate a .NET Framework 4 e versioni precedenti.|
|Ambito|Secondario|
|Versione|4.6|
|Tipo|Ridestinazione|

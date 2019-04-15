---
ms.openlocfilehash: e8c48c4b1031813ce62f576e5bf1f94c082dfe4b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234701"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>L'attributo ObsoleteAttribute viene esportato sia come ObsoleteAttribute che come DeprecatedAttribute negli scenari WinMD

|   |   |
|---|---|
|Dettagli|Quando si crea una raccolta di metadati Windows (file con estensione winmd), l'attributo <xref:System.ObsoleteAttribute?displayProperty=name> viene esportato sia come <xref:System.ObsoleteAttribute?displayProperty=name> che come [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute).|
|Suggerimento|La ricompilazione del codice sorgente esistente che usa l'attributo <xref:System.ObsoleteAttribute?displayProperty=name> può generare avvisi quando si utilizza tale codice da C++/CX o JavaScript. È sconsigliabile applicare sia <xref:System.ObsoleteAttribute?displayProperty=name> che [ Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) al codice negli assembly gestiti, perché potrebbero essere generati avvisi di compilazione.|
|Ambito|Microsoft Edge|
|Versione|4.5.1|
|Tipo|Ridestinazione|

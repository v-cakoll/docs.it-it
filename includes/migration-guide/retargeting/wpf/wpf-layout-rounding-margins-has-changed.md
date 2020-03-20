---
ms.openlocfilehash: 73096e5f61e5257e062df9743cae0f5464892357
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804483"
---
### <a name="wpf-layout-rounding-of-margins-has-changed"></a>L'arrotondamento del layout dei margini in WPF è stato modificato

|   |   |
|---|---|
|Dettagli|Il modo in cui i margini vengono arrotondati e i bordi e lo sfondo al loro interno vengono modificati. Come conseguenza di questo cambiamento:<ul><li>La larghezza o l'altezza degli elementi può aumentare o diminuire al massimo di un pixel.</li><li>La posizione di un oggetto può cambiare al massimo di un pixel.</li><li>Gli elementi centrati possono risultare decentrati in orizzontale o in verticale al massimo di un pixel.</li></ul>Per impostazione predefinita, questo nuovo layout è disponibile solo per app destinate a .NET Framework 4.6.|
|Suggerimento|Poiché questa modifica tende a eliminare il ritaglio del lato destro o inferiore dei controlli WPF a DPI elevati, le app destinate a versioni precedenti di .NET Framework ma eseguite su .NET Framework 4.6 possono adottare questo nuovo comportamento aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false&quot; /&gt;&#39;&#13;&#10;</code></pre>Le app che usano .NET Framework 4.6, ma che richiedono che il rendering dei controlli WPF sia eseguito tramite l'algoritmo di layout precedente, possono aggiungere la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config per raggiungere tale scopo:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true&quot; /&gt;&#39;.&#13;&#10;</code></pre>|
|Scope|Minorenne|
|Versione|4.6|
|Type|Ridestinazione|

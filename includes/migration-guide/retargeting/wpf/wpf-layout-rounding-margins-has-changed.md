---
ms.openlocfilehash: f907cb1939e111c586d68243e6b8a8e291974e36
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615722"
---
### <a name="wpf-layout-rounding-of-margins-has-changed"></a>L'arrotondamento del layout dei margini in WPF è stato modificato

#### <a name="details"></a>Dettagli

Il modo in cui i margini vengono arrotondati e i bordi e lo sfondo al loro interno vengono modificati. Come conseguenza di questo cambiamento:

- La larghezza o l'altezza degli elementi può aumentare o diminuire al massimo di un pixel.
- La posizione di un oggetto può cambiare al massimo di un pixel.
- Gli elementi centrati possono risultare decentrati in orizzontale o in verticale al massimo di un pixel.
Per impostazione predefinita, questo nuovo layout è disponibile solo per app destinate a .NET Framework 4.6.

#### <a name="suggestion"></a>Suggerimento

Poiché questa modifica tende a eliminare il ritaglio del lato destro o inferiore dei controlli WPF a DPI elevati, le app destinate a versioni precedenti di .NET Framework ma eseguite su .NET Framework 4.6 possono adottare questo nuovo comportamento aggiungendo la riga seguente alla sezione `<runtime>` del file app.config:

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false&quot; /&gt;&#39;&#13;&#10;</code></pre>

Le app che usano .NET Framework 4.6, ma che richiedono che il rendering dei controlli WPF sia eseguito tramite l'algoritmo di layout precedente, possono aggiungere la riga seguente alla sezione `<runtime>` del file app.config per raggiungere tale scopo:

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true&quot; /&gt;&#39;.&#13;&#10;</code></pre>

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.6         |
| Type    | Ridestinazione |

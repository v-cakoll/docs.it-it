---
ms.openlocfilehash: 5df5afec17d400ed14fe9b4c03c2f754895f0dd7
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "66378758"
---
### <a name="resizing-a-grid-can-cause-an-application-to-become-unresponsive"></a>Un'applicazione smette di rispondere se una griglia viene ridimensionata

|   |   |
|---|---|
|Dettagli|Durante il layout di <code>T:System.Windows.Controls.Grid</code> può verificarsi un ciclo infinito nelle circostanze seguenti:<ul><li>Le definizioni di riga contengono due *-righe che dichiarano entrambe un valore MinHeight e MaxHeight.</li><li>Il contenuto delle *-righe non supera il valore MaxHeight corrispondente</li><li>L'altezza disponibile della griglia viene superata dal primo valore MinHeight (più qualsiasi altra riga automatica o fissa)</li><li>L'app è destinata a .NET Framework 4.7 o acconsente esplicitamente all'algoritmo di allocazione della versione 4.7 impostando <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code></li></ul>Il ciclo si verifica anche nel caso in cui siano presenti più di due righe o nel caso analogo per le colonne. Il problema è stato risolto in .NET Framework 4.7.1.|
|Suggerimento|Effettuare l'aggiornamento a .NET Framework 4.7.1.  In alternativa, se non è necessario l'algoritmo di allocazione della versione 4.7 è possibile usare l'impostazione di configurazione seguente:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ambito|Microsoft Edge|
|Versione|4.7|
|Tipo|Runtime|

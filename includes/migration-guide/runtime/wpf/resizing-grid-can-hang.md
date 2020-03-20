---
ms.openlocfilehash: eff7e7cfc8fa0b4bc8ee3a64a7c60ee21d51f466
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "70997639"
---
### <a name="resizing-a-grid-can-hang"></a>Possibile blocco durante il ridimensionamento di una griglia

|   |   |
|---|---|
|Dettagli|Durante il layout di <code>T:System.Windows.Controls.Grid</code> può verificarsi un ciclo infinito nelle circostanze seguenti:<ul><li>Le definizioni di riga contengono due *-righe che dichiarano entrambe un valore MinHeight e MaxHeight.</li><li>Il contenuto delle *-righe non supera il valore MaxHeight corrispondente</li><li>L'altezza disponibile della griglia viene superata dal primo valore MinHeight (più qualsiasi altra riga automatica o fissa)</li><li>L'app è destinata a .NET Framework 4.7 o acconsente esplicitamente all'algoritmo di allocazione della versione 4.7 impostando <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code></li></ul>Il ciclo si verificherebbe anche con più di due righe o nel caso analogo per le colonne. Il problema è stato corretto in .NET Framework 4.7.1.|
|Suggerimento|Effettuare l'aggiornamento a .NET Framework 4.7.1.  In alternativa, se non è necessario l'algoritmo di allocazione della versione 4.7 è possibile usare l'impostazione di configurazione seguente:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Scope|Microsoft Edge|
|Versione|4.7|
|Type|Runtime|

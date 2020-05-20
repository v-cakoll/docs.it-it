---
ms.openlocfilehash: 1e4c0ac1f0f9011f4b8fc136ec2e383d38567355
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83435464"
---
### <a name="resizing-a-grid-can-hang"></a>Possibile blocco durante il ridimensionamento di una griglia

|   |   |
|---|---|
|Dettagli|Durante il layout di <code>T:System.Windows.Controls.Grid</code> può verificarsi un ciclo infinito nelle circostanze seguenti:<ul><li>Le definizioni di riga contengono due \* righe, che dichiarano entrambe un MinHeight e un MaxHeight.</li><li>Il contenuto di \* -Rows non supera il MaxHeight corrispondente</li><li>L'altezza disponibile della griglia viene superata dal primo valore MinHeight (più qualsiasi altra riga automatica o fissa)</li><li>L'app è destinata a .NET Framework 4.7 o acconsente esplicitamente all'algoritmo di allocazione della versione 4.7 impostando <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code></li></ul>Il ciclo si verificherà anche con più di due righe o nel caso analogo per le colonne. Il problema è stato corretto in .NET Framework 4.7.1.|
|Suggerimento|Effettuare l'aggiornamento a .NET Framework 4.7.1.  In alternativa, se non è necessario l'algoritmo di allocazione della versione 4.7 è possibile usare l'impostazione di configurazione seguente:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ambito|Edge|
|Versione|4.7|
|Tipo|Runtime|

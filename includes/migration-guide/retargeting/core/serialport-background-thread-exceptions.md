---
ms.openlocfilehash: 81b104d8e5a9ccc8e790c3b16e4837cfa0c0def5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236436"
---
### <a name="serialport-background-thread-exceptions"></a>Eccezioni di thread in background SerialPort

|   |   |
|---|---|
|Dettagli|I thread in background creati con flussi <xref:System.IO.Ports.SerialPort> non terminano più il processo quando vengono generate eccezioni del sistema operativo. <br/>Nelle applicazioni destinate a .NET Framework 4.7 e versioni precedenti, un processo viene terminato quando viene generata un'eccezione del sistema operativo in un thread in background creato con un flusso <xref:System.IO.Ports.SerialPort>. <br/>Nelle applicazioni destinate a .NET Framework 4.7.1 o versioni successive, i thread in background attendono gli eventi del sistema operativo relativi alla porta seriale attiva e possono arrestarsi in modo anomalo in alcuni casi, ad esempio in caso di rimozione improvvisa della porta seriale.|
|Suggerimento|Per le app destinate a .NET Framework 4.7.1, è possibile rifiutare esplicitamente la gestione delle eccezioni, nel caso non sia opportuna, aggiungendo il codice seguente alla sezione <code>&lt;runtime&gt;</code> del file <code>app.config</code>:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Per le app destinate alle versioni precedenti di .NET Framework, ma eseguite in .NET Framework 4.7.1 o versioni successive è possibile acconsentire esplicitamente alla gestione delle eccezioni aggiungendo il codice seguente alla sezione <code>&lt;runtime&gt;</code> del file <code>app.config</code>:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ambito|Secondario|
|Versione|4.7.1|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.IO.Ports.SerialPort?displayProperty=nameWithType></li></ul>|

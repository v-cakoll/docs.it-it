---
ms.openlocfilehash: 9c3eedb7f7d4cd030a12c141b8630876c1ffdb4d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236449"
---
### <a name="throttle-concurrent-requests-per-session"></a>Limitazione delle richieste simultanee per sessione

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.6.2 e versioni precedenti, ASP.NET esegue le richieste in sequenza con lo stesso Sessionid e in ASP.NET Sessionid viene sempre generato usando un cookie per impostazione predefinita. Se una pagina richiede molto tempo a rispondere, ridurrà in modo significativo le prestazioni del server semplicemente premendo F5 nel browser. Nella correzione è stato aggiunto un contatore per tenere traccia delle richieste in coda e terminare le richieste quando superano il limite specificato. Il valore predefinito è 50. Se si raggiunge il limite, verrà registrato un avviso nel registro eventi e potrebbe essere registrata una risposta HTTP 500 nel log di IIS.|
|Suggerimento|Per ripristinare il comportamento precedente, è possibile aggiungere l'impostazione seguente al file web. config per rifiutare esplicitamente il nuovo comportamento.<pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;aspnet:RequestQueueLimitPerSession&quot; value=&quot;2147483647&quot;/&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|Ambito|Microsoft Edge|
|Versione|4.7|
|Tipo|Ridestinazione|

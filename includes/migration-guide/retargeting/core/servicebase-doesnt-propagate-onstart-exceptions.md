---
ms.openlocfilehash: 1148d040aa3b292d5c37eb50224413b6ddd202e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859006"
---
### <a name="servicebase-doesnt-propagate-onstart-exceptions"></a>ServiceBase non propaga le eccezioni OnStart

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.7 e versioni precedenti, le eccezioni generate all'avvio di servizi non vengono propagate al chiamante di <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>.<br/>A partire dalle applicazioni destinate a .NET Framework 4.7.1, il runtime propaga le eccezioni a <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> per i servizi il cui avvio non riesce.|
|Suggerimento|All'avvio del servizio, se si verifica un'eccezione, tale eccezione verrà propagata. Questo dovrebbe aiutare a diagnosticare casi in cui l'avvio di un servizio non riesce. <br/>Se questo comportamento non è accettabile, è possibile rifiutarlo esplicitamente aggiungendo l'elemento &lt;AppContextSwitchOverrides&gt; seguente alla sezione &lt;runtime&gt; del file di configurazione dell'applicazione:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceProcess.DontThrowExceptionsOnStart=true&quot; /&gt;&#13;&#10;</code></pre>Se l'applicazione è destinata a una versione precedente la 4.7.1 ma si vuole avere questo comportamento, aggiungere l'elemento &lt;AppContextSwitchOverrides&gt; seguente alla sezione &lt;runtime&gt; del file di configurazione dell'applicazione:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceProcess.DontThrowExceptionsOnStart=false&quot; /&gt;&#13;&#10;</code></pre>|
|Scope|Minorenne|
|Versione|4.7.1|
|Type|Ridestinazione|
|API interessate|<ul><li><xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase)?displayProperty=nameWithType></li><li><xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase[])?displayProperty=nameWithType></li></ul>|

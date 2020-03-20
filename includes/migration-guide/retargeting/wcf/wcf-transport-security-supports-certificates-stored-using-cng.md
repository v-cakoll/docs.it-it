---
ms.openlocfilehash: b57e0acb03a99f33460a7b6c880280b37e01a17b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859345"
---
### <a name="wcf-transport-security-supports-certificates-stored-using-cng"></a>La sicurezza del trasporto WCF supporta i certificati archiviati usando CNG

|   |   |
|---|---|
|Dettagli|A partire dalle applicazioni che hanno come destinazione .NET Framework 4.6.2, la sicurezza del trasporto WCF supporta i certificati archiviati usando la libreria di crittografia di Windows (CNG). Questo supporto è limitato ai certificati con una chiave pubblica che ha un esponente di lunghezza non superiore a 32 bit. Quando un'applicazione è destinata a .NET Framework 4.6.2, questa funzionalità è attivata per impostazione predefinita. Nelle versioni precedenti di .NET Framework il tentativo di usare i certificati X509 con un provider di archiviazione chiavi CSG genera un'eccezione.|
|Suggerimento|Le applicazioni destinate a .NET Framework 4.6.1 e versioni precedenti ma eseguite in .NET Framework 4.6.2 abilitano il supporto per i certificati CNG aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config o web.config:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableCngCertificates=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>L'operazione può essere eseguita anche con il codice seguente:<pre><code class="lang-cs">private const string DisableCngCertificates = @&quot;Switch.System.ServiceModel.DisableCngCertificate&quot;;&#13;&#10;AppContext.SetSwitch(disableCngCertificates, false);&#13;&#10;</code></pre><pre><code class="lang-vb">Const DisableCngCertificates As String = &quot;Switch.System.ServiceModel.DisableCngCertificates&quot;&#13;&#10;AppContext.SetSwitch(disableCngCertificates, False)&#13;&#10;</code></pre>Si noti che, grazie a questa modifica, i codici di gestione delle eccezioni che dipendono dal tentativo di avviare una comunicazione protetta con un certificato CNG di esito negativo non verranno più eseguiti.|
|Scope|Minorenne|
|Versione|4.6.2|
|Type|Ridestinazione|

---
ms.openlocfilehash: e12ba8eb53e6725ebc2e1d87edff3a6a3ce2116b
ms.sourcegitcommit: 5d9f4b805787f890ca6e0dc7ea30a43018bc9cbb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2019
ms.locfileid: "58467479"
---
### <a name="improved-wcf-chain-trust-certificate-validation-for-nettcp-certificate-authentication"></a>Miglioramento della convalida dei certificati attendibili della catena WCF per l'autenticazione del certificato Net.Tcp

|   |   |
|---|---|
|Dettagli|.NET Framework 4.7.2 migliora la convalida dei certificati attendibili della catena quando si usa l'autenticazione del certificato con sicurezza del trasporto con WCF. Con questo miglioramento, i certificati client usati per eseguire l'autenticazione a un server devono essere configurati per l'autenticazione client.  Analogamente, i certificati server per l'autenticazione di un server devono essere configurati per l'autenticazione server. Con questa modifica, se il certificato radice è disabilitato, la convalida della catena di certificati non riesce. La stessa modifica è stata apportata anche a .NET Framework 3.5 e versioni successive tramite rollup della sicurezza di Windows. Altre informazioni sono disponibili [qui](https://support.microsoft.com/en-us/help/4055269/security-only-update-for-net-framework-3-5-1-4-5-2-4-6-4-6-1-4-6-2-4-7). Questa modifica è attivata per impostazione predefinita e può essere disattivata tramite un'impostazione di configurazione.|
|Suggerimento|<ul><li>Verificare se la certificazione per client e server è dotata dell'OID EKU necessario. In caso contrario, aggiornare la certificazione.</li><li>Verificare se il certificato radice è valido. In caso contrario, aggiornare il certificato radice.</li><li>Come rifiutare esplicitamente la modifica: se non è possibile aggiornare il certificato, una soluzione alternativa temporanea per questa modifica che causa un'interruzione è costituita dall'impostazione di configurazione seguente. Con il rifiuto esplicito della modifica, tuttavia, il sistema sarà vulnerabile al problema di sicurezza.</li></ul><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;wcf:useLegacyCertificateUsagePolicy&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|Ambito|Secondario|
|Versione|4.7.2|
|Tipo|Runtime|


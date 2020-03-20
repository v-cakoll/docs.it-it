---
ms.openlocfilehash: ee9bba91a2c4e11bd005fedb8adf0c2e7c7b0d3e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804426"
---
### <a name="certificate-eku-oid-validation"></a>Convalida dell'OID EKU del certificato

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.6, le classi <xref:System.Net.Security.SslStream> o <xref:System.Net.ServicePointManager> eseguono la convalida dell'oggetto identificatore (OID) dell'utilizzo chiavi avanzato (EKU). Un'estensione di utilizzo chiavi avanzato (EKU) è una raccolta di identificatori di oggetto (OID) che indica le applicazioni che usano la chiave. La convalida dell'OID EKU usa callback del certificato remoto per assicurarsi che il certificato remoto abbia gli OID corretti per lo scopo previsto.|
|Suggerimento|Se questa modifica non è auspicabile, è possibile disabilitare la [`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) convalida oID EKU del certificato aggiungendo l'opzione seguente all'>[ \<AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) nel file di configurazione dell'app:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Net.DontCheckCertificateEKUs=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre> <blockquote> [!IMPORTANT] Questa impostazione è disponibile solo per la compatibilità con le versioni precedenti. Il suo uso non è altrimenti consigliato.</blockquote> |
|Scope|Minorenne|
|Versione|4.6|
|Type|Ridestinazione|
|API interessate|<ul><li><xref:System.Net.Security.SslStream?displayProperty=nameWithType></li><li><xref:System.Net.ServicePointManager?displayProperty=nameWithType></li><li><xref:System.Net.Http.HttpClient?displayProperty=nameWithType></li><li><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType></li><li><xref:System.Net.HttpWebRequest?displayProperty=nameWithType></li><li><xref:System.Net.FtpWebRequest?displayProperty=nameWithType></li></ul>|

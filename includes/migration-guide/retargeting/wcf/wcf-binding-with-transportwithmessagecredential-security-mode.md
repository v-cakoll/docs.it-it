---
ms.openlocfilehash: 2359dafb9042c13ae75e644d4ea655f53c14e95e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234424"
---
### <a name="wcf-binding-with-the-transportwithmessagecredential-security-mode"></a>Associazione WCF con la modalità di sicurezza TransportWithMessageCredential

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.6.1 l'associazione WCF che usa la modalità di sicurezza TransportWithMessageCredential può essere impostata in modo da ricevere i messaggi con intestazioni &quot;a&quot; non firmate per le chiavi di sicurezza asimmetriche. Per impostazione predefinita, le intestazioni &quot;a&quot; non firmate continueranno a essere rifiutate in .NET Framework 4.6.1. Verranno accettate solo se un'applicazione accetta in modo esplicito questa nuova modalità di funzionamento usando l'opzione di configurazione Switch.System.ServiceModel.AllowUnsignedToHeader.|
|Suggerimento|Poiché è una funzionalità che prevede il consenso esplicito, non dovrebbe influire sul comportamento delle app esistenti.<br/>Per stabilire se il nuovo comportamento deve essere usato o meno, usare l'impostazione di configurazione seguente:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.AllowUnsignedToHeader=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ambito|Trasparente|
|Versione|4.6.1|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.BasicHttpsSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li></ul>|

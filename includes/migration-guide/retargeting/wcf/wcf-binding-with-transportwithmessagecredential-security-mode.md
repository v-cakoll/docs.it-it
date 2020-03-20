---
ms.openlocfilehash: 2359dafb9042c13ae75e644d4ea655f53c14e95e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804372"
---
### <a name="wcf-binding-with-the-transportwithmessagecredential-security-mode"></a>Associazione WCF con la modalità di sicurezza TransportWithMessageCredential

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.6.1 l'associazione WCF che usa la modalità di sicurezza TransportWithMessageCredential può essere impostata in modo da ricevere i messaggi con intestazioni &quot;a&quot; non firmate per le chiavi di sicurezza asimmetriche. Per impostazione predefinita, le intestazioni &quot;a&quot; non firmate continueranno a essere rifiutate in .NET Framework 4.6.1. Verranno accettate solo se un'applicazione accetta in modo esplicito questa nuova modalità di funzionamento usando l'opzione di configurazione Switch.System.ServiceModel.AllowUnsignedToHeader.|
|Suggerimento|Poiché è una funzionalità che prevede il consenso esplicito, non dovrebbe influire sul comportamento delle app esistenti.<br/>Per stabilire se il nuovo comportamento deve essere usato o meno, usare l'impostazione di configurazione seguente:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.AllowUnsignedToHeader=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Scope|Trasparente|
|Versione|4.6.1|
|Type|Ridestinazione|
|API interessate|<ul><li><xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.BasicHttpsSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li></ul>|

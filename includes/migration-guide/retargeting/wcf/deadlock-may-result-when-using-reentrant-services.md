---
ms.openlocfilehash: 2f960942bda54505690cbac3151ef74ec0ab5ebb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "68235572"
---
### <a name="deadlock-may-result-when-using-reentrant-services"></a>Possibile deadlock quando si usano servizi rientranti

|   |   |
|---|---|
|Dettagli|Può verificarsi un deadlock in un servizio rientrante, che limita le istanze del servizio a un solo thread di esecuzione alla volta. Sono soggetti a questo problema i servizi che includono l'attributo <xref:System.ServiceModel.ServiceBehaviorAttribute> seguente nel codice:<pre><code class="lang-csharp">[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]&#13;&#10;</code></pre>|
|Suggerimento|Per risolvere questo problema, è possibile eseguire le operazioni seguenti:<ul><li>Impostare la modalità di concorrenza del servizio su <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> oppure &lt;System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType&gt;. Ad esempio:</li></ul><pre><code class="lang-csharp">[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single)]&#13;&#10;</code></pre><ul><li>Installare l'aggiornamento più recente di .NET Framework 4.6.2 oppure eseguire l'aggiornamento a una versione successiva di .NET Framework. Viene così disabilitato il flusso di <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>. Questo comportamento è configurabile ed è equivalente all'aggiunta dell'impostazione dell'app seguente nel file di configurazione:</li></ul><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.ServiceModel.DisableOperationContextAsyncFlow&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>Il valore di <code>Switch.System.ServiceModel.DisableOperationContextAsyncFlow</code> non deve mai essere impostato su <code>false</code> per i servizi Rentrant.|
|Scope|Minorenne|
|Versione|4.6.2|
|Type|Ridestinazione|
|API interessate|<ul><li><xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType></li></ul>|

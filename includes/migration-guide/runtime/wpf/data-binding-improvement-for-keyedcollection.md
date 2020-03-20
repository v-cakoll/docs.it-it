---
ms.openlocfilehash: 8aae403e3f23d3bfc755140b2ac29d757f10f753
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74451565"
---
### <a name="data-binding-improvement-for-keyedcollection"></a>Miglioramento del data binding per KeyedCollection

|   |   |
|---|---|
|Dettagli|Correzione <xref:System.Windows.Data.Binding> dell'utilizzo non corretto dell'indicizzatore IList quando l'oggetto di origine&lt;dichiara un indicizzatore personalizzato con la stessa firma , ad esempio KeyedCollection int,TItem&gt;.|
|Suggerimento|Affinché un'applicazione destinata a una versione precedente tragga vantaggio da questa modifica, deve essere eseguita in .NET Framework 4.8 <code>&lt;runtime&gt;</code> o versione successiva e deve <code>false</code>acconsentire esplicitamente alla modifica aggiungendo l'opzione [AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) seguente alla sezione del file di configurazione dell'app e impostandola su :<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.Binding.IListIndexerHidesCustomIndexer=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Scope|Principale|
|Versione|4.8|
|Type|Runtime|

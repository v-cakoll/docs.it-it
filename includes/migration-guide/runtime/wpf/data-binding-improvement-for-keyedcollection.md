---
ms.openlocfilehash: a0dc2401155a162eaa5aa6b4d9e6af1ca1c2ccc8
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802698"
---
### <a name="data-binding-improvement-for-keyedcollection"></a>Miglioramento del data binding per KeyedCollection

|   |   |
|---|---|
|Dettagli|Risolto l'uso non corretto dell'indicizzatore IList da parte di <xref:System.Windows.Data.Binding> quando l'oggetto di origine dichiara un indicizzatore personalizzato con la stessa firma (ad esempio, KeyedCollection&lt;int,TItem&gt;).|
|Suggerimento|Perché l'applicazione possa usufruire di questa modifica, è necessario che sia eseguita in .NET Framework 4.7.2 o versione successiva e che acconsenta esplicitamente alla modifica aggiungendo l'[opzione di AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) seguente alla sezione <code>&lt;runtime&gt;</code> del file di configurazione dell'app e impostandola su <code>false</code>:<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.Binding.IListIndexerHidesCustomIndexer=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ambito|Principale|
|Versione|4.8|
|Tipo|Runtime|


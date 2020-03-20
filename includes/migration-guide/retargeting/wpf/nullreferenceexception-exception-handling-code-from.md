---
ms.openlocfilehash: 824d75585efd40937c1a48376ec7862cba1a8fa3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "68235519"
---
### <a name="nullreferenceexception-in-exception-handling-code-from-imagesourceconverterconvertfrom"></a>NullReferenceException nel codice di gestione delle eccezioni da ImageSourceConverter.ConvertFrom

|   |   |
|---|---|
|Dettagli|Un errore nel codice di gestione delle eccezioni per <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> ha causato la generazione di un oggetto <xref:System.NullReferenceException?displayProperty=name> non corretto anziché dell'eccezione prevista (<xref:System.IO.DirectoryNotFoundException?displayProperty=name> o <xref:System.IO.FileNotFoundException?displayProperty=name>). Questa modifica corregge tale errore e quindi il metodo ora genera l'eccezione appropriata. <p/>Per impostazione predefinita, tutte le applicazioni destinate a .NET Framework 4.6.2 e versioni precedenti continuano a generare <xref:System.NullReferenceException?displayProperty=name> per la compatibilità. Gli sviluppatori di applicazioni destinate a.NET Framework 4.7 e versioni precedenti visualizzano le eccezioni corrette.|
|Suggerimento|Gli sviluppatori che preferiscono tornare al recupero di <xref:System.NullReferenceException?displayProperty=name> quando usano .NET Framework 4.7 o versione successiva come destinazione possono aggiungere o unire il codice seguente al file App.config della propria applicazione:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Scope|Microsoft Edge|
|Versione|4.7|
|Type|Ridestinazione|
|API interessate|<ul><li><xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)?displayProperty=nameWithType></li></ul>|

---
ms.openlocfilehash: 9c9c4ec55143ef991e9b69a389e0f3368263bb4e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614845"
---
### <a name="nullreferenceexception-in-exception-handling-code-from-imagesourceconverterconvertfrom"></a>NullReferenceException nel codice di gestione delle eccezioni da ImageSourceConverter.ConvertFrom

#### <a name="details"></a>Dettagli

Un errore nel codice di gestione delle eccezioni per <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> ha causato la generazione di un oggetto <xref:System.NullReferenceException?displayProperty=fullName> non corretto anziché dell'eccezione prevista (<xref:System.IO.DirectoryNotFoundException?displayProperty=fullName> o <xref:System.IO.FileNotFoundException?displayProperty=fullName>). Questa modifica corregge tale errore e quindi il metodo ora genera l'eccezione appropriata. <p/>Per impostazione predefinita, tutte le applicazioni destinate a .NET Framework 4.6.2 e versioni precedenti continuano a generare <xref:System.NullReferenceException?displayProperty=fullName> per la compatibilità. Gli sviluppatori di applicazioni destinate a.NET Framework 4.7 e versioni precedenti visualizzano le eccezioni corrette.

#### <a name="suggestion"></a>Suggerimento

Gli sviluppatori che preferiscono tornare al recupero di <xref:System.NullReferenceException?displayProperty=fullName> quando usano .NET Framework 4.7 o versione successiva come destinazione possono aggiungere o unire il codice seguente al file App.config della propria applicazione:

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.7         |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)?displayProperty=nameWithType>

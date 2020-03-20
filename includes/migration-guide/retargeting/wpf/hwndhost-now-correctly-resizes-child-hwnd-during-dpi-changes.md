---
ms.openlocfilehash: b92086c8ccf7592ce70b75bd31d4ea255c35b543
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803511"
---
### <a name="hwndhost-now-correctly-resizes-child-hwnd-during-dpi-changes"></a>HwndHost ora ridimensiona correttamente l'elemento HWND figlio durante le modifiche DPI

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.7.2 e versioni precedenti, quando WPF viene eseguito in modalità sensibile ai valori DPI del monitor, i controlli ospitati all'interno di <xref:System.Windows.Interop.HwndHost> non vengono ridimensionati correttamente dopo le modifiche DPI, ad esempio quando si passano le applicazioni da un monitor a un altro. Questa correzione garantisce il corretto ridimensionamento dei controlli ospitati.|
|Suggerimento|Perché l'applicazione possa usufruire di queste modifiche, è necessario che sia eseguita in .NET Framework 4.7.2 o versione successiva e che acconsenta esplicitamente a questo comportamento impostando l'[opzione di AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) seguente nella sezione <code>&lt;runtime&gt;</code> del file di configurazione dell'app su <code>false</code>, come illustrato nell'esempio riportato di seguito.<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.DoNotUsePresentationDpiCapabilityTier2OrGreater=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Scope|Principale|
|Versione|4.8|
|Type|Ridestinazione|

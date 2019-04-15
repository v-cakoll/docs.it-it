---
ms.openlocfilehash: 4eac93d5cfea19cb83c66cd3fe35c1b0703c0cc0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234038"
---
### <a name="wpf-focusvisual-for-radiobutton-and-checkbox-now-displays-correctly-when-the-controls-have-no-content"></a>Gli oggetti visivi WPF per RadioButton e CheckBox vengono ora visualizzati correttamente quando i controlli non hanno contenuto

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.7.1 e versioni precedenti le classi <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> e <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> di WPF contengono oggetti visivi dello stato attivo incoerenti e non corretti nei temi classico e a contrasto elevato.  Questi problemi si verificano se i controlli non hanno impostato un contenuto.  La transizione tra i temi può risultare quindi confusa e diventa difficile visualizzare l'oggetto visivo con stato attivo. In .NET Framework 4.7.2 questi oggetti visivi sono più coerenti tra i temi e possono essere visualizzati più facilmente nei temi classico e a contrasto elevato.|
|Suggerimento|Gli sviluppatori che usano .NET Framework 4.7.2 e vogliono ripristinare il comportamento di .NET 4.7.1 devono impostare il flag AppContext seguente.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures.2=true;&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Gli sviluppatori che vogliono usare questa modifica e usare al tempo stesso una versione di framework precedente alla versione .NET 4.7.2 devono impostare i flag AppContext seguenti. Si noti che tutti i flag devono essere impostati correttamente ed è necessario installare la versione .NET Framework 4.7.2 o versione successiva. Le applicazioni WPF devono acconsentire esplicitamente a tutti i miglioramenti precedenti in termini di accessibilità per ottenere gli ultimi miglioramenti. A tale scopo, assicurarsi che le due opzioni di AppContext "Switch.UseLegacyAccessibilityFeatures" e "Switch.UseLegacyAccessibilityFeatures.2" siano impostate su False.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ambito|Microsoft Edge|
|Versione|4.7.2|
|Tipo|Ridestinazione|

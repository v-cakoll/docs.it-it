---
ms.openlocfilehash: 9e70bcd95393a7ff24de43577d26869ce674067b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614966"
---
### <a name="wpf-focusvisual-for-radiobutton-and-checkbox-now-displays-correctly-when-the-controls-have-no-content"></a>Gli oggetti visivi WPF per RadioButton e CheckBox vengono ora visualizzati correttamente quando i controlli non hanno contenuto

#### <a name="details"></a>Dettagli

In .NET Framework 4.7.1 e versioni precedenti le classi <xref:System.Windows.Controls.CheckBox?displayProperty=nameWithType> e <xref:System.Windows.Controls.RadioButton?displayProperty=nameWithType> di WPF contengono oggetti visivi dello stato attivo incoerenti e non corretti nei temi classico e a contrasto elevato.  Questi problemi si verificano se i controlli non hanno impostato un contenuto.  La transizione tra i temi può risultare quindi confusa e diventa difficile visualizzare l'oggetto visivo con stato attivo. In .NET Framework 4.7.2 questi oggetti visivi sono più coerenti tra i temi e possono essere visualizzati più facilmente nei temi classico e a contrasto elevato.

#### <a name="suggestion"></a>Suggerimento

Gli sviluppatori che usano .NET Framework 4.7.2 e vogliono ripristinare il comportamento di .NET 4.7.1 devono impostare il flag AppContext seguente.

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures.2=true;&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

Gli sviluppatori che vogliono usare questa modifica e usare al tempo stesso una versione di framework precedente alla versione .NET 4.7.2 devono impostare i flag AppContext seguenti. Si noti che tutti i flag devono essere impostati correttamente ed è necessario installare la versione .NET Framework 4.7.2 o versione successiva. Le applicazioni WPF devono acconsentire esplicitamente a tutti i miglioramenti precedenti in termini di accessibilità per ottenere gli ultimi miglioramenti. A tale scopo, assicurarsi che le due opzioni di AppContext "Switch.UseLegacyAccessibilityFeatures" e "Switch.UseLegacyAccessibilityFeatures.2" siano impostate su False.

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.7.2       |
| Type    | Ridestinazione |

---
ms.openlocfilehash: 7c2e80669d9ef27f87cde9442d8eeab0ee31a524
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614980"
---
### <a name="wpf-textboxpasswordbox-text-selection-does-not-follow-system-colors"></a>La selezione di testo di TextBox/PasswordBox WPF non rispetta i colori di sistema

#### <a name="details"></a>Dettagli

In .NET Framework 4.7.1 e versioni precedenti i controlli `System.Windows.Controls.TextBox` e `System.Windows.Controls.PasswordBox` WPF eseguono solo il rendering di una selezione di testo a livello di Adorner. In alcuni temi di sistema il testo appare poco chiaro e di difficile lettura.  In .NET Framework 4.7.2 e versioni successive gli sviluppatori possono abilitare uno schema di rendering di una selezione che non si basa su Adorner in modo da limitare questo problema.

#### <a name="suggestion"></a>Suggerimento

Gli sviluppatori che vogliono usare questa modifica devono impostare il flag AppContext seguente in modo appropriato.  Per usare questa funzionalità, è necessario installare la versione .NET Framework 4.7.2 o versione successiva. Per abilitare la selezione non basata su Adorner, usare il flag AppContext seguente.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Text.UseAdornerForTextboxSelectionRendering=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.7.2       |
| Type    | Ridestinazione |

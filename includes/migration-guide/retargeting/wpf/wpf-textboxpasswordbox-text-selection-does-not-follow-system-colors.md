---
ms.openlocfilehash: 649e4456ef6a11903ab1b390baf56583f31f5562
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760917"
---
### <a name="wpf-textboxpasswordbox-text-selection-does-not-follow-system-colors"></a>La selezione di testo di TextBox/PasswordBox WPF non rispetta i colori di sistema

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.7.1 e versioni precedenti i controlli <code>System.Windows.Controls.TextBox</code> e <code>System.Windows.Controls.PasswordBox</code> WPF eseguono solo il rendering di una selezione di testo a livello di Adorner. In alcuni temi di sistema il testo appare poco chiaro e di difficile lettura.  In .NET Framework 4.7.2 e versioni successive gli sviluppatori possono abilitare uno schema di rendering di una selezione che non si basa su Adorner in modo da limitare questo problema.|
|Suggerimento|Gli sviluppatori che vogliono usare questa modifica devono impostare il flag AppContext seguente in modo appropriato.  Per usare questa funzionalità, è necessario installare la versione .NET Framework 4.7.2 o versione successiva. Per abilitare la selezione non basata su Adorner, usare il flag AppContext seguente.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Text.UseAdornerForTextboxSelectionRendering=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ambito|Microsoft Edge|
|Versione|4.7.2|
|Tipo|Ridestinazione|


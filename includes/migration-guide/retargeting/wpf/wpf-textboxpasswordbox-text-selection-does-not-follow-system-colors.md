---
ms.openlocfilehash: 3f88c8b80518aa65c082dc3da2d75b5221dd00f0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774101"
---
### <a name="wpf-textboxpasswordbox-text-selection-does-not-follow-system-colors"></a>La selezione di testo di TextBox/PasswordBox WPF non rispetta i colori di sistema

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.7.1 e versioni precedenti i controlli <code>System.Windows.Controls.TextBox</code> e <code>System.Windows.Controls.PasswordBox</code> WPF eseguono solo il rendering di una selezione di testo a livello di Adorner. In alcuni temi di sistema il testo appare poco chiaro e di difficile lettura.  In .NET Framework 4.7.2 e versioni successive gli sviluppatori possono abilitare uno schema di rendering di una selezione che non si basa su Adorner in modo da limitare questo problema.|
|Suggerimento|Gli sviluppatori che vogliono usare questa modifica devono impostare il flag AppContext seguente in modo appropriato.  Per usare questa funzionalità, è necessario installare la versione .NET Framework 4.7.2 o versione successiva. Per abilitare la selezione non basata su Adorner, usare il flag AppContext seguente.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Text.UseAdornerForTextboxSelectionRendering=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ambito|Microsoft Edge|
|Versione|4.7.2|
|Tipo|Ridestinazione|

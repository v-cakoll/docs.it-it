---
ms.openlocfilehash: 3bde64b80e5dcfe98bbf598700b6d7004e3c3c9d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234052"
---
### <a name="keyboard-focus-now-moves-correctly-across-multiple-layers-of-winformswpf-hosting"></a>Stato attivo della tastiera ora consente di spostarsi correttamente su più livelli di hosting di Windows Form/WPF

|   |   |
|---|---|
|Dettagli|Si consideri un'applicazione WPF che ospita un controllo Windows Form che a sua volta ospita i controlli WPF. Può accadere che gli utenti non possano uscire dal livello di Windows Form tramite tabulazione se il primo o l'ultimo controllo in tale livello è <code>System.Windows.Forms.Integration.ElementHost</code> di WPF. Questa modifica consente di correggere tale problema. Gli utenti ora possono uscire dal livello di Windows Form tramite tabulazione. Le applicazioni automatiche che si basano su uno stato attivo che non esce mai dal livello di Windows Form potrebbero non funzionare come previsto.|
|Suggerimento|Uno sviluppatore che vuole usare questa modifica per una versione del framework precedente a .NET 4.7.2 può impostare i flag AppContext seguenti su False per disabilitare la modifica.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Le applicazioni WPF devono accettare tutti i miglioramenti di accessibilità precedenti per ottenere i miglioramenti successivi. In altre parole, è necessario impostare entrambe le due opzioni <code>Switch.UseLegacyAccessibilityFeatures</code> e <code>Switch.UseLegacyAccessibilityFeatures.2</code>. Uno sviluppatore che richiede la funzionalità precedente per .NET 4.7.2 o versione successiva può impostare il flag AppContext seguente su True per disabilitare la modifica.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures.2=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ambito|Microsoft Edge|
|Versione|4.7.2|
|Tipo|Ridestinazione|

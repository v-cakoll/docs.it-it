---
ms.openlocfilehash: a82b720fd4e771481ea1142a88a095443afa0d5b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614943"
---
### <a name="keyboard-focus-now-moves-correctly-across-multiple-layers-of-winformswpf-hosting"></a>Stato attivo della tastiera ora consente di spostarsi correttamente su più livelli di hosting di Windows Form/WPF

#### <a name="details"></a>Dettagli

Si consideri un'applicazione WPF che ospita un controllo Windows Form che a sua volta ospita i controlli WPF. Può accadere che gli utenti non possano uscire dal livello di Windows Form tramite tabulazione se il primo o l'ultimo controllo in tale livello è `System.Windows.Forms.Integration.ElementHost` di WPF. Questa modifica consente di correggere tale problema. Gli utenti ora possono uscire dal livello di Windows Form tramite tabulazione. Le applicazioni automatiche che si basano su uno stato attivo che non esce mai dal livello di Windows Form potrebbero non funzionare come previsto.

#### <a name="suggestion"></a>Suggerimento

Uno sviluppatore che vuole usare questa modifica per una versione del framework precedente a .NET 4.7.2 può impostare i flag AppContext seguenti su False per disabilitare la modifica.

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

Le applicazioni WPF devono accettare tutti i miglioramenti di accessibilità precedenti per ottenere i miglioramenti successivi. In altre parole, è necessario impostare entrambe le due opzioni `Switch.UseLegacyAccessibilityFeatures` e `Switch.UseLegacyAccessibilityFeatures.2`. Uno sviluppatore che richiede la funzionalità precedente per .NET 4.7.2 o versione successiva può impostare il flag AppContext seguente su True per disabilitare la modifica.

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures.2=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.7.2       |
| Type    | Ridestinazione |

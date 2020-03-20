---
ms.openlocfilehash: 0b087fca59d60a086a9ea8b2bb19c09f646c3dfd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859046"
---
### <a name="improved-accessibility-for-some-net-sdk-tools"></a>Accessibilità migliorata per alcuni strumenti di .NET SDK

|   |   |
|---|---|
|Dettagli|In .NET Framework SDK 4.7.1 gli strumenti SvcConfigEditor.exe e SvcTraceViewer.exe sono stati migliorati risolvendo vari problemi relativi all'accessibilità. Molti erano problemi di lieve entità, come ad esempio un nome non definito o alcuni pattern dell'automazione interfaccia utente non implementati correttamente. È possibile che molti utenti non si siano accorti di questi valori non corretti. I clienti che usano tipi di assistive technology, ad esempio le utilità per la lettura dello schermo, troveranno invece questi strumenti SDK più accessibili. Queste correzioni modificano sicuramente alcuni comportamenti precedenti, ad esempio l'ordine dello stato attivo della tastiera. Per ottenere tutte le correzioni relative all'accessibilità in questi strumenti, è possibile applicare quanto segue al file app.config:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Scope|Microsoft Edge|
|Versione|4.7.1|
|Type|Ridestinazione|

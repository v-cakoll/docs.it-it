---
ms.openlocfilehash: cc6d96bd614ff015ae2125c0f1477e18a91a68f7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802613"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a>Modifica del contrasto elevato di ComboBox in svcTraceViewer

|   |   |
|---|---|
|Dettagli|Nello [strumento Visualizzatore di tracce dei servizi Microsoft](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) i controlli ComboBox non venivano visualizzati nel colore corretto in alcuni temi a contrasto elevato. Il problema è stato risolto in .NET Framework 4.7.2. Tuttavia, a causa dei requisiti di compatibilità con le versioni precedenti di .NET Framework SDK, la correzione non risultava visibile ai clienti per impostazione predefinita. .NET 4.8 espone questa modifica aggiungendo le [opzioni di configurazione di AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguenti al file svcTraceViewer.exe.config:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>|
|Suggerimento|<ul><li>Come rifiutare esplicitamente la modifica: se non si vuole avere la modifica funzionale relativa al contrasto elevato, è possibile disabilitarla rimuovendo la sezione seguente dal file svcTraceViewer.exe.config:</li></ul><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>|
|Scope|Microsoft Edge|
|Versione|4.8|
|Type|Runtime|

---
ms.openlocfilehash: 5a45d616001be5a2a2bdf2c654c10526125d7d86
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802613"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a>Modifica del contrasto elevato di ComboBox in svcTraceViewer

|   |   |
|---|---|
|Dettagli|Nello [strumento Visualizzatore di tracce dei servizi Microsoft](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) i controlli ComboBox non venivano visualizzati nel colore corretto in alcuni temi a contrasto elevato. Il problema è stato risolto in .NET Framework 4.7.2. Tuttavia, a causa dei requisiti di compatibilità con le versioni precedenti di .NET Framework SDK, la correzione non risultava visibile ai clienti per impostazione predefinita. .NET 4.8 espone questa modifica aggiungendo le [opzioni di configurazione di AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguenti al file svcTraceViewer.exe.config:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>|
|Suggerimento|<ul><li>Come rifiutare esplicitamente la modifica: se non si vuole avere la modifica funzionale relativa al contrasto elevato, è possibile disabilitarla rimuovendo la sezione seguente dal file svcTraceViewer.exe.config:</li></ul><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>|
|Ambito|Microsoft Edge|
|Versione|4.8|
|Tipo|Runtime|


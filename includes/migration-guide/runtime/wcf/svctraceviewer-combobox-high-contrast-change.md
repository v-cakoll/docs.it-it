---
ms.openlocfilehash: 06f4186e8f233f5c769dfc5e05d2de5eacd9b053
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621991"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a>Modifica del contrasto elevato di ComboBox in svcTraceViewer

#### <a name="details"></a>Dettagli

Nello [strumento Visualizzatore di tracce dei servizi Microsoft](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) i controlli ComboBox non venivano visualizzati nel colore corretto in alcuni temi a contrasto elevato. Il problema è stato risolto in .NET Framework 4.7.2. Tuttavia, a causa dei requisiti di compatibilità con le versioni precedenti di .NET Framework SDK, la correzione non risultava visibile ai clienti per impostazione predefinita. .NET 4.8 espone questa modifica aggiungendo le [opzioni di configurazione di AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguenti al file svcTraceViewer.exe.config:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>

#### <a name="suggestion"></a>Suggerimento

<ul><li>Come rifiutare esplicitamente la modifica: se non si vuole avere la modifica funzionale relativa al contrasto elevato, è possibile disabilitarla rimuovendo la sezione seguente dal file svcTraceViewer.exe.config:</li></ul><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.8|
|Type|Runtime|

---
ms.openlocfilehash: 60759e3d03137bb5983703cbf04719ba4946cb6e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804280"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a>Gli adattatori flusso di WinRT non chiamano più automaticamente FlushAsync alla chiusura

|   |   |
|---|---|
|Dettagli|Nelle app di Windows Store, gli adattatori flusso di Windows Runtime non chiamano più il metodo FlushAsync dal metodo Dispose.|
|Suggerimento|Questa modifica dovrebbe essere trasparente. Gli sviluppatori potranno ripristinare il comportamento precedente scrivendo del codice simile al seguente:<pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>|
|Ambito|Trasparente|
|Versione|4.5.1|
|Tipo|Runtime|

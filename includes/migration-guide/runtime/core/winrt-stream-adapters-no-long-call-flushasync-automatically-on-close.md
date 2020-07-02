---
ms.openlocfilehash: 60937459b6f18e9abae87ad2dc97c3942325eedc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620274"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a>Gli adattatori flusso di WinRT non chiamano più automaticamente FlushAsync alla chiusura

#### <a name="details"></a>Dettagli

Nelle app di Windows Store, gli adattatori flusso di Windows Runtime non chiamano più il metodo FlushAsync dal metodo Dispose.

#### <a name="suggestion"></a>Suggerimento

Questa modifica dovrebbe essere trasparente. Gli sviluppatori potranno ripristinare il comportamento precedente scrivendo del codice simile al seguente:<pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Modalità trasparente|
|Version|4.5.1|
|Type|Runtime|

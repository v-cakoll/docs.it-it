---
ms.openlocfilehash: 8db115a46df3fcea103e8fa6896542d0116aa256
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804652"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a>VB.NET non supporta più la qualificazione parziale dello spazio dei nomi per le API System.Windows

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.5.2, i progetti VB.NET non possono specificare API System.Windows con spazi dei nomi parzialmente qualificati. Ad esempio, un riferimento a <code>Windows.Forms.DialogResult</code> avrà esito negativo. Il codice deve invece fare riferimento al nome completo (<xref:System.Windows.Forms.DialogResult>) o importare lo spazio dei nomi specifico e fare semplicemente riferimento a <xref:System.Windows.Forms.DialogResult?displayProperty=name>.|
|Suggerimento|È consigliabile aggiornare il codice in modo che faccia riferimento alle API <code>System.Windows</code> tramite nomi semplici (e importare lo spazio dei nomi rilevante) o con nomi completi.|
|Scope|Minorenne|
|Versione|4.5.2|
|Type|Ridestinazione|

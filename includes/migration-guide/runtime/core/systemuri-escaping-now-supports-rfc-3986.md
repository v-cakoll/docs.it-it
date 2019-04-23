---
ms.openlocfilehash: 1654d58651bf14b0e7c21de2afa827634b7db858
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235664"
---
### <a name="systemuri-escaping-now-supports-rfc-3986"></a>La funzionalità di escape System.Uri ora supporta RFC 3986

|   |   |
|---|---|
|Dettagli|La funzionalità di escape URI è stata modificata in .NET Framework 4.5 per supportare la specifica [RFC 3986](https://tools.ietf.org/html/rfc3986). Le modifiche specifiche includono:<ul><li><xref:System.Uri.EscapeDataString(System.String)?displayProperty=name> Con il metodo EscapeDataString(String) viene effettuato l'escape dei caratteri riservati basati su RFC 3986.</li><li><xref:System.Uri.EscapeUriString(System.String)?displayProperty=name> Con il metodo EscapeUriString(String) non viene effettuato l'escape dei caratteri riservati.</li><li><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=name> non genera un'eccezione se rileva una sequenza di escape non valida.</li><li>I caratteri di escape non riservati non sono sottoposti a escape.</li></ul>|
|Suggerimento|<ul><li>Aggiornare le applicazioni in modo che non si basino sul fatto che <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=name> generi un'eccezione in presenza di una sequenza di escape non valida. Queste sequenze devono ora essere rilevate direttamente.</li><li>Allo stesso modo, prevedere che gli URI e le stringhe di dati con e senza codice di escape possano variare da .NET Framework 4.0 a .NET Framework 4.5 ed evitare confronti diretti tra versioni diverse di .NET. Questi elementi devono essere invece analizzati e normalizzati in una singola versione di .NET prima di eseguire eventuali confronti.</li></ul>|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Uri.EscapeDataString(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.EscapeUriString(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=nameWithType></li></ul>|

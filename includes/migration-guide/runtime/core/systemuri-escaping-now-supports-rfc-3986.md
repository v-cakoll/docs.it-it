---
ms.openlocfilehash: 1d7dc808d5b514acc582675d6ccdbd5778314624
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620264"
---
### <a name="systemuri-escaping-now-supports-rfc-3986"></a>La funzionalità di escape System.Uri ora supporta RFC 3986

#### <a name="details"></a>Dettagli

La funzionalità di escape URI è stata modificata in .NET Framework 4.5 per supportare la specifica [RFC 3986](https://tools.ietf.org/html/rfc3986). Le modifiche specifiche includono:<ul><li>Tramite il metodo <xref:System.Uri.EscapeDataString(System.String)?displayProperty=fullName> viene effettuato l'escape dei caratteri riservati basati su RFC 3986.</li><li>Tramite il metodo <xref:System.Uri.EscapeUriString(System.String)?displayProperty=fullName> non viene effettuato l'escape dei caratteri riservati.</li><li><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> non genera un'eccezione se rileva una sequenza di escape non valida.</li><li>I caratteri di escape non riservati non sono sottoposti a escape.</li></ul>

#### <a name="suggestion"></a>Suggerimento

<ul><li>Aggiornare le applicazioni in modo che non si basino sul fatto che <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> generi un'eccezione in presenza di una sequenza di escape non valida. Queste sequenze devono ora essere rilevate direttamente.</li><li>Allo stesso modo, prevedere che gli URI e le stringhe di dati con e senza codice di escape possano variare da .NET Framework 4.0 a .NET Framework 4.5 ed evitare confronti diretti tra versioni diverse di .NET. Questi elementi devono essere invece analizzati e normalizzati in una singola versione di .NET prima di eseguire eventuali confronti.</li></ul>

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Uri.EscapeDataString(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.EscapeUriString(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=nameWithType></li></ul>|

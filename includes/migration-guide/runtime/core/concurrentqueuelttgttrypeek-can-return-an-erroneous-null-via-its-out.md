---
ms.openlocfilehash: a93fbbd787aa50f080337a6170cf8f56d0d24e31
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804233"
---
### <a name="concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>ConcurrentQueue\<T>.TryPeek può restituire erroneamente un valore Null tramite il parametro di output

|   |   |
|---|---|
|Dettagli|In alcuni scenari multithread, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> può restituire true, ma popolare il parametro di output con un valore null, anziché il valore corretto, restituito.|
|Suggerimento|Questo problema è risolto in .NET Framework 4.5.1. L'aggiornamento a questa versione di .NET Framework consentirà di risolvere il problema.|
|Ambito|Principale|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|

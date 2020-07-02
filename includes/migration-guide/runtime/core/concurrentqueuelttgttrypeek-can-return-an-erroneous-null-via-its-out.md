---
ms.openlocfilehash: 02a15f6b9c02002b60c568b9e1d871af49744092
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622049"
---
### <a name="concurrentqueuelttgttrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>ConcurrentQueue&lt;T&gt;.TryPeek può restituire erroneamente un valore Null tramite il parametro di output

#### <a name="details"></a>Dettagli

In alcuni scenari multithread, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> può restituire true, ma popolare il parametro di output con un valore null, anziché il valore corretto, restituito.

#### <a name="suggestion"></a>Suggerimento

Questo problema è risolto in .NET Framework 4.5.1. L'aggiornamento a questa versione di .NET Framework consentirà di risolvere il problema.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Principale|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|

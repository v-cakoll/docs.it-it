---
ms.openlocfilehash: 6c35174be50ffc5031d0c4183bd936b4ef27757e
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859796"
---
### <a name="sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs"></a>I metodi CompareGreaterThan SSE e SSE2 gestiscono correttamente gli input NaN

I metodi <xref:System.Runtime.Intrinsics.X86.Sse?displayProperty=nameWithType> e <xref:System.Runtime.Intrinsics.X86.Sse2?displayProperty=nameWithType> seguenti sono stati corretti per gestire `NaN` correttamente gli input e corrispondono al comportamento hardware dei metodi equivalenti nella <xref:System.Runtime.Intrinsics.X86.Avx?displayProperty=nameWithType> classe:

* `CompareGreaterThan`
* `CompareGreaterThanOrEqual`
* `CompareNotGreaterThan`
* `CompareNotGreaterThanOrEqual`
* `CompareScalarGreaterThan`
* `CompareScalarGreaterThanOrEqual`
* `CompareScalarNotGreaterThan`
* `CompareScalarNotGreaterThanOrEqual`

#### <a name="change-description"></a>Descrizione modifica:

In precedenza `NaN` , gli input per <xref:System.Runtime.Intrinsics.X86.Sse> i <xref:System.Runtime.Intrinsics.X86.Sse2> metodi e elencati restituivano un risultato errato. Anche il risultato è diverso dal risultato generato dal metodo corrispondente nella <xref:System.Runtime.Intrinsics.X86.Avx> classe.

A partire da .NET 5,0, questi metodi gestiscono `NaN` correttamente gli input e restituiscono gli stessi risultati dei metodi <xref:System.Runtime.Intrinsics.X86.Avx> corrispondenti nella classe.

Le architetture standard di settore Streaming SIMD Extensions (SSE) e Streaming SIMD Extensions 2 (SSE2) (ISA) non forniscono supporto hardware diretto per questi metodi di confronto, quindi sono implementate nel software. In precedenza, i metodi venivano implementati in modo non corretto e gli `NaN` input venivano gestiti in modo errato. Per il codice trasferito da nativo, il comportamento errato può presentare bug. Per un percorso di codice a 256 bit, i metodi possono anche produrre risultati diversi nei metodi equivalenti della <xref:System.Runtime.Intrinsics.X86.Avx> classe.

Come esempio del modo in cui i metodi non erano corretti in precedenza, `CompareNotGreaterThan(x,y)` è `CompareLessThanOrEqual(x,y)` possibile implementare come per i valori integer regolari. Tuttavia, per `NaN` gli input, la logica calcola il risultato errato. Al contrario, `CompareNotLessThan(y,x)` l'utilizzo di confronta correttamente i numeri `NaN` *e* prende in considerazione gli input.

#### <a name="version-introduced"></a>Versione introdotta

5,0 Anteprima 4

#### <a name="recommended-action"></a>Azione consigliata

- Se il comportamento precedente era un bug, non è necessaria alcuna modifica.

- Se era necessario il comportamento precedente, è possibile mantenere tale comportamento cambiando la chiamata pertinente come segue:

  * `CompareGreaterThan(x,y)` -> `CompareNotLessThanOrEqual(x,y)`
  * `CompareGreaterThanOrEqual(x,y)` -> `CompareNotLessThan(x,y)`
  * `CompareNotGreaterThan(x,y)` -> `CompareLessThanOrEqual(x,y)`
  * `CompareNotGreaterThanOrEqual(x,y)` -> `CompareLessThan(x,y)`
  * `CompareScalarGreaterThan(x,y)` -> `CompareScalarNotLessThanOrEqual(x,y)`
  * `CompareScalarGreaterThanOrEqual(x,y)` -> `CompareScalarNotLessThan(x,y)`
  * `CompareScalarNotGreaterThan(x,y)` -> `CompareScalarLessThanOrEqual(x,y)`
  * `CompareScalarNotGreaterThanOrEqual(x,y)` -> `CompareScalarLessThan(x,y)`

#### <a name="category"></a>Categoria

Principali librerie .NET

#### <a name="affected-apis"></a>API interessate

- <xref:System.Runtime.Intrinsics.X86.Sse.CompareGreaterThan(System.Runtime.Intrinsics.Vector128{System.Single},System.Runtime.Intrinsics.Vector128{System.Single})?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse.CompareGreaterThanOrEqual(System.Runtime.Intrinsics.Vector128{System.Single},System.Runtime.Intrinsics.Vector128{System.Single})?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse.CompareNotGreaterThan(System.Runtime.Intrinsics.Vector128{System.Single},System.Runtime.Intrinsics.Vector128{System.Single})?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse.CompareNotGreaterThanOrEqual(System.Runtime.Intrinsics.Vector128{System.Single},System.Runtime.Intrinsics.Vector128{System.Single})?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse.CompareScalarGreaterThan(System.Runtime.Intrinsics.Vector128{System.Single},System.Runtime.Intrinsics.Vector128{System.Single})?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse.CompareScalarGreaterThanOrEqual(System.Runtime.Intrinsics.Vector128{System.Single},System.Runtime.Intrinsics.Vector128{System.Single})?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse.CompareScalarNotGreaterThan(System.Runtime.Intrinsics.Vector128{System.Single},System.Runtime.Intrinsics.Vector128{System.Single})?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse.CompareScalarNotGreaterThanOrEqual(System.Runtime.Intrinsics.Vector128{System.Single},System.Runtime.Intrinsics.Vector128{System.Single})?displayProperty=fullName>

- <xref:System.Runtime.Intrinsics.X86.Sse2.CompareGreaterThan(System.Runtime.Intrinsics.Vector128{System.Double},System.Runtime.Intrinsics.Vector128{System.Double})?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse2.CompareGreaterThanOrEqual(System.Runtime.Intrinsics.Vector128{System.Double},System.Runtime.Intrinsics.Vector128{System.Double})?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse2.CompareNotGreaterThan(System.Runtime.Intrinsics.Vector128{System.Double},System.Runtime.Intrinsics.Vector128{System.Double})?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse2.CompareNotGreaterThanOrEqual(System.Runtime.Intrinsics.Vector128{System.Double},System.Runtime.Intrinsics.Vector128{System.Double})?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse2.CompareScalarGreaterThan(System.Runtime.Intrinsics.Vector128{System.Double},System.Runtime.Intrinsics.Vector128{System.Double})?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse2.CompareScalarGreaterThanOrEqual(System.Runtime.Intrinsics.Vector128{System.Double},System.Runtime.Intrinsics.Vector128{System.Double})?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse2.CompareScalarNotGreaterThan(System.Runtime.Intrinsics.Vector128{System.Double},System.Runtime.Intrinsics.Vector128{System.Double})?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse2.CompareScalarNotGreaterThanOrEqual(System.Runtime.Intrinsics.Vector128{System.Double},System.Runtime.Intrinsics.Vector128{System.Double})?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Runtime.Intrinsics.X86.Sse.CompareGreaterThan(System.Runtime.Intrinsics.Vector128{System.Single},System.Runtime.Intrinsics.Vector128{System.Single})`
- `M:System.Runtime.Intrinsics.X86.Sse.CompareGreaterThanOrEqual(System.Runtime.Intrinsics.Vector128{System.Single},System.Runtime.Intrinsics.Vector128{System.Single})`
- `M:System.Runtime.Intrinsics.X86.Sse.CompareNotGreaterThan(System.Runtime.Intrinsics.Vector128{System.Single},System.Runtime.Intrinsics.Vector128{System.Single})`
- `M:System.Runtime.Intrinsics.X86.Sse.CompareNotGreaterThanOrEqual(System.Runtime.Intrinsics.Vector128{System.Single},System.Runtime.Intrinsics.Vector128{System.Single})`
- `M:System.Runtime.Intrinsics.X86.Sse.CompareScalarGreaterThan(System.Runtime.Intrinsics.Vector128{System.Single},System.Runtime.Intrinsics.Vector128{System.Single})`
- `M:System.Runtime.Intrinsics.X86.Sse.CompareScalarGreaterThanOrEqual(System.Runtime.Intrinsics.Vector128{System.Single},System.Runtime.Intrinsics.Vector128{System.Single})`
- `M:System.Runtime.Intrinsics.X86.Sse.CompareScalarNotGreaterThan(System.Runtime.Intrinsics.Vector128{System.Single},System.Runtime.Intrinsics.Vector128{System.Single})`
- `M:System.Runtime.Intrinsics.X86.Sse.CompareScalarNotGreaterThanOrEqual(System.Runtime.Intrinsics.Vector128{System.Single},System.Runtime.Intrinsics.Vector128{System.Single})`

- `M:System.Runtime.Intrinsics.X86.Sse2.CompareGreaterThan(System.Runtime.Intrinsics.Vector128{System.Double},System.Runtime.Intrinsics.Vector128{System.Double})`
- `M:System.Runtime.Intrinsics.X86.Sse2.CompareGreaterThanOrEqual(System.Runtime.Intrinsics.Vector128{System.Double},System.Runtime.Intrinsics.Vector128{System.Double})`
- `M:System.Runtime.Intrinsics.X86.Sse2.CompareNotGreaterThan(System.Runtime.Intrinsics.Vector128{System.Double},System.Runtime.Intrinsics.Vector128{System.Double})`
- `M:System.Runtime.Intrinsics.X86.Sse2.CompareNotGreaterThanOrEqual(System.Runtime.Intrinsics.Vector128{System.Double},System.Runtime.Intrinsics.Vector128{System.Double})`
- `M:System.Runtime.Intrinsics.X86.Sse2.CompareScalarGreaterThan(System.Runtime.Intrinsics.Vector128{System.Double},System.Runtime.Intrinsics.Vector128{System.Double})`
- `M:System.Runtime.Intrinsics.X86.Sse2.CompareScalarGreaterThanOrEqual(System.Runtime.Intrinsics.Vector128{System.Double},System.Runtime.Intrinsics.Vector128{System.Double})`
- `M:System.Runtime.Intrinsics.X86.Sse2.CompareScalarNotGreaterThan(System.Runtime.Intrinsics.Vector128{System.Double},System.Runtime.Intrinsics.Vector128{System.Double})`
- `M:System.Runtime.Intrinsics.X86.Sse2.CompareScalarNotGreaterThanOrEqual(System.Runtime.Intrinsics.Vector128{System.Double},System.Runtime.Intrinsics.Vector128{System.Double})`

-->

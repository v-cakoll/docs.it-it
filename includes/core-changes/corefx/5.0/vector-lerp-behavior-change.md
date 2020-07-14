---
ms.openlocfilehash: 4bc060f991501b81db0cb7c521e55996a2b5e91e
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281303"
---
### <a name="behavior-change-for-vector2lerp-and-vector4lerp"></a>Modifica del comportamento per Vector2. Lerp e Vector4. Lerp

Implementazione di <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> e <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> modificata in modo da tenere conto di un errore di arrotondamento a virgola mobile.

#### <a name="change-description"></a>Descrizione modifica:

In precedenza, <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> e <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> venivano implementati come `value1 + (value2 - value1) * amount` . Tuttavia, a causa di un errore di arrotondamento a virgola mobile, questo algoritmo non restituisce sempre `value2` quando `amount` è `1.0f` .

In .NET 5,0 e versioni successive, l'implementazione utilizza lo stesso algoritmo di <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType> , ovvero `(value1 * (1.0f - amount)) + (value2 * amount)` . Questo algoritmo rappresenta correttamente l'errore di arrotondamento. A questo punto, quando `amount` è `1.0f` , il risultato è esattamente `value2` . L'algoritmo aggiornato consente inoltre l'ottimizzazione gratuita dell'algoritmo utilizzando <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> quando è disponibile.

#### <a name="version-introduced"></a>Versione introdotta

5,0 Anteprima 7

#### <a name="recommended-action"></a>Azione consigliata

Non è necessaria alcuna azione. Tuttavia, se si desidera mantenere il comportamento precedente, è possibile implementare una funzione personalizzata `Lerp` che utilizza l'algoritmo precedente di `value1 + (value2 - value1) * amount` .

#### <a name="category"></a>Categoria

Principali librerie .NET

#### <a name="affected-apis"></a>API interessate

- <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=fullName>
- <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)`
- `M:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)`

-->

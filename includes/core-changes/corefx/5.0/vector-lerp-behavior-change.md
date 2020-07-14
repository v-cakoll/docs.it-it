---
ms.openlocfilehash: 4bc060f991501b81db0cb7c521e55996a2b5e91e
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281303"
---
### <a name="behavior-change-for-vector2lerp-and-vector4lerp"></a><span data-ttu-id="2488a-101">Modifica del comportamento per Vector2. Lerp e Vector4. Lerp</span><span class="sxs-lookup"><span data-stu-id="2488a-101">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>

<span data-ttu-id="2488a-102">Implementazione di <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> e <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> modificata in modo da tenere conto di un errore di arrotondamento a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="2488a-102">The implementation of <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> and <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> changed to correctly account for a floating-point rounding error.</span></span>

#### <a name="change-description"></a><span data-ttu-id="2488a-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="2488a-103">Change description</span></span>

<span data-ttu-id="2488a-104">In precedenza, <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> e <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> venivano implementati come `value1 + (value2 - value1) * amount` .</span><span class="sxs-lookup"><span data-stu-id="2488a-104">Previously, <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> and <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> were implemented as `value1 + (value2 - value1) * amount`.</span></span> <span data-ttu-id="2488a-105">Tuttavia, a causa di un errore di arrotondamento a virgola mobile, questo algoritmo non restituisce sempre `value2` quando `amount` è `1.0f` .</span><span class="sxs-lookup"><span data-stu-id="2488a-105">However, due to a floating-point rounding error, this algorithm doesn't always return `value2` when `amount` is `1.0f`.</span></span>

<span data-ttu-id="2488a-106">In .NET 5,0 e versioni successive, l'implementazione utilizza lo stesso algoritmo di <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType> , ovvero `(value1 * (1.0f - amount)) + (value2 * amount)` .</span><span class="sxs-lookup"><span data-stu-id="2488a-106">In .NET 5.0 and later, the implementation uses the same algorithm as <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType>, which is `(value1 * (1.0f - amount)) + (value2 * amount)`.</span></span> <span data-ttu-id="2488a-107">Questo algoritmo rappresenta correttamente l'errore di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="2488a-107">This algorithm correctly accounts for the rounding error.</span></span> <span data-ttu-id="2488a-108">A questo punto, quando `amount` è `1.0f` , il risultato è esattamente `value2` .</span><span class="sxs-lookup"><span data-stu-id="2488a-108">Now, when `amount` is `1.0f`, the result is precisely `value2`.</span></span> <span data-ttu-id="2488a-109">L'algoritmo aggiornato consente inoltre l'ottimizzazione gratuita dell'algoritmo utilizzando <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> quando è disponibile.</span><span class="sxs-lookup"><span data-stu-id="2488a-109">The updated algorithm also allows the algorithm to be freely optimized using <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> when it's available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2488a-110">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="2488a-110">Version introduced</span></span>

<span data-ttu-id="2488a-111">5,0 Anteprima 7</span><span class="sxs-lookup"><span data-stu-id="2488a-111">5.0 Preview 7</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2488a-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="2488a-112">Recommended action</span></span>

<span data-ttu-id="2488a-113">Non è necessaria alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="2488a-113">No action is necessary.</span></span> <span data-ttu-id="2488a-114">Tuttavia, se si desidera mantenere il comportamento precedente, è possibile implementare una funzione personalizzata `Lerp` che utilizza l'algoritmo precedente di `value1 + (value2 - value1) * amount` .</span><span class="sxs-lookup"><span data-stu-id="2488a-114">However, if you want to maintain the old behavior, you can implement your own `Lerp` function that uses the previous algorithm of `value1 + (value2 - value1) * amount`.</span></span>

#### <a name="category"></a><span data-ttu-id="2488a-115">Categoria</span><span class="sxs-lookup"><span data-stu-id="2488a-115">Category</span></span>

<span data-ttu-id="2488a-116">Principali librerie .NET</span><span class="sxs-lookup"><span data-stu-id="2488a-116">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2488a-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="2488a-117">Affected APIs</span></span>

- <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=fullName>
- <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)`
- `M:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)`

-->

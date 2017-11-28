---
title: Conversione boxing di tipi nullable (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- boxing [C#], nullable types
- unboxing [C#], nullable types
- nullable types [C#], boxing and unboxing
ms.assetid: bdb5b626-abc0-405d-8f64-0f0a0bf883a4
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 29fccba56f6758fdfd407fa1879baa9260b69187
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="boxing-nullable-types-c-programming-guide"></a><span data-ttu-id="741f4-102">Conversione boxing di tipi nullable (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="741f4-102">Boxing Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="741f4-103">Gli oggetti basati su tipi nullable sono boxed solo se l'oggetto è diverso da null.</span><span class="sxs-lookup"><span data-stu-id="741f4-103">Objects based on nullable types are only boxed if the object is non-null.</span></span> <span data-ttu-id="741f4-104">Se <xref:System.Nullable%601.HasValue%2A> è `false`, il riferimento all'oggetto viene assegnato a `null` anziché alla conversione boxing.</span><span class="sxs-lookup"><span data-stu-id="741f4-104">If <xref:System.Nullable%601.HasValue%2A> is `false`, the object reference is assigned to `null` instead of boxing.</span></span> <span data-ttu-id="741f4-105">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="741f4-105">For example:</span></span>  
  
```csharp  
bool? b = null;  
object o = b;  
// Now o is null.  
```  
  
 <span data-ttu-id="741f4-106">Se l'oggetto è diverso da null (ovvero se <xref:System.Nullable%601.HasValue%2A> è `true`) viene eseguita la conversione boxing, ma solo il tipo sottostante su cui è basato l'oggetto è boxed.</span><span class="sxs-lookup"><span data-stu-id="741f4-106">If the object is non-null -- if <xref:System.Nullable%601.HasValue%2A> is `true` -- then boxing occurs, but only the underlying type that the nullable object is based on is boxed.</span></span> <span data-ttu-id="741f4-107">La conversione boxing di un tipo valore nullable diverso da null converte il tipo valore stesso e non <xref:System.Nullable%601?displayProperty=nameWithType>, usato per il wrapping del tipo valore.</span><span class="sxs-lookup"><span data-stu-id="741f4-107">Boxing a non-null nullable value type boxes the value type itself, not the <xref:System.Nullable%601?displayProperty=nameWithType> that wraps the value type.</span></span> <span data-ttu-id="741f4-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="741f4-108">For example:</span></span>  
  
```csharp  
bool? b = false;  
int? i = 44;  
object bBoxed = b; // bBoxed contains a boxed bool.  
object iBoxed = i; // iBoxed contains a boxed int.  
```  
  
 <span data-ttu-id="741f4-109">I due oggetti boxed sono identici a quelli creati dalla conversione boxing di tipi non nullable.</span><span class="sxs-lookup"><span data-stu-id="741f4-109">The two boxed objects are identical to those created by boxing non-nullable types.</span></span> <span data-ttu-id="741f4-110">E, proprio come i tipi boxed non nullable, possono essere boxed in tipi nullable, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="741f4-110">And, just like non-nullable boxed types, they can be unboxed into nullable types, as in the following example:</span></span>  
  
```csharp  
bool? b2 = (bool?)bBoxed;  
int? i2 = (int?)iBoxed;  
```  
  
## <a name="remarks"></a><span data-ttu-id="741f4-111">Note</span><span class="sxs-lookup"><span data-stu-id="741f4-111">Remarks</span></span>  
 <span data-ttu-id="741f4-112">Il comportamento di tipi nullable boxed offre due vantaggi:</span><span class="sxs-lookup"><span data-stu-id="741f4-112">The behavior of nullable types when boxed provides two advantages:</span></span>  
  
1.  <span data-ttu-id="741f4-113">È possibile testare gli oggetti nullable e la relativa controparte boxed per i valori null:</span><span class="sxs-lookup"><span data-stu-id="741f4-113">Nullable objects and their boxed counterpart can be tested for null:</span></span>  
  
    ```csharp  
    bool? b = null;  
    object boxedB = b;  
    if (b == null)  
    {  
      // True.  
    }  
    if (boxedB == null)  
    {  
      // Also true.  
    }  
    ```  
  
2.  <span data-ttu-id="741f4-114">I tipi nullable boxed supportano la funzionalità del tipo sottostante:</span><span class="sxs-lookup"><span data-stu-id="741f4-114">Boxed nullable types fully support the functionality of the underlying type:</span></span>  
  
    ```csharp  
    double? d = 44.4;  
    object iBoxed = d;  
    // Access IConvertible interface implemented by double.  
    IConvertible ic = (IConvertible)iBoxed;  
    int i = ic.ToInt32(null);  
    string str = ic.ToString();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="741f4-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="741f4-115">See Also</span></span>  
 [<span data-ttu-id="741f4-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="741f4-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="741f4-117">Tipi nullable</span><span class="sxs-lookup"><span data-stu-id="741f4-117">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="741f4-118">Procedura: Identificare un tipo nullable</span><span class="sxs-lookup"><span data-stu-id="741f4-118">How to: Identify a Nullable Type</span></span>](../../../csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type.md)

---
title: Conversione boxing di tipi nullable (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- boxing [C#], nullable types
- unboxing [C#], nullable types
- nullable types [C#], boxing and unboxing
ms.assetid: bdb5b626-abc0-405d-8f64-0f0a0bf883a4
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5ce063a70ced98fd8b99b4b46d704e08ddc96e10
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="boxing-nullable-types-c-programming-guide"></a><span data-ttu-id="0b244-102">Conversione boxing di tipi nullable (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="0b244-102">Boxing Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="0b244-103">Gli oggetti basati su tipi nullable sono boxed solo se l'oggetto è diverso da null.</span><span class="sxs-lookup"><span data-stu-id="0b244-103">Objects based on nullable types are only boxed if the object is non-null.</span></span> <span data-ttu-id="0b244-104">Se <xref:System.Nullable%601.HasValue%2A> è `false`, il riferimento all'oggetto viene assegnato a `null` anziché alla conversione boxing.</span><span class="sxs-lookup"><span data-stu-id="0b244-104">If <xref:System.Nullable%601.HasValue%2A> is `false`, the object reference is assigned to `null` instead of boxing.</span></span> <span data-ttu-id="0b244-105">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0b244-105">For example:</span></span>  
  
```csharp  
bool? b = null;  
object o = b;  
// Now o is null.  
```  
  
 <span data-ttu-id="0b244-106">Se l'oggetto è diverso da null (ovvero se <xref:System.Nullable%601.HasValue%2A> è `true`) viene eseguita la conversione boxing, ma solo il tipo sottostante su cui è basato l'oggetto è boxed.</span><span class="sxs-lookup"><span data-stu-id="0b244-106">If the object is non-null -- if <xref:System.Nullable%601.HasValue%2A> is `true` -- then boxing occurs, but only the underlying type that the nullable object is based on is boxed.</span></span> <span data-ttu-id="0b244-107">La conversione boxing di un tipo valore nullable diverso da null converte il tipo valore stesso e non <xref:System.Nullable%601?displayProperty=fullName>, usato per il wrapping del tipo valore.</span><span class="sxs-lookup"><span data-stu-id="0b244-107">Boxing a non-null nullable value type boxes the value type itself, not the <xref:System.Nullable%601?displayProperty=fullName> that wraps the value type.</span></span> <span data-ttu-id="0b244-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0b244-108">For example:</span></span>  
  
```csharp  
bool? b = false;  
int? i = 44;  
object bBoxed = b; // bBoxed contains a boxed bool.  
object iBoxed = i; // iBoxed contains a boxed int.  
```  
  
 <span data-ttu-id="0b244-109">I due oggetti boxed sono identici a quelli creati dalla conversione boxing di tipi non nullable.</span><span class="sxs-lookup"><span data-stu-id="0b244-109">The two boxed objects are identical to those created by boxing non-nullable types.</span></span> <span data-ttu-id="0b244-110">E, proprio come i tipi boxed non nullable, possono essere boxed in tipi nullable, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0b244-110">And, just like non-nullable boxed types, they can be unboxed into nullable types, as in the following example:</span></span>  
  
```csharp  
bool? b2 = (bool?)bBoxed;  
int? i2 = (int?)iBoxed;  
```  
  
## <a name="remarks"></a><span data-ttu-id="0b244-111">Note</span><span class="sxs-lookup"><span data-stu-id="0b244-111">Remarks</span></span>  
 <span data-ttu-id="0b244-112">Il comportamento di tipi nullable boxed offre due vantaggi:</span><span class="sxs-lookup"><span data-stu-id="0b244-112">The behavior of nullable types when boxed provides two advantages:</span></span>  
  
1.  <span data-ttu-id="0b244-113">È possibile testare gli oggetti nullable e la relativa controparte boxed per i valori null:</span><span class="sxs-lookup"><span data-stu-id="0b244-113">Nullable objects and their boxed counterpart can be tested for null:</span></span>  
  
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
  
2.  <span data-ttu-id="0b244-114">I tipi nullable boxed supportano la funzionalità del tipo sottostante:</span><span class="sxs-lookup"><span data-stu-id="0b244-114">Boxed nullable types fully support the functionality of the underlying type:</span></span>  
  
    ```csharp  
    double? d = 44.4;  
    object iBoxed = d;  
    // Access IConvertible interface implemented by double.  
    IConvertible ic = (IConvertible)iBoxed;  
    int i = ic.ToInt32(null);  
    string str = ic.ToString();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0b244-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b244-115">See Also</span></span>  
 <span data-ttu-id="0b244-116">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0b244-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0b244-117">[Tipi nullable](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="0b244-117">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 [<span data-ttu-id="0b244-118">Procedura: Identificare un tipo nullable</span><span class="sxs-lookup"><span data-stu-id="0b244-118">How to: Identify a Nullable Type</span></span>](../../../csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type.md)


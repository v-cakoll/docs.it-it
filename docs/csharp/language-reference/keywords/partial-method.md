---
title: parziale (Metodo) (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- partialmethod_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
caps.latest.revision: 26
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
ms.openlocfilehash: b6f8ecca01ebf681c906b73abefc94e9e45b8700
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="partial-method-c-reference"></a><span data-ttu-id="7b5ee-102">parziale (Metodo) (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="7b5ee-102">partial (Method) (C# Reference)</span></span>
<span data-ttu-id="7b5ee-103">Un metodo parziale ha la firma definita in una parte di un tipo parziale e l'implementazione definita in un'altra parte del tipo.</span><span class="sxs-lookup"><span data-stu-id="7b5ee-103">A partial method has its signature defined in one part of a partial type, and its implementation defined in another part of the type.</span></span> <span data-ttu-id="7b5ee-104">I metodi parziali consentono a Progettazione classi di fornire gli hook del metodo, analoghi ai gestori eventi, che gli sviluppatori possono decidere se implementare o meno.</span><span class="sxs-lookup"><span data-stu-id="7b5ee-104">Partial methods enable class designers to provide method hooks, similar to event handlers, that developers may decide to implement or not.</span></span> <span data-ttu-id="7b5ee-105">Se lo sviluppatore non fornisce un'implementazione, il compilatore rimuove la firma in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="7b5ee-105">If the developer does not supply an implementation, the compiler removes the signature at compile time.</span></span> <span data-ttu-id="7b5ee-106">Ai metodi parziali si applicano le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b5ee-106">The following conditions apply to partial methods:</span></span>  
  
-   <span data-ttu-id="7b5ee-107">Le firme nelle due parti del tipo parziale devono corrispondere.</span><span class="sxs-lookup"><span data-stu-id="7b5ee-107">Signatures in both parts of the partial type must match.</span></span>  
  
-   <span data-ttu-id="7b5ee-108">Il metodo deve restituire void.</span><span class="sxs-lookup"><span data-stu-id="7b5ee-108">The method must return void.</span></span>  
  
-   <span data-ttu-id="7b5ee-109">Non è consentito alcun modificatore di accesso.</span><span class="sxs-lookup"><span data-stu-id="7b5ee-109">No access modifiers are allowed.</span></span> <span data-ttu-id="7b5ee-110">I metodi parziali sono implicitamente privati.</span><span class="sxs-lookup"><span data-stu-id="7b5ee-110">Partial methods are implicitly private.</span></span>  
  
 <span data-ttu-id="7b5ee-111">Nell'esempio seguente viene illustrato un metodo parziale definito in due parti di una classe parziale:</span><span class="sxs-lookup"><span data-stu-id="7b5ee-111">The following example shows a partial method defined in two parts of a partial class:</span></span>  
  
 <span data-ttu-id="7b5ee-112">[!code-cs[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7b5ee-112">[!code-cs[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]</span></span>  
  
 <span data-ttu-id="7b5ee-113">Per altre informazioni, vedere [Classi e metodi parziali](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="7b5ee-113">For more information, see [Partial Classes and Methods](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b5ee-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b5ee-114">See Also</span></span>  
 <span data-ttu-id="7b5ee-115">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="7b5ee-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 [<span data-ttu-id="7b5ee-116">partial (tipo)</span><span class="sxs-lookup"><span data-stu-id="7b5ee-116">partial (Type)</span></span>](../../../csharp/language-reference/keywords/partial-type.md)


---
title: parziale (Metodo) (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 03962a59d5dbe0146cad9835f81d41c06914795b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="partial-method-c-reference"></a><span data-ttu-id="5410a-102">parziale (Metodo) (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="5410a-102">partial (Method) (C# Reference)</span></span>
<span data-ttu-id="5410a-103">Un metodo parziale ha la firma definita in una parte di un tipo parziale e l'implementazione definita in un'altra parte del tipo.</span><span class="sxs-lookup"><span data-stu-id="5410a-103">A partial method has its signature defined in one part of a partial type, and its implementation defined in another part of the type.</span></span> <span data-ttu-id="5410a-104">I metodi parziali consentono a Progettazione classi di fornire gli hook del metodo, analoghi ai gestori eventi, che gli sviluppatori possono decidere se implementare o meno.</span><span class="sxs-lookup"><span data-stu-id="5410a-104">Partial methods enable class designers to provide method hooks, similar to event handlers, that developers may decide to implement or not.</span></span> <span data-ttu-id="5410a-105">Se lo sviluppatore non fornisce un'implementazione, il compilatore rimuove la firma in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="5410a-105">If the developer does not supply an implementation, the compiler removes the signature at compile time.</span></span> <span data-ttu-id="5410a-106">Ai metodi parziali si applicano le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5410a-106">The following conditions apply to partial methods:</span></span>  
  
-   <span data-ttu-id="5410a-107">Le firme nelle due parti del tipo parziale devono corrispondere.</span><span class="sxs-lookup"><span data-stu-id="5410a-107">Signatures in both parts of the partial type must match.</span></span>  
  
-   <span data-ttu-id="5410a-108">Il metodo deve restituire void.</span><span class="sxs-lookup"><span data-stu-id="5410a-108">The method must return void.</span></span>  
  
-   <span data-ttu-id="5410a-109">Non è consentito alcun modificatore di accesso.</span><span class="sxs-lookup"><span data-stu-id="5410a-109">No access modifiers are allowed.</span></span> <span data-ttu-id="5410a-110">I metodi parziali sono implicitamente privati.</span><span class="sxs-lookup"><span data-stu-id="5410a-110">Partial methods are implicitly private.</span></span>  
  
 <span data-ttu-id="5410a-111">Nell'esempio seguente viene illustrato un metodo parziale definito in due parti di una classe parziale:</span><span class="sxs-lookup"><span data-stu-id="5410a-111">The following example shows a partial method defined in two parts of a partial class:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]  
  
 <span data-ttu-id="5410a-112">Per altre informazioni, vedere [Classi e metodi parziali](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="5410a-112">For more information, see [Partial Classes and Methods](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5410a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5410a-113">See Also</span></span>  
 [<span data-ttu-id="5410a-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="5410a-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5410a-115">partial (tipo)</span><span class="sxs-lookup"><span data-stu-id="5410a-115">partial (Type)</span></span>](../../../csharp/language-reference/keywords/partial-type.md)

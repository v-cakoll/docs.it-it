---
title: -&gt; Operatore (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: fb95e508ce1339868723bcc3178851e8c1355c1f
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44271247"
---
# <a name="-gt-operator-c-reference"></a><span data-ttu-id="6defe-102">-&gt; Operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="6defe-102">-&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="6defe-103">L'operatore `->` combina la deferenziazione del puntatore e l'accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="6defe-103">The `->` operator combines pointer dereferencing and member access.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6defe-104">Note</span><span class="sxs-lookup"><span data-stu-id="6defe-104">Remarks</span></span>  
 <span data-ttu-id="6defe-105">Un'espressione nel formato</span><span class="sxs-lookup"><span data-stu-id="6defe-105">An expression of the form,</span></span>  
  
```csharp  
x->y  
```  
  
 <span data-ttu-id="6defe-106">(dove `x` è un puntatore di tipo `T*` e `y` è un membro di `T`) è equivalente a</span><span class="sxs-lookup"><span data-stu-id="6defe-106">(where `x` is a pointer of type `T*` and `y` is a member of `T`) is equivalent to,</span></span>  
  
```csharp  
(*x).y  
```  
  
 <span data-ttu-id="6defe-107">L'operatore `->` può essere usato solo nel codice contrassegnato come [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="6defe-107">The `->` operator can be used only in code that is marked as [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span></span>  
  
 <span data-ttu-id="6defe-108">Non è possibile sottoporre l'operatore `->` a overload.</span><span class="sxs-lookup"><span data-stu-id="6defe-108">The `->` operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6defe-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="6defe-109">Example</span></span>  
 [!code-csharp[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="6defe-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6defe-110">See Also</span></span>

- [<span data-ttu-id="6defe-111">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="6defe-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="6defe-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="6defe-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="6defe-113">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="6defe-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

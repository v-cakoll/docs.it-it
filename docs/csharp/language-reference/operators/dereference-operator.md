---
title: -&gt; Operatore (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ->_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
caps.latest.revision: 19
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
ms.openlocfilehash: f42135e43bdfc58ee64fd3465074b3f8791f8ada
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-gt-operator-c-reference"></a><span data-ttu-id="5e9ed-102">-&gt; Operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="5e9ed-102">-&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="5e9ed-103">L'operatore `->` combina la deferenziazione del puntatore e l'accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="5e9ed-103">The `->` operator combines pointer dereferencing and member access.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e9ed-104">Note</span><span class="sxs-lookup"><span data-stu-id="5e9ed-104">Remarks</span></span>  
 <span data-ttu-id="5e9ed-105">Un'espressione nel formato</span><span class="sxs-lookup"><span data-stu-id="5e9ed-105">An expression of the form,</span></span>  
  
```  
x->y  
```  
  
 <span data-ttu-id="5e9ed-106">(dove `x` è un puntatore di tipo `T*` e `y` è un membro di `T`) è equivalente a</span><span class="sxs-lookup"><span data-stu-id="5e9ed-106">(where `x` is a pointer of type `T*` and `y` is a member of `T`) is equivalent to,</span></span>  
  
```  
(*x).y  
```  
  
 <span data-ttu-id="5e9ed-107">L'operatore `->` può essere usato solo nel codice contrassegnato come [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="5e9ed-107">The `->` operator can be used only in code that is marked as [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span></span>  
  
 <span data-ttu-id="5e9ed-108">Non è possibile eseguire l'overload dell'operatore `->`.</span><span class="sxs-lookup"><span data-stu-id="5e9ed-108">The `->` operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e9ed-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="5e9ed-109">Example</span></span>  
 <span data-ttu-id="5e9ed-110">[!code-cs[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5e9ed-110">[!code-cs[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e9ed-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e9ed-111">See Also</span></span>  
 <span data-ttu-id="5e9ed-112">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="5e9ed-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="5e9ed-113">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5e9ed-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="5e9ed-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="5e9ed-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)


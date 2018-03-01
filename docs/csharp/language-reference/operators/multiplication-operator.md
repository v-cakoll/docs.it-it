---
title: '* Operatore (Riferimenti per C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 64c32def0935f4347f9aaccc2865b9cd33dd8a70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="b5dfb-102">Operatore \* (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b5dfb-102">\* Operator (C# Reference)</span></span>
<span data-ttu-id="b5dfb-103">L'operatore di moltiplicazione (`*`), che calcola il prodotto degli operandi.</span><span class="sxs-lookup"><span data-stu-id="b5dfb-103">The multiplication operator (`*`), which computes the product of its operands.</span></span>  <span data-ttu-id="b5dfb-104">L'operatore di dereferenziazione, che consente la lettura e scrittura in un puntatore.</span><span class="sxs-lookup"><span data-stu-id="b5dfb-104">Also, the dereference operator, which allows reading and writing to a pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5dfb-105">Note</span><span class="sxs-lookup"><span data-stu-id="b5dfb-105">Remarks</span></span>  
 <span data-ttu-id="b5dfb-106">Tutti i tipi numerici hanno operatori di moltiplicazione predefiniti.</span><span class="sxs-lookup"><span data-stu-id="b5dfb-106">All numeric types have predefined multiplication operators.</span></span>  
  
 <span data-ttu-id="b5dfb-107">L'operatore `*` viene anche usato per dichiarare i tipi di puntatore e dereferenziare i puntatori.</span><span class="sxs-lookup"><span data-stu-id="b5dfb-107">The `*` operator is also used to declare pointer types and to dereference pointers.</span></span> <span data-ttu-id="b5dfb-108">Questo operatore può essere usato solo in contesti non sicuri, che sono identificati dall'uso della parola chiave [unsafe](../../../csharp/language-reference/keywords/unsafe.md) e richiedono l'opzione [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) del compilatore.</span><span class="sxs-lookup"><span data-stu-id="b5dfb-108">This operator can only be used in unsafe contexts, denoted by the use of the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, and requiring the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>  <span data-ttu-id="b5dfb-109">L'operatore di dereferenziazione è noto anche come operatore di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="b5dfb-109">The dereference operator is also known as the indirection operator.</span></span>  
  
 <span data-ttu-id="b5dfb-110">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `*` (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="b5dfb-110">User-defined types can overload the binary `*` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="b5dfb-111">Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente.</span><span class="sxs-lookup"><span data-stu-id="b5dfb-111">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5dfb-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="b5dfb-112">Example</span></span>  
 [!code-csharp[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="b5dfb-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="b5dfb-113">Example</span></span>  
 [!code-csharp[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b5dfb-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5dfb-114">See Also</span></span>  
 [<span data-ttu-id="b5dfb-115">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="b5dfb-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b5dfb-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b5dfb-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b5dfb-117">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="b5dfb-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="b5dfb-118">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="b5dfb-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

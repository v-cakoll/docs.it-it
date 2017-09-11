---
title: '* Operatore (Riferimenti per C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '*_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
caps.latest.revision: 14
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
ms.openlocfilehash: 165ca8f797eb8d03ae1dec8c0ec5e1f4b31cb050
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="3f1af-102">Operatore * (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="3f1af-102">* Operator (C# Reference)</span></span>
<span data-ttu-id="3f1af-103">L'operatore di moltiplicazione (`*`), che calcola il prodotto degli operandi.</span><span class="sxs-lookup"><span data-stu-id="3f1af-103">The multiplication operator (`*`), which computes the product of its operands.</span></span>  <span data-ttu-id="3f1af-104">L'operatore di dereferenziazione, che consente la lettura e scrittura in un puntatore.</span><span class="sxs-lookup"><span data-stu-id="3f1af-104">Also, the dereference operator, which allows reading and writing to a pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f1af-105">Note</span><span class="sxs-lookup"><span data-stu-id="3f1af-105">Remarks</span></span>  
 <span data-ttu-id="3f1af-106">Tutti i tipi numerici hanno operatori di moltiplicazione predefiniti.</span><span class="sxs-lookup"><span data-stu-id="3f1af-106">All numeric types have predefined multiplication operators.</span></span>  
  
 <span data-ttu-id="3f1af-107">L'operatore `*` viene anche usato per dichiarare i tipi di puntatore e dereferenziare i puntatori.</span><span class="sxs-lookup"><span data-stu-id="3f1af-107">The `*` operator is also used to declare pointer types and to dereference pointers.</span></span> <span data-ttu-id="3f1af-108">Questo operatore può essere usato solo in contesti non sicuri, che sono identificati dall'uso della parola chiave [unsafe](../../../csharp/language-reference/keywords/unsafe.md) e richiedono l'opzione [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) del compilatore.</span><span class="sxs-lookup"><span data-stu-id="3f1af-108">This operator can only be used in unsafe contexts, denoted by the use of the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, and requiring the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>  <span data-ttu-id="3f1af-109">L'operatore di dereferenziazione è noto anche come operatore di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="3f1af-109">The dereference operator is also known as the indirection operator.</span></span>  
  
 <span data-ttu-id="3f1af-110">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `*` (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="3f1af-110">User-defined types can overload the binary `*` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="3f1af-111">Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente.</span><span class="sxs-lookup"><span data-stu-id="3f1af-111">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f1af-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="3f1af-112">Example</span></span>  
 <span data-ttu-id="3f1af-113">[!code-cs[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3f1af-113">[!code-cs[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f1af-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="3f1af-114">Example</span></span>  
 <span data-ttu-id="3f1af-115">[!code-cs[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="3f1af-115">[!code-cs[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f1af-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f1af-116">See Also</span></span>  
 <span data-ttu-id="3f1af-117">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3f1af-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3f1af-118">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3f1af-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3f1af-119">[Codice unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="3f1af-119">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 [<span data-ttu-id="3f1af-120">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="3f1af-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)


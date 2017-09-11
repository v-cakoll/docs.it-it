---
title: Operatore ++ (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ++_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9f481dbe2437495b109d6d41cd24c8b4bb5b6a5b
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="c372b-102">Operatore ++ (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="c372b-102">++ Operator (C# Reference)</span></span>
<span data-ttu-id="c372b-103">L'operatore di incremento (`++`) incrementa il suo operando di 1.</span><span class="sxs-lookup"><span data-stu-id="c372b-103">The increment operator (`++`) increments its operand by 1.</span></span> <span data-ttu-id="c372b-104">L'operatore di incremento può apparire prima o dopo il suo operando: `++variable` e `variable++`.</span><span class="sxs-lookup"><span data-stu-id="c372b-104">The increment operator can appear before or after its operand: `++variable` and `variable++`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c372b-105">Note</span><span class="sxs-lookup"><span data-stu-id="c372b-105">Remarks</span></span>  
 <span data-ttu-id="c372b-106">Il primo modulo è un'operazione di incremento prefisso.</span><span class="sxs-lookup"><span data-stu-id="c372b-106">The first form is a prefix increment operation.</span></span> <span data-ttu-id="c372b-107">Il risultato dell'operazione è il valore dell'operando dopo essere stato incrementato.</span><span class="sxs-lookup"><span data-stu-id="c372b-107">The result of the operation is the value of the operand after it has been incremented.</span></span>  
  
 <span data-ttu-id="c372b-108">Il secondo modulo è un'operazione di incremento suffisso.</span><span class="sxs-lookup"><span data-stu-id="c372b-108">The second form is a postfix increment operation.</span></span> <span data-ttu-id="c372b-109">Il risultato dell'operazione è il valore dell'operando prima di essere incrementato.</span><span class="sxs-lookup"><span data-stu-id="c372b-109">The result of the operation is the value of the operand before it has been incremented.</span></span>  
  
 <span data-ttu-id="c372b-110">I tipi numerico e di enumerazione hanno operatori di incremento predefiniti.</span><span class="sxs-lookup"><span data-stu-id="c372b-110">Numeric and enumeration types have predefined increment operators.</span></span> <span data-ttu-id="c372b-111">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `++` .</span><span class="sxs-lookup"><span data-stu-id="c372b-111">User-defined types can overload the `++` operator.</span></span> <span data-ttu-id="c372b-112">Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="c372b-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c372b-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="c372b-113">Example</span></span>  
 <span data-ttu-id="c372b-114">[!code-cs[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c372b-114">[!code-cs[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c372b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c372b-115">See Also</span></span>  
 <span data-ttu-id="c372b-116">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c372b-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c372b-117">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c372b-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="c372b-118">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="c372b-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)


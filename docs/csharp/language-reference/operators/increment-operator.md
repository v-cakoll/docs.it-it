---
title: Operatore ++ (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: a52f614ce1bbfb8e9d9be686b277c1e69f6f9d35
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48030470"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="29460-102">Operatore ++ (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="29460-102">++ Operator (C# Reference)</span></span>
<span data-ttu-id="29460-103">L'operatore di incremento (`++`) incrementa il suo operando di 1.</span><span class="sxs-lookup"><span data-stu-id="29460-103">The increment operator (`++`) increments its operand by 1.</span></span> <span data-ttu-id="29460-104">L'operatore di incremento può apparire prima o dopo il suo operando: `++variable` e `variable++`.</span><span class="sxs-lookup"><span data-stu-id="29460-104">The increment operator can appear before or after its operand: `++variable` and `variable++`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29460-105">Note</span><span class="sxs-lookup"><span data-stu-id="29460-105">Remarks</span></span>  
 <span data-ttu-id="29460-106">Il primo modulo è un'operazione di incremento prefisso.</span><span class="sxs-lookup"><span data-stu-id="29460-106">The first form is a prefix increment operation.</span></span> <span data-ttu-id="29460-107">Il risultato dell'operazione è il valore dell'operando dopo essere stato incrementato.</span><span class="sxs-lookup"><span data-stu-id="29460-107">The result of the operation is the value of the operand after it has been incremented.</span></span>  
  
 <span data-ttu-id="29460-108">Il secondo modulo è un'operazione di incremento suffisso.</span><span class="sxs-lookup"><span data-stu-id="29460-108">The second form is a postfix increment operation.</span></span> <span data-ttu-id="29460-109">Il risultato dell'operazione è il valore dell'operando prima di essere incrementato.</span><span class="sxs-lookup"><span data-stu-id="29460-109">The result of the operation is the value of the operand before it has been incremented.</span></span>  
  
 <span data-ttu-id="29460-110">I tipi numerico e di enumerazione hanno operatori di incremento predefiniti.</span><span class="sxs-lookup"><span data-stu-id="29460-110">Numeric and enumeration types have predefined increment operators.</span></span> <span data-ttu-id="29460-111">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `++` .</span><span class="sxs-lookup"><span data-stu-id="29460-111">User-defined types can overload the `++` operator.</span></span> <span data-ttu-id="29460-112">Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="29460-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29460-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="29460-113">Example</span></span>  
 [!code-csharp[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="29460-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29460-114">See Also</span></span>

- [<span data-ttu-id="29460-115">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="29460-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="29460-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="29460-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="29460-117">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="29460-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

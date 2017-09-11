---
title: . Operatore (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ._CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
caps.latest.revision: 21
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
ms.openlocfilehash: fdc7c1821548509f3a3750aef2836c034f7aa53b
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="855dc-103">.</span><span class="sxs-lookup"><span data-stu-id="855dc-103">.</span></span> <span data-ttu-id="855dc-104">Operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="855dc-104">Operator (C# Reference)</span></span>
<span data-ttu-id="855dc-105">L'operatore punto (`.`) viene usato per l'accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="855dc-105">The dot operator (`.`) is used for member access.</span></span> <span data-ttu-id="855dc-106">L'operatore punto specifica un membro di un tipo o di uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="855dc-106">The dot operator specifies a member of a type or namespace.</span></span> <span data-ttu-id="855dc-107">Ad esempio, viene usato per accedere a metodi specifici all'interno delle librerie di classi .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="855dc-107">For example, the dot operator is used to access specific methods within the .NET Framework class libraries:</span></span>  
  
 <span data-ttu-id="855dc-108">[!code-cs[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="855dc-108">[!code-cs[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="855dc-109">Si consideri ad esempio la classe seguente:</span><span class="sxs-lookup"><span data-stu-id="855dc-109">For example, consider the following class:</span></span>  
  
 <span data-ttu-id="855dc-110">[!code-cs[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="855dc-110">[!code-cs[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_2.cs)]</span></span>  
  
 <span data-ttu-id="855dc-111">[!code-cs[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="855dc-111">[!code-cs[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_3.cs)]</span></span>  
  
 <span data-ttu-id="855dc-112">La variabile `s` ha due membri, `a` e `b`, per accedere ai quali è necessario usare l'operatore punto:</span><span class="sxs-lookup"><span data-stu-id="855dc-112">The variable `s` has two members, `a` and `b`; to access them, use the dot operator:</span></span>  
  
 <span data-ttu-id="855dc-113">[!code-cs[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="855dc-113">[!code-cs[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_4.cs)]</span></span>  
  
 <span data-ttu-id="855dc-114">Il punto viene usato anche per formare nomi completi, ovvero nomi che specificano lo spazio dei nomi o l'interfaccia, ad esempio, a cui appartengono.</span><span class="sxs-lookup"><span data-stu-id="855dc-114">The dot is also used to form qualified names, which are names that specify the namespace or interface, for example, to which they belong.</span></span>  
  
 <span data-ttu-id="855dc-115">[!code-cs[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="855dc-115">[!code-cs[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_5.cs)]</span></span>  
  
 <span data-ttu-id="855dc-116">La direttiva using rende facoltativa la qualificazione di alcuni nomi:</span><span class="sxs-lookup"><span data-stu-id="855dc-116">The using directive makes some name qualification optional:</span></span>  
  
 <span data-ttu-id="855dc-117">[!code-cs[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="855dc-117">[!code-cs[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_6.cs)]</span></span>  
  
 <span data-ttu-id="855dc-118">Ma quando un identificatore è ambiguo, deve essere qualificato:</span><span class="sxs-lookup"><span data-stu-id="855dc-118">But when an identifier is ambiguous, it must be qualified:</span></span>  
  
 <span data-ttu-id="855dc-119">[!code-cs[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="855dc-119">[!code-cs[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_7.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="855dc-120">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="855dc-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="855dc-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="855dc-121">See Also</span></span>  
 <span data-ttu-id="855dc-122">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="855dc-122">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="855dc-123">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="855dc-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="855dc-124">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="855dc-124">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)


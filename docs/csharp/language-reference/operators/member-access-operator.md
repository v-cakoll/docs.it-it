---
title: . Operatore (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- ._CSharpKeyword
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
ms.openlocfilehash: 088f1991cafa92a69e11ca14bd2d983b36c0e3ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="8529d-103">.</span><span class="sxs-lookup"><span data-stu-id="8529d-103">.</span></span> <span data-ttu-id="8529d-104">Operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="8529d-104">Operator (C# Reference)</span></span>
<span data-ttu-id="8529d-105">L'operatore punto (`.`) viene usato per l'accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="8529d-105">The dot operator (`.`) is used for member access.</span></span> <span data-ttu-id="8529d-106">L'operatore punto specifica un membro di un tipo o di uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8529d-106">The dot operator specifies a member of a type or namespace.</span></span> <span data-ttu-id="8529d-107">Ad esempio, viene usato per accedere a metodi specifici all'interno delle librerie di classi .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8529d-107">For example, the dot operator is used to access specific methods within the .NET Framework class libraries:</span></span>  
  
 [!code-csharp[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_1.cs)]  
  
 <span data-ttu-id="8529d-108">Si consideri ad esempio la classe seguente:</span><span class="sxs-lookup"><span data-stu-id="8529d-108">For example, consider the following class:</span></span>  
  
 [!code-csharp[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_2.cs)]  
  
 [!code-csharp[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_3.cs)]  
  
 <span data-ttu-id="8529d-109">La variabile `s` ha due membri, `a` e `b`, per accedere ai quali è necessario usare l'operatore punto:</span><span class="sxs-lookup"><span data-stu-id="8529d-109">The variable `s` has two members, `a` and `b`; to access them, use the dot operator:</span></span>  
  
 [!code-csharp[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_4.cs)]  
  
 <span data-ttu-id="8529d-110">Il punto viene usato anche per formare nomi completi, ovvero nomi che specificano lo spazio dei nomi o l'interfaccia, ad esempio, a cui appartengono.</span><span class="sxs-lookup"><span data-stu-id="8529d-110">The dot is also used to form qualified names, which are names that specify the namespace or interface, for example, to which they belong.</span></span>  
  
 [!code-csharp[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_5.cs)]  
  
 <span data-ttu-id="8529d-111">La direttiva using rende facoltativa la qualificazione di alcuni nomi:</span><span class="sxs-lookup"><span data-stu-id="8529d-111">The using directive makes some name qualification optional:</span></span>  
  
 [!code-csharp[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_6.cs)]  
  
 <span data-ttu-id="8529d-112">Ma quando un identificatore è ambiguo, deve essere qualificato:</span><span class="sxs-lookup"><span data-stu-id="8529d-112">But when an identifier is ambiguous, it must be qualified:</span></span>  
  
 [!code-csharp[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_7.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="8529d-113">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="8529d-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8529d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8529d-114">See Also</span></span>  
 [<span data-ttu-id="8529d-115">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="8529d-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8529d-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="8529d-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8529d-117">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="8529d-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

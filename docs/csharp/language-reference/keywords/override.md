---
title: override (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- override
- override_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
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
ms.openlocfilehash: 0f5a87eaa5894b61187c379c92ad785336aa79b2
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="override-c-reference"></a><span data-ttu-id="2fef8-102">override (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="2fef8-102">override (C# Reference)</span></span>
<span data-ttu-id="2fef8-103">Il modificatore `override` è necessario per estendere o modificare l'implementazione astratta o virtuale di un metodo, una proprietà, un indicizzatore o un evento ereditato.</span><span class="sxs-lookup"><span data-stu-id="2fef8-103">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fef8-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="2fef8-104">Example</span></span>  
 <span data-ttu-id="2fef8-105">In questo esempio la classe `Square` deve specificare un'implementazione sottoposta a override di `Area` poiché `Area` viene ereditato da `ShapesClass` astratto:</span><span class="sxs-lookup"><span data-stu-id="2fef8-105">In this example, the `Square` class must provide an overridden implementation of `Area` because `Area` is inherited from the abstract `ShapesClass`:</span></span>  
  
 <span data-ttu-id="2fef8-106">[!code-cs[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2fef8-106">[!code-cs[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_1.cs)]</span></span>  
  
 <span data-ttu-id="2fef8-107">Un metodo `override` offre una nuova implementazione di un membro ereditato da una classe base.</span><span class="sxs-lookup"><span data-stu-id="2fef8-107">An `override` method provides a new implementation of a member that is inherited from a base class.</span></span> <span data-ttu-id="2fef8-108">Il metodo che viene sottoposto a override mediante una dichiarazione `override` viene definito metodo di base sottoposto a override.</span><span class="sxs-lookup"><span data-stu-id="2fef8-108">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="2fef8-109">Il metodo di base sottoposto a override deve avere la stessa firma del metodo `override`.</span><span class="sxs-lookup"><span data-stu-id="2fef8-109">The overridden base method must have the same signature as the `override` method.</span></span> <span data-ttu-id="2fef8-110">Per informazioni sull'ereditarietà, vedere [Ereditarietà](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="2fef8-110">For information about inheritance, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>  
  
 <span data-ttu-id="2fef8-111">Non è possibile eseguire l'override di un metodo non virtuale o statico.</span><span class="sxs-lookup"><span data-stu-id="2fef8-111">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="2fef8-112">Il metodo di base sottoposto a override deve essere `virtual`, `abstract` o `override`.</span><span class="sxs-lookup"><span data-stu-id="2fef8-112">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>  
  
 <span data-ttu-id="2fef8-113">Una dichiarazione `override` non può modificare l'accessibilità del metodo `virtual`.</span><span class="sxs-lookup"><span data-stu-id="2fef8-113">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="2fef8-114">Il metodo `override` e il metodo `virtual` devono avere lo stesso [modificatore del livello di accesso](../../../csharp/language-reference/keywords/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="2fef8-114">Both the `override` method and the `virtual` method must have the same [access level modifier](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="2fef8-115">Non è possibile usare i modificatori `new`, `static` o `virtual` per modificare un metodo `override`.</span><span class="sxs-lookup"><span data-stu-id="2fef8-115">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>  
  
 <span data-ttu-id="2fef8-116">Una dichiarazione di proprietà di override deve indicare esattamente lo stesso modificatore di accesso, lo stesso tipo e lo stesso nome della proprietà ereditata e la proprietà sottoposta a override deve essere `virtual`, `abstract` o `override`.</span><span class="sxs-lookup"><span data-stu-id="2fef8-116">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property, and the overridden property must be `virtual`, `abstract`, or `override`.</span></span>  
  
 <span data-ttu-id="2fef8-117">Per altre informazioni sull'uso della parola chiave `override`, vedere [Controllo delle versioni con le parole chiave Override e New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) e [Sapere quando utilizzare le parole chiave Override e New](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="2fef8-117">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fef8-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="2fef8-118">Example</span></span>  
 <span data-ttu-id="2fef8-119">Questo esempio definisce una classe base denominata `Employee` e una classe derivata denominata `SalesEmployee`.</span><span class="sxs-lookup"><span data-stu-id="2fef8-119">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="2fef8-120">La classe `SalesEmployee` include la proprietà aggiuntiva `salesbonus` ed esegue l'override del metodo `CalculatePay` per prenderla in considerazione.</span><span class="sxs-lookup"><span data-stu-id="2fef8-120">The `SalesEmployee` class includes an extra property, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>  
  
 <span data-ttu-id="2fef8-121">[!code-cs[csrefKeywordsModifiers#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="2fef8-121">[!code-cs[csrefKeywordsModifiers#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="2fef8-122">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="2fef8-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2fef8-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2fef8-123">See Also</span></span>  
 <span data-ttu-id="2fef8-124">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="2fef8-124">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="2fef8-125">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2fef8-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="2fef8-126">[Ereditarietà](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span><span class="sxs-lookup"><span data-stu-id="2fef8-126">[Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span></span>  
 <span data-ttu-id="2fef8-127">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="2fef8-127">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="2fef8-128">[Modificatori](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="2fef8-128">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="2fef8-129">[abstract](../../../csharp/language-reference/keywords/abstract.md) </span><span class="sxs-lookup"><span data-stu-id="2fef8-129">[abstract](../../../csharp/language-reference/keywords/abstract.md) </span></span>  
 <span data-ttu-id="2fef8-130">[virtual](../../../csharp/language-reference/keywords/virtual.md) </span><span class="sxs-lookup"><span data-stu-id="2fef8-130">[virtual](../../../csharp/language-reference/keywords/virtual.md) </span></span>  
 <span data-ttu-id="2fef8-131">[new](../../../csharp/language-reference/keywords/new.md) </span><span class="sxs-lookup"><span data-stu-id="2fef8-131">[new](../../../csharp/language-reference/keywords/new.md) </span></span>  
 [<span data-ttu-id="2fef8-132">Polimorfismo</span><span class="sxs-lookup"><span data-stu-id="2fef8-132">Polymorphism</span></span>](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)


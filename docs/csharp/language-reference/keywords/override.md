---
title: override (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 8f692dfdf8bd34ddb62623d86ec3dadd2b8dead3
ms.sourcegitcommit: 2d8b7488d94101b534ca3e9780b1c1e840233405
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2018
ms.locfileid: "39199264"
---
# <a name="override-c-reference"></a><span data-ttu-id="4d33e-102">override (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="4d33e-102">override (C# Reference)</span></span>
<span data-ttu-id="4d33e-103">Il modificatore `override` è necessario per estendere o modificare l'implementazione astratta o virtuale di un metodo, una proprietà, un indicizzatore o un evento ereditato.</span><span class="sxs-lookup"><span data-stu-id="4d33e-103">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d33e-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="4d33e-104">Example</span></span>  
 <span data-ttu-id="4d33e-105">In questo esempio la classe `Square` deve specificare un'implementazione sottoposta a override di `Area` poiché `Area` viene ereditato da `ShapesClass` astratto:</span><span class="sxs-lookup"><span data-stu-id="4d33e-105">In this example, the `Square` class must provide an overridden implementation of `Area` because `Area` is inherited from the abstract `ShapesClass`:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_1.cs)]  
  
 <span data-ttu-id="4d33e-106">Un metodo `override` offre una nuova implementazione di un membro ereditato da una classe base.</span><span class="sxs-lookup"><span data-stu-id="4d33e-106">An `override` method provides a new implementation of a member that is inherited from a base class.</span></span> <span data-ttu-id="4d33e-107">Il metodo che viene sottoposto a override mediante una dichiarazione `override` viene definito metodo di base sottoposto a override.</span><span class="sxs-lookup"><span data-stu-id="4d33e-107">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="4d33e-108">Il metodo di base sottoposto a override deve avere la stessa firma del metodo `override`.</span><span class="sxs-lookup"><span data-stu-id="4d33e-108">The overridden base method must have the same signature as the `override` method.</span></span> <span data-ttu-id="4d33e-109">Per informazioni sull'ereditarietà, vedere [Ereditarietà](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="4d33e-109">For information about inheritance, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>  
  
 <span data-ttu-id="4d33e-110">Non è possibile eseguire l'override di un metodo non virtuale o statico.</span><span class="sxs-lookup"><span data-stu-id="4d33e-110">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="4d33e-111">Il metodo di base sottoposto a override deve essere `virtual`, `abstract` o `override`.</span><span class="sxs-lookup"><span data-stu-id="4d33e-111">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>  
  
 <span data-ttu-id="4d33e-112">Una dichiarazione `override` non può modificare l'accessibilità del metodo `virtual`.</span><span class="sxs-lookup"><span data-stu-id="4d33e-112">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="4d33e-113">Il metodo `override` e il metodo `virtual` devono avere lo stesso [modificatore del livello di accesso](../../../csharp/language-reference/keywords/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="4d33e-113">Both the `override` method and the `virtual` method must have the same [access level modifier](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="4d33e-114">Non è possibile usare i modificatori `new`, `static` o `virtual` per modificare un metodo `override`.</span><span class="sxs-lookup"><span data-stu-id="4d33e-114">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>  
  
 <span data-ttu-id="4d33e-115">Una dichiarazione di proprietà di override deve indicare esattamente lo stesso modificatore di accesso, lo stesso tipo e lo stesso nome della proprietà ereditata e la proprietà sottoposta a override deve essere `virtual`, `abstract` o `override`.</span><span class="sxs-lookup"><span data-stu-id="4d33e-115">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property, and the overridden property must be `virtual`, `abstract`, or `override`.</span></span>  
  
 <span data-ttu-id="4d33e-116">Per altre informazioni sull'uso della parola chiave `override`, vedere [Controllo delle versioni con le parole chiave Override e New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) e [Sapere quando utilizzare le parole chiave Override e New](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="4d33e-116">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d33e-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="4d33e-117">Example</span></span>  
 <span data-ttu-id="4d33e-118">Questo esempio definisce una classe base denominata `Employee` e una classe derivata denominata `SalesEmployee`.</span><span class="sxs-lookup"><span data-stu-id="4d33e-118">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="4d33e-119">La classe `SalesEmployee` include la proprietà aggiuntiva `salesbonus` ed esegue l'override del metodo `CalculatePay` per prenderla in considerazione.</span><span class="sxs-lookup"><span data-stu-id="4d33e-119">The `SalesEmployee` class includes an extra property, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="4d33e-120">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="4d33e-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4d33e-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d33e-121">See Also</span></span>  
 [<span data-ttu-id="4d33e-122">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="4d33e-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="4d33e-123">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="4d33e-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4d33e-124">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="4d33e-124">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)  
 [<span data-ttu-id="4d33e-125">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="4d33e-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="4d33e-126">Modificatori</span><span class="sxs-lookup"><span data-stu-id="4d33e-126">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="4d33e-127">abstract</span><span class="sxs-lookup"><span data-stu-id="4d33e-127">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)  
 [<span data-ttu-id="4d33e-128">virtual</span><span class="sxs-lookup"><span data-stu-id="4d33e-128">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)  
 [<span data-ttu-id="4d33e-129">new</span><span class="sxs-lookup"><span data-stu-id="4d33e-129">new</span></span>](../../../csharp/language-reference/keywords/new.md)  
 [<span data-ttu-id="4d33e-130">Polimorfismo</span><span class="sxs-lookup"><span data-stu-id="4d33e-130">Polymorphism</span></span>](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)

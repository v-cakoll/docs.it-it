---
title: Modificatore override - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: acad3aa3b196c184132ad1acdf52b18a799b0896
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713248"
---
# <a name="override-c-reference"></a><span data-ttu-id="0f49b-102">override (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="0f49b-102">override (C# Reference)</span></span>

<span data-ttu-id="0f49b-103">Il modificatore `override` è necessario per estendere o modificare l'implementazione astratta o virtuale di un metodo, una proprietà, un indicizzatore o un evento ereditato.</span><span class="sxs-lookup"><span data-stu-id="0f49b-103">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>

## <a name="example"></a><span data-ttu-id="0f49b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="0f49b-104">Example</span></span>

<span data-ttu-id="0f49b-105">In questo esempio, `Square` la classe deve `GetArea` fornire `GetArea` un'implementazione `Shape` sottoposta a override di perché viene ereditata dalla classe astratta:In this example, the class must provide an overridden implementation of because is inherited from the abstract class:</span><span class="sxs-lookup"><span data-stu-id="0f49b-105">In this example, the `Square` class must provide an overridden implementation of `GetArea` because `GetArea` is inherited from the abstract `Shape` class:</span></span>

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

<span data-ttu-id="0f49b-106">Un metodo `override` offre una nuova implementazione di un membro ereditato da una classe base.</span><span class="sxs-lookup"><span data-stu-id="0f49b-106">An `override` method provides a new implementation of a member that is inherited from a base class.</span></span> <span data-ttu-id="0f49b-107">Il metodo che viene sottoposto a override mediante una dichiarazione `override` viene definito metodo di base sottoposto a override.</span><span class="sxs-lookup"><span data-stu-id="0f49b-107">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="0f49b-108">Il metodo di base sottoposto a override deve avere la stessa firma del metodo `override`.</span><span class="sxs-lookup"><span data-stu-id="0f49b-108">The overridden base method must have the same signature as the `override` method.</span></span> <span data-ttu-id="0f49b-109">Per informazioni sull'ereditarietà, vedere [Ereditarietà](../../programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="0f49b-109">For information about inheritance, see [Inheritance](../../programming-guide/classes-and-structs/inheritance.md).</span></span>

<span data-ttu-id="0f49b-110">Non è possibile eseguire l'override di un metodo non virtuale o statico.</span><span class="sxs-lookup"><span data-stu-id="0f49b-110">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="0f49b-111">Il metodo di base sottoposto a override deve essere `virtual`, `abstract` o `override`.</span><span class="sxs-lookup"><span data-stu-id="0f49b-111">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="0f49b-112">Una dichiarazione `override` non può modificare l'accessibilità del metodo `virtual`.</span><span class="sxs-lookup"><span data-stu-id="0f49b-112">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="0f49b-113">Il metodo `override` e il metodo `virtual` devono avere lo stesso [modificatore del livello di accesso](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="0f49b-113">Both the `override` method and the `virtual` method must have the same [access level modifier](access-modifiers.md).</span></span>

<span data-ttu-id="0f49b-114">Non è possibile usare i modificatori `new`, `static` o `virtual` per modificare un metodo `override`.</span><span class="sxs-lookup"><span data-stu-id="0f49b-114">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>

<span data-ttu-id="0f49b-115">Una dichiarazione di proprietà di override deve indicare esattamente lo stesso modificatore di accesso, lo stesso tipo e lo stesso nome della proprietà ereditata e la proprietà sottoposta a override deve essere `virtual`, `abstract` o `override`.</span><span class="sxs-lookup"><span data-stu-id="0f49b-115">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property, and the overridden property must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="0f49b-116">Per altre informazioni sull'uso della parola chiave `override`, vedere [Controllo delle versioni con le parole chiave Override e New](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) e [Sapere quando utilizzare le parole chiave Override e New](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="0f49b-116">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>

## <a name="example"></a><span data-ttu-id="0f49b-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="0f49b-117">Example</span></span>

<span data-ttu-id="0f49b-118">Questo esempio definisce una classe base denominata `Employee` e una classe derivata denominata `SalesEmployee`.</span><span class="sxs-lookup"><span data-stu-id="0f49b-118">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="0f49b-119">La classe `SalesEmployee` include il campo aggiuntivo `salesbonus` ed esegue l'override del metodo `CalculatePay` per prenderlo in considerazione.</span><span class="sxs-lookup"><span data-stu-id="0f49b-119">The `SalesEmployee` class includes an extra field, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="0f49b-120">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="0f49b-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="0f49b-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f49b-121">See also</span></span>

- [<span data-ttu-id="0f49b-122">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="0f49b-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0f49b-123">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="0f49b-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0f49b-124">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="0f49b-124">Inheritance</span></span>](../../programming-guide/classes-and-structs/inheritance.md)
- [<span data-ttu-id="0f49b-125">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="0f49b-125">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="0f49b-126">Modificatori</span><span class="sxs-lookup"><span data-stu-id="0f49b-126">Modifiers</span></span>](index.md)
- [<span data-ttu-id="0f49b-127">astratto</span><span class="sxs-lookup"><span data-stu-id="0f49b-127">abstract</span></span>](abstract.md)
- [<span data-ttu-id="0f49b-128">Virtuale</span><span class="sxs-lookup"><span data-stu-id="0f49b-128">virtual</span></span>](virtual.md)
- [<span data-ttu-id="0f49b-129">new (modifier)</span><span class="sxs-lookup"><span data-stu-id="0f49b-129">new (modifier)</span></span>](new-modifier.md)
- [<span data-ttu-id="0f49b-130">Polimorfismo</span><span class="sxs-lookup"><span data-stu-id="0f49b-130">Polymorphism</span></span>](../../programming-guide/classes-and-structs/polymorphism.md)

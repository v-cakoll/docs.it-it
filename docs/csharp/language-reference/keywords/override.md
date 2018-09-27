---
title: Modificatore override (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: cbd5e21e7ca71a4986099a0386c684a6db37c3e8
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2018
ms.locfileid: "45591173"
---
# <a name="override-c-reference"></a><span data-ttu-id="cedcc-102">override (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="cedcc-102">override (C# Reference)</span></span>

<span data-ttu-id="cedcc-103">Il modificatore `override` è necessario per estendere o modificare l'implementazione astratta o virtuale di un metodo, una proprietà, un indicizzatore o un evento ereditato.</span><span class="sxs-lookup"><span data-stu-id="cedcc-103">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>

## <a name="example"></a><span data-ttu-id="cedcc-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="cedcc-104">Example</span></span>

<span data-ttu-id="cedcc-105">In questo esempio la classe `Square` deve specificare un'implementazione sottoposta a override di `Area` poiché `Area` viene ereditato da `ShapesClass` astratto:</span><span class="sxs-lookup"><span data-stu-id="cedcc-105">In this example, the `Square` class must provide an overridden implementation of `Area` because `Area` is inherited from the abstract `ShapesClass`:</span></span>

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

<span data-ttu-id="cedcc-106">Un metodo `override` offre una nuova implementazione di un membro ereditato da una classe base.</span><span class="sxs-lookup"><span data-stu-id="cedcc-106">An `override` method provides a new implementation of a member that is inherited from a base class.</span></span> <span data-ttu-id="cedcc-107">Il metodo che viene sottoposto a override mediante una dichiarazione `override` viene definito metodo di base sottoposto a override.</span><span class="sxs-lookup"><span data-stu-id="cedcc-107">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="cedcc-108">Il metodo di base sottoposto a override deve avere la stessa firma del metodo `override`.</span><span class="sxs-lookup"><span data-stu-id="cedcc-108">The overridden base method must have the same signature as the `override` method.</span></span> <span data-ttu-id="cedcc-109">Per informazioni sull'ereditarietà, vedere [Ereditarietà](../../programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="cedcc-109">For information about inheritance, see [Inheritance](../../programming-guide/classes-and-structs/inheritance.md).</span></span>

<span data-ttu-id="cedcc-110">Non è possibile eseguire l'override di un metodo non virtuale o statico.</span><span class="sxs-lookup"><span data-stu-id="cedcc-110">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="cedcc-111">Il metodo di base sottoposto a override deve essere `virtual`, `abstract` o `override`.</span><span class="sxs-lookup"><span data-stu-id="cedcc-111">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="cedcc-112">Una dichiarazione `override` non può modificare l'accessibilità del metodo `virtual`.</span><span class="sxs-lookup"><span data-stu-id="cedcc-112">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="cedcc-113">Il metodo `override` e il metodo `virtual` devono avere lo stesso [modificatore del livello di accesso](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="cedcc-113">Both the `override` method and the `virtual` method must have the same [access level modifier](access-modifiers.md).</span></span>

<span data-ttu-id="cedcc-114">Non è possibile usare i modificatori `new`, `static` o `virtual` per modificare un metodo `override`.</span><span class="sxs-lookup"><span data-stu-id="cedcc-114">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>

<span data-ttu-id="cedcc-115">Una dichiarazione di proprietà di override deve indicare esattamente lo stesso modificatore di accesso, lo stesso tipo e lo stesso nome della proprietà ereditata e la proprietà sottoposta a override deve essere `virtual`, `abstract` o `override`.</span><span class="sxs-lookup"><span data-stu-id="cedcc-115">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property, and the overridden property must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="cedcc-116">Per altre informazioni sull'uso della parola chiave `override`, vedere [Controllo delle versioni con le parole chiave Override e New](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) e [Sapere quando utilizzare le parole chiave Override e New](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="cedcc-116">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>

## <a name="example"></a><span data-ttu-id="cedcc-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="cedcc-117">Example</span></span>

<span data-ttu-id="cedcc-118">Questo esempio definisce una classe base denominata `Employee` e una classe derivata denominata `SalesEmployee`.</span><span class="sxs-lookup"><span data-stu-id="cedcc-118">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="cedcc-119">La classe `SalesEmployee` include il campo aggiuntivo `salesbonus` ed esegue l'override del metodo `CalculatePay` per prenderlo in considerazione.</span><span class="sxs-lookup"><span data-stu-id="cedcc-119">The `SalesEmployee` class includes an extra field, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="cedcc-120">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="cedcc-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="cedcc-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cedcc-121">See also</span></span>

- [<span data-ttu-id="cedcc-122">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="cedcc-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="cedcc-123">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="cedcc-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="cedcc-124">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="cedcc-124">Inheritance</span></span>](../../programming-guide/classes-and-structs/inheritance.md)
- [<span data-ttu-id="cedcc-125">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="cedcc-125">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="cedcc-126">Modificatori</span><span class="sxs-lookup"><span data-stu-id="cedcc-126">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="cedcc-127">abstract</span><span class="sxs-lookup"><span data-stu-id="cedcc-127">abstract</span></span>](abstract.md)
- [<span data-ttu-id="cedcc-128">virtual</span><span class="sxs-lookup"><span data-stu-id="cedcc-128">virtual</span></span>](virtual.md)
- [<span data-ttu-id="cedcc-129">new</span><span class="sxs-lookup"><span data-stu-id="cedcc-129">new</span></span>](new.md)
- [<span data-ttu-id="cedcc-130">Polimorfismo</span><span class="sxs-lookup"><span data-stu-id="cedcc-130">Polymorphism</span></span>](../../programming-guide/classes-and-structs/polymorphism.md)

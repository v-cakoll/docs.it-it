---
title: Modificatore sealed - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- sealed
- sealed_CSharpKeyword
helpviewer_keywords:
- sealed keyword [C#]
ms.assetid: 8e4ed5d3-10be-47db-9488-0da2008e6f3f
ms.openlocfilehash: 7b9551fe892b0335fb445ab9edce4facca0badbe
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833339"
---
# <a name="sealed-c-reference"></a><span data-ttu-id="71637-102">sealed (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="71637-102">sealed (C# Reference)</span></span>

<span data-ttu-id="71637-103">Quando applicato a una classe, il modificatore `sealed` impedisce che altre classi ereditino da esso.</span><span class="sxs-lookup"><span data-stu-id="71637-103">When applied to a class, the `sealed` modifier prevents other classes from inheriting from it.</span></span> <span data-ttu-id="71637-104">Nell'esempio seguente, la classe `B` eredita dalla classe `A`, ma nessuna classe può ereditare dalla classe `B`.</span><span class="sxs-lookup"><span data-stu-id="71637-104">In the following example, class `B` inherits from class `A`, but no class can inherit from class `B`.</span></span>

```csharp
class A {}
sealed class B : A {}
```

<span data-ttu-id="71637-105">È anche possibile usare il modificatore `sealed` su un metodo o su una proprietà che esegue l'override di un metodo o di una proprietà virtuale in una classe di base.</span><span class="sxs-lookup"><span data-stu-id="71637-105">You can also use the `sealed` modifier on a method or property that overrides a virtual method or property in a base class.</span></span> <span data-ttu-id="71637-106">In questo modo è possibile consentire alle classi di derivare dalla classe e impedire l'override di proprietà o metodi virtuali specifici.</span><span class="sxs-lookup"><span data-stu-id="71637-106">This enables you to allow classes to derive from your class and prevent them from overriding specific virtual methods or properties.</span></span>

## <a name="example"></a><span data-ttu-id="71637-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="71637-107">Example</span></span>

<span data-ttu-id="71637-108">Nell'esempio seguente, `Z` eredita da `Y` ma `Z` non può eseguire l'override della funzione virtuale `F` dichiarata in `X` e bloccata in `Y`.</span><span class="sxs-lookup"><span data-stu-id="71637-108">In the following example, `Z` inherits from `Y` but `Z` cannot override the virtual function `F` that is declared in `X` and sealed in `Y`.</span></span>

[!code-csharp[csrefKeywordsModifiers#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#16)]

<span data-ttu-id="71637-109">Quando si definiscono nuovi metodi o proprietà in una classe, è possibile impedire alle classi derivate di eseguire l'override non dichiarandole come [virtuali](virtual.md).</span><span class="sxs-lookup"><span data-stu-id="71637-109">When you define new methods or properties in a class, you can prevent deriving classes from overriding them by not declaring them as [virtual](virtual.md).</span></span>

<span data-ttu-id="71637-110">È un errore usare il modificatore [abstract](abstract.md) con una classe sealed, poiché la classe astratta deve essere ereditata da una classe che fornisce un'implementazione dei metodi o delle proprietà astratti.</span><span class="sxs-lookup"><span data-stu-id="71637-110">It is an error to use the [abstract](abstract.md) modifier with a sealed class, because an abstract class must be inherited by a class that provides an implementation of the abstract methods or properties.</span></span>

<span data-ttu-id="71637-111">Quando applicato a un metodo o a una proprietà, il modificatore `sealed` deve sempre essere usato con [override](override.md).</span><span class="sxs-lookup"><span data-stu-id="71637-111">When applied to a method or property, the `sealed` modifier must always be used with [override](override.md).</span></span>

<span data-ttu-id="71637-112">Poiché gli struct sono sealed in modo implicito, non possono essere ereditati.</span><span class="sxs-lookup"><span data-stu-id="71637-112">Because structs are implicitly sealed, they cannot be inherited.</span></span>

<span data-ttu-id="71637-113">Per altre informazioni, vedere [Ereditarietà](../../programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="71637-113">For more information, see [Inheritance](../../programming-guide/classes-and-structs/inheritance.md).</span></span>

<span data-ttu-id="71637-114">Per altri esempi, vedere [Classi e membri delle classi astratte e sealed](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="71637-114">For more examples, see [Abstract and Sealed Classes and Class Members](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>

## <a name="example"></a><span data-ttu-id="71637-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="71637-115">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#17)]

<span data-ttu-id="71637-116">Nell'esempio precedente è possibile ereditare dalla classe sealed tramite l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="71637-116">In the previous example, you might try to inherit from the sealed class by using the following statement:</span></span>

`class MyDerivedC: SealedClass {}   // Error`

<span data-ttu-id="71637-117">Il risultato è un messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="71637-117">The result is an error message:</span></span>

`'MyDerivedC': cannot derive from sealed type 'SealedClass'`

## <a name="remarks"></a><span data-ttu-id="71637-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="71637-118">Remarks</span></span>

<span data-ttu-id="71637-119">Per determinare se bloccare una classe, proprietà o metodo, è consigliabile in genere considerare i due punti seguenti:</span><span class="sxs-lookup"><span data-stu-id="71637-119">To determine whether to seal a class, method, or property, you should generally consider the following two points:</span></span>

- <span data-ttu-id="71637-120">I potenziali vantaggi di cui le classi derivate possono usufruire grazie alla possibilità di personalizzare la classe.</span><span class="sxs-lookup"><span data-stu-id="71637-120">The potential benefits that deriving classes might gain through the ability to customize your class.</span></span>

- <span data-ttu-id="71637-121">La possibilità che le classi derivate possono modificare le classi in uso in modo tale che non funzionino più correttamente o come previsto.</span><span class="sxs-lookup"><span data-stu-id="71637-121">The potential that deriving classes could modify your classes in such a way that they would no longer work correctly or as expected.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="71637-122">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="71637-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="71637-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71637-123">See also</span></span>

- [<span data-ttu-id="71637-124">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="71637-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="71637-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="71637-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="71637-126">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="71637-126">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="71637-127">Classi statiche e membri di classi statiche</span><span class="sxs-lookup"><span data-stu-id="71637-127">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
- [<span data-ttu-id="71637-128">Classi e membri delle classi astratte e sealed</span><span class="sxs-lookup"><span data-stu-id="71637-128">Abstract and Sealed Classes and Class Members</span></span>](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)
- [<span data-ttu-id="71637-129">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="71637-129">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="71637-130">Modificatori</span><span class="sxs-lookup"><span data-stu-id="71637-130">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="71637-131">override</span><span class="sxs-lookup"><span data-stu-id="71637-131">override</span></span>](override.md)
- [<span data-ttu-id="71637-132">virtual</span><span class="sxs-lookup"><span data-stu-id="71637-132">virtual</span></span>](virtual.md)

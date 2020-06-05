---
title: Override
ms.date: 07/20/2015
f1_keywords:
- Overrides
- vb.Overrides
helpviewer_keywords:
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- Overrides keyword [Visual Basic]
- overriding, Overrides keyword
- properties [Visual Basic], overriding
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
ms.openlocfilehash: 657f838b2959a5b6a7cef5ff18295a4ada709e9a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392028"
---
# <a name="overrides-visual-basic"></a><span data-ttu-id="7498e-102">Overrides (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7498e-102">Overrides (Visual Basic)</span></span>

<span data-ttu-id="7498e-103">Specifica che una proprietà o una routine esegue l'override di una proprietà o una routine con nome identico ereditata da una classe base.</span><span class="sxs-lookup"><span data-stu-id="7498e-103">Specifies that a property or procedure overrides an identically named property or procedure inherited from a base class.</span></span>

## <a name="rules"></a><span data-ttu-id="7498e-104">Regole</span><span class="sxs-lookup"><span data-stu-id="7498e-104">Rules</span></span>

- <span data-ttu-id="7498e-105">\*\*Contesto della dichiarazione. \*\*</span><span class="sxs-lookup"><span data-stu-id="7498e-105">**Declaration Context.**</span></span> <span data-ttu-id="7498e-106">È possibile utilizzare `Overrides` solo in un'istruzione di dichiarazione di proprietà o di routine.</span><span class="sxs-lookup"><span data-stu-id="7498e-106">You can use `Overrides` only in a property or procedure declaration statement.</span></span>

- <span data-ttu-id="7498e-107">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="7498e-107">**Combined Modifiers.**</span></span> <span data-ttu-id="7498e-108">Non è possibile specificare `Overrides` insieme a `Shadows` o `Shared` nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="7498e-108">You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration.</span></span> <span data-ttu-id="7498e-109">Poiché un elemento che esegue l'override può essere implicitamente sottoposto a override, non è possibile combinare `Overridable` e `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="7498e-109">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>

- <span data-ttu-id="7498e-110">**Firme corrispondenti.**</span><span class="sxs-lookup"><span data-stu-id="7498e-110">**Matching Signatures.**</span></span> <span data-ttu-id="7498e-111">La firma di questa dichiarazione deve corrispondere esattamente alla *firma* della proprietà o della routine sottoposta a override.</span><span class="sxs-lookup"><span data-stu-id="7498e-111">The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides.</span></span> <span data-ttu-id="7498e-112">In altre parole, gli elenchi di parametri devono presentare lo stesso numero di parametri, nel medesimo ordine, e contenere gli stessi tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="7498e-112">This means the parameter lists must have the same number of parameters, in the same order, with the same data types.</span></span>

  <span data-ttu-id="7498e-113">Oltre alla firma, la dichiarazione che esegue l'override deve anche corrispondere esattamente a quanto segue.</span><span class="sxs-lookup"><span data-stu-id="7498e-113">In addition to the signature, the overriding declaration must also exactly match the following:</span></span>

  - <span data-ttu-id="7498e-114">Livello di accesso</span><span class="sxs-lookup"><span data-stu-id="7498e-114">The access level</span></span>

  - <span data-ttu-id="7498e-115">Tipo restituito, se disponibile</span><span class="sxs-lookup"><span data-stu-id="7498e-115">The return type, if any</span></span>

- <span data-ttu-id="7498e-116">**Firme generiche.**</span><span class="sxs-lookup"><span data-stu-id="7498e-116">**Generic Signatures.**</span></span> <span data-ttu-id="7498e-117">Nel caso di una routine generica la firma include il numero di parametri del tipo.</span><span class="sxs-lookup"><span data-stu-id="7498e-117">For a generic procedure, the signature includes the number of type parameters.</span></span> <span data-ttu-id="7498e-118">La dichiarazione che esegue l'override, quindi, deve corrispondere alla versione della classe base anche in relazione a tali caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="7498e-118">Therefore, the overriding declaration must match the base class version in that respect as well.</span></span>

- <span data-ttu-id="7498e-119">**Corrispondenze aggiuntive.**</span><span class="sxs-lookup"><span data-stu-id="7498e-119">**Additional Matching.**</span></span> <span data-ttu-id="7498e-120">Oltre a corrispondere alla firma della versione della classe base, la dichiarazione deve presentare anche le corrispondenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="7498e-120">In addition to matching the signature of the base class version, this declaration must also match it in the following respects:</span></span>

  - <span data-ttu-id="7498e-121">Modificatore a livello di accesso (ad esempio [public](public.md))</span><span class="sxs-lookup"><span data-stu-id="7498e-121">Access-level modifier (such as [Public](public.md))</span></span>

  - <span data-ttu-id="7498e-122">Passaggio del meccanismo di ogni parametro ([ByVal](byval.md) o [ByRef](byref.md))</span><span class="sxs-lookup"><span data-stu-id="7498e-122">Passing mechanism of each parameter ([ByVal](byval.md) or [ByRef](byref.md))</span></span>

  - <span data-ttu-id="7498e-123">Elenchi di vincoli su ogni parametro di tipo di una routine generica</span><span class="sxs-lookup"><span data-stu-id="7498e-123">Constraint lists on each type parameter of a generic procedure</span></span>

- <span data-ttu-id="7498e-124">**Shadowing e override.**</span><span class="sxs-lookup"><span data-stu-id="7498e-124">**Shadowing and Overriding.**</span></span> <span data-ttu-id="7498e-125">Sebbene lo shadowing e l'override ridefiniscano entrambi un elemento ereditato, tra i due metodi esistono differenze sostanziali.</span><span class="sxs-lookup"><span data-stu-id="7498e-125">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="7498e-126">Per ulteriori informazioni, vedere [shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="7498e-126">For more information, see [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span></span>

<span data-ttu-id="7498e-127">Se si usa `Overrides`, il compilatore aggiunge implicitamente `Overloads` in modo che le API della libreria funzionino più facilmente con C#.</span><span class="sxs-lookup"><span data-stu-id="7498e-127">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>

<span data-ttu-id="7498e-128">Il modificatore `Overrides` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7498e-128">The `Overrides` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="7498e-129">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="7498e-129">Function Statement</span></span>](../statements/function-statement.md)

- [<span data-ttu-id="7498e-130">Property Statement</span><span class="sxs-lookup"><span data-stu-id="7498e-130">Property Statement</span></span>](../statements/property-statement.md)

- [<span data-ttu-id="7498e-131">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="7498e-131">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="7498e-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7498e-132">See also</span></span>

- [<span data-ttu-id="7498e-133">MustOverride</span><span class="sxs-lookup"><span data-stu-id="7498e-133">MustOverride</span></span>](mustoverride.md)
- [<span data-ttu-id="7498e-134">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="7498e-134">NotOverridable</span></span>](notoverridable.md)
- [<span data-ttu-id="7498e-135">Overridable</span><span class="sxs-lookup"><span data-stu-id="7498e-135">Overridable</span></span>](overridable.md)
- [<span data-ttu-id="7498e-136">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7498e-136">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="7498e-137">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7498e-137">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="7498e-138">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7498e-138">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="7498e-139">Type List</span><span class="sxs-lookup"><span data-stu-id="7498e-139">Type List</span></span>](../statements/type-list.md)

---
title: Classi astratte (F#)
description: 'Informazioni su F # classi astratte, in cui alcuni o tutti i membri non implementata e rappresentano una funzionalità comune di un set di tipi di oggetto.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 0d7ca996de89c44a5cfb9197c1b515741a2303df
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="abstract-classes"></a><span data-ttu-id="e7fef-103">Classi astratte</span><span class="sxs-lookup"><span data-stu-id="e7fef-103">Abstract Classes</span></span>

<span data-ttu-id="e7fef-104">*Classi astratte* sono classi in cui alcuni o tutti i membri non implementati, in modo che le implementazioni possono essere fornite dalle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="e7fef-104">*Abstract classes* are classes that leave some or all members unimplemented, so that implementations can be provided by derived classes.</span></span>

## <a name="syntax"></a><span data-ttu-id="e7fef-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7fef-105">Syntax</span></span>

```fsharp
// Abstract class syntax.
[<AbstractClass>]
type [ accessibility-modifier ] abstract-class-name =
[ inherit base-class-or-interface-name ]
[ abstract-member-declarations-and-member-definitions ]

// Abstract member syntax.
abstract member member-name : type-signature
```

## <a name="remarks"></a><span data-ttu-id="e7fef-106">Note</span><span class="sxs-lookup"><span data-stu-id="e7fef-106">Remarks</span></span>
<span data-ttu-id="e7fef-107">Nella programmazione orientata agli oggetti, una classe astratta viene utilizzata come classe di base di una gerarchia e rappresenta la funzionalità comune di un set di tipi di oggetto.</span><span class="sxs-lookup"><span data-stu-id="e7fef-107">In object-oriented programming, an abstract class is used as a base class of a hierarchy, and represents common functionality of a diverse set of object types.</span></span> <span data-ttu-id="e7fef-108">Come suggerito dal nome "classe", classi astratte spesso non corrispondono direttamente a entità concrete nel dominio del problema.</span><span class="sxs-lookup"><span data-stu-id="e7fef-108">As the name "abstract" implies, abstract classes often do not correspond directly onto concrete entities in the problem domain.</span></span> <span data-ttu-id="e7fef-109">Tuttavia, che rappresentano le numerose entità concrete diverse hanno in comune.</span><span class="sxs-lookup"><span data-stu-id="e7fef-109">However, they do represent what many different concrete entities have in common.</span></span>

<span data-ttu-id="e7fef-110">Le classi astratte devono avere la `AbstractClass` attributo.</span><span class="sxs-lookup"><span data-stu-id="e7fef-110">Abstract classes must have the `AbstractClass` attribute.</span></span> <span data-ttu-id="e7fef-111">Possono avere implementato e i membri di non implementata.</span><span class="sxs-lookup"><span data-stu-id="e7fef-111">They can have implemented and unimplemented members.</span></span> <span data-ttu-id="e7fef-112">L'utilizzo del termine *astratta* quando applicato a una classe è uguale a quello di altri linguaggi .NET; tuttavia, l'utilizzo del termine *astratta* quando applicata a (metodi e proprietà) è leggermente diverso in F # da relativo utilizzare in altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="e7fef-112">The use of the term *abstract* when applied to a class is the same as in other .NET languages; however, the use of the term *abstract* when applied to methods (and properties) is a little different in F# from its use in other .NET languages.</span></span> <span data-ttu-id="e7fef-113">In F #, quando un metodo è contrassegnato con il `abstract` (parola chiave), significa che un membro dispone di una voce, nota come un *slot di invio virtuale*, nella tabella interna di funzioni virtuali per quel tipo.</span><span class="sxs-lookup"><span data-stu-id="e7fef-113">In F#, when a method is marked with the `abstract` keyword, this indicates that a member has an entry, known as a *virtual dispatch slot*, in the internal table of virtual functions for that type.</span></span> <span data-ttu-id="e7fef-114">In altre parole, il metodo è virtuale, anche se il `virtual` parola chiave non viene usato nel linguaggio F #.</span><span class="sxs-lookup"><span data-stu-id="e7fef-114">In other words, the method is virtual, although the `virtual` keyword is not used in the F# language.</span></span> <span data-ttu-id="e7fef-115">La parola chiave `abstract` viene usato nei metodi virtuali, indipendentemente dal fatto che il metodo è implementato.</span><span class="sxs-lookup"><span data-stu-id="e7fef-115">The keyword `abstract` is used on virtual methods regardless of whether the method is implemented.</span></span> <span data-ttu-id="e7fef-116">La dichiarazione di uno slot di distribuzione virtuale è separata dalla definizione di un metodo per tale slot di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e7fef-116">The declaration of a virtual dispatch slot is separate from the definition of a method for that dispatch slot.</span></span> <span data-ttu-id="e7fef-117">Pertanto, l'equivalente di una dichiarazione di metodo virtuale e la definizione di un altro linguaggio .NET F # è una combinazione di una dichiarazione di metodo astratto e una definizione separata, con la `default` parola chiave o `override` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="e7fef-117">Therefore, the F# equivalent of a virtual method declaration and definition in another .NET language is a combination of both an abstract method declaration and a separate definition, with either the `default` keyword or the `override` keyword.</span></span> <span data-ttu-id="e7fef-118">Per ulteriori informazioni ed esempi, vedere [metodi](members/methods.md).</span><span class="sxs-lookup"><span data-stu-id="e7fef-118">For more information and examples, see [Methods](members/methods.md).</span></span>

<span data-ttu-id="e7fef-119">Una classe è considerata astratta solo se esistono metodi astratti dichiarati, ma non è definiti.</span><span class="sxs-lookup"><span data-stu-id="e7fef-119">A class is considered abstract only if there are abstract methods that are declared but not defined.</span></span> <span data-ttu-id="e7fef-120">Pertanto, le classi che dispongono di metodi astratti non sono necessariamente classi astratte.</span><span class="sxs-lookup"><span data-stu-id="e7fef-120">Therefore, classes that have abstract methods are not necessarily abstract classes.</span></span> <span data-ttu-id="e7fef-121">A meno che una classe ha definito i metodi astratti, non utilizzare il **AbstractClass** attributo.</span><span class="sxs-lookup"><span data-stu-id="e7fef-121">Unless a class has undefined abstract methods, do not use the **AbstractClass** attribute.</span></span>

<span data-ttu-id="e7fef-122">Nella sintassi precedente, *modificatore di accessibilità* può essere `public`, `private` o `internal`.</span><span class="sxs-lookup"><span data-stu-id="e7fef-122">In the previous syntax, *accessibility-modifier* can be `public`, `private` or `internal`.</span></span> <span data-ttu-id="e7fef-123">Per altre informazioni, vedere [Controllo di accesso](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="e7fef-123">For more information, see [Access Control](access-control.md).</span></span>

<span data-ttu-id="e7fef-124">Come con altri tipi, classi astratte possono avere una classe di base e uno o più interfacce di base.</span><span class="sxs-lookup"><span data-stu-id="e7fef-124">As with other types, abstract classes can have a base class and one or more base interfaces.</span></span> <span data-ttu-id="e7fef-125">Ogni classe di base o interfaccia, viene visualizzato in una riga separata, insieme con il `inherit` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="e7fef-125">Each base class or interface appears on a separate line together with the `inherit` keyword.</span></span>

<span data-ttu-id="e7fef-126">La definizione del tipo di una classe astratta può contenere membri completamente definiti, ma può anche contenere membri astratti.</span><span class="sxs-lookup"><span data-stu-id="e7fef-126">The type definition of an abstract class can contain fully defined members, but it can also contain abstract members.</span></span> <span data-ttu-id="e7fef-127">La sintassi per i membri astratti viene visualizzata separatamente nella sintassi precedente.</span><span class="sxs-lookup"><span data-stu-id="e7fef-127">The syntax for abstract members is shown separately in the previous syntax.</span></span> <span data-ttu-id="e7fef-128">In questa sintassi, il *la firma del tipo* di un membro è un elenco che contiene i tipi di parametro in ordine e i tipi restituiti, separato da `->` token e/o `*` token come appropriato per sottoposte a currying e tupla parametri.</span><span class="sxs-lookup"><span data-stu-id="e7fef-128">In this syntax, the *type signature* of a member is a list that contains the parameter types in order and the return types, separated by `->` tokens and/or `*` tokens as appropriate for curried and tupled parameters.</span></span> <span data-ttu-id="e7fef-129">La sintassi per le firme del tipo di membro astratto è quello utilizzato nel file di firma e visualizzata da IntelliSense nell'Editor di codice di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e7fef-129">The syntax for abstract member type signatures is the same as that used in signature files and that shown by IntelliSense in the Visual Studio Code Editor.</span></span>

<span data-ttu-id="e7fef-130">Il codice seguente viene illustrata una classe astratta, forma, che dispone di due classi non astratte derivate, Square e Circle.</span><span class="sxs-lookup"><span data-stu-id="e7fef-130">The following code illustrates an abstract class Shape, which has two non-abstract derived classes, Square and Circle.</span></span> <span data-ttu-id="e7fef-131">Nell'esempio viene illustrato come utilizzare le proprietà, metodi e classi astratte.</span><span class="sxs-lookup"><span data-stu-id="e7fef-131">The example shows how to use abstract classes, methods, and properties.</span></span> <span data-ttu-id="e7fef-132">Nell'esempio, la forma della classe astratta rappresenta gli elementi comuni delle entità concrete circle e square.</span><span class="sxs-lookup"><span data-stu-id="e7fef-132">In the example, the abstract class Shape represents the common elements of the concrete entities circle and square.</span></span> <span data-ttu-id="e7fef-133">Le funzionalità comuni di tutte le forme (in un sistema di coordinate bidimensionale) vengono estratte nella classe Shape: la posizione nella griglia, l'angolo di rotazione e le proprietà di area e il perimetro.</span><span class="sxs-lookup"><span data-stu-id="e7fef-133">The common features of all shapes (in a two-dimensional coordinate system) are abstracted out into the Shape class: the position on the grid, an angle of rotation, and the area and perimeter properties.</span></span> <span data-ttu-id="e7fef-134">Questi può essere sottoposto a override, ad eccezione di posizione, il comportamento di cui non è possibile modificare le singole forme.</span><span class="sxs-lookup"><span data-stu-id="e7fef-134">These can be overridden, except for position, the behavior of which individual shapes cannot change.</span></span>

<span data-ttu-id="e7fef-135">Il metodo di rotazione può essere sottoposto a override, come la classe di cerchio, che è invariante rispetto alla rotazione a causa della sua simmetria.</span><span class="sxs-lookup"><span data-stu-id="e7fef-135">The rotation method can be overridden, as in the Circle class, which is rotation invariant because of its symmetry.</span></span> <span data-ttu-id="e7fef-136">Nella classe Circle, pertanto il metodo di rotazione viene sostituito da un metodo che non esegue alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="e7fef-136">So in the Circle class, the rotation method is replaced by a method that does nothing.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

<span data-ttu-id="e7fef-137">**Output:**</span><span class="sxs-lookup"><span data-stu-id="e7fef-137">**Output:**</span></span>

```
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a><span data-ttu-id="e7fef-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7fef-138">See Also</span></span>
[<span data-ttu-id="e7fef-139">Classi</span><span class="sxs-lookup"><span data-stu-id="e7fef-139">Classes</span></span>](classes.md)

[<span data-ttu-id="e7fef-140">Membri</span><span class="sxs-lookup"><span data-stu-id="e7fef-140">Members</span></span>](members/index.md)

[<span data-ttu-id="e7fef-141">Metodi</span><span class="sxs-lookup"><span data-stu-id="e7fef-141">Methods</span></span>](members/methods.md)

[<span data-ttu-id="e7fef-142">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e7fef-142">Properties</span></span>](members/Properties.md)

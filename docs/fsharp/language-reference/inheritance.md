---
title: Ereditarietà (C#)
description: "Informazioni su come specificare relazioni di ereditarietà F # usando la parola chiave 'inherit'."
ms.date: 05/16/2016
ms.openlocfilehash: e4d79244fb9bada5db0c5c4c7179d4bfe6e21f3d
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "43864469"
---
# <a name="inheritance"></a><span data-ttu-id="1efba-103">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="1efba-103">Inheritance</span></span>

<span data-ttu-id="1efba-104">Ereditarietà viene usata per modellare la relazione "is-a", o definizione dei sottotipi nella programmazione orientata agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="1efba-104">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>

## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="1efba-105">Specifica di relazioni di ereditarietà</span><span class="sxs-lookup"><span data-stu-id="1efba-105">Specifying Inheritance Relationships</span></span>

<span data-ttu-id="1efba-106">Specificare le relazioni di ereditarietà utilizzando la `inherit` parola chiave in una dichiarazione di classe.</span><span class="sxs-lookup"><span data-stu-id="1efba-106">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="1efba-107">La forma sintattica di base è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="1efba-107">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="1efba-108">Una classe può avere al massimo una classe base diretta.</span><span class="sxs-lookup"><span data-stu-id="1efba-108">A class can have at most one direct base class.</span></span> <span data-ttu-id="1efba-109">Se non si specifica una classe di base usando la `inherit` parola chiave, la classe eredita in modo implicito da `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="1efba-109">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>

## <a name="inherited-members"></a><span data-ttu-id="1efba-110">Membri ereditati</span><span class="sxs-lookup"><span data-stu-id="1efba-110">Inherited Members</span></span>

<span data-ttu-id="1efba-111">Se una classe eredita da un'altra classe, i metodi e membri della classe di base sono disponibili per gli utenti della classe derivata come se fossero membri diretti della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="1efba-111">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="1efba-112">Le associazioni let e i parametri del costruttore sono privati per una classe e, pertanto, non sono accessibile dalle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="1efba-112">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="1efba-113">La parola chiave `base` è disponibile nelle classi derivate e fa riferimento all'istanza della classe base.</span><span class="sxs-lookup"><span data-stu-id="1efba-113">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="1efba-114">Viene usato come identificatore Self-Service.</span><span class="sxs-lookup"><span data-stu-id="1efba-114">It is used like the self-identifier.</span></span>

## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="1efba-115">Le sostituzioni e metodi virtuali</span><span class="sxs-lookup"><span data-stu-id="1efba-115">Virtual Methods and Overrides</span></span>

<span data-ttu-id="1efba-116">Metodi virtuali (e proprietà) funzionano in modo diverso in F # rispetto a altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="1efba-116">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="1efba-117">Per dichiarare un nuovo membro virtuale, Usa il `abstract` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="1efba-117">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="1efba-118">A tale scopo, indipendentemente dal fatto che è fornire un'implementazione predefinita per il metodo.</span><span class="sxs-lookup"><span data-stu-id="1efba-118">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="1efba-119">In questo modo una definizione completa di un metodo virtuale in una classe di base segue questo modello:</span><span class="sxs-lookup"><span data-stu-id="1efba-119">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="1efba-120">E in una classe derivata, un override di questo metodo virtuale segue questo modello:</span><span class="sxs-lookup"><span data-stu-id="1efba-120">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="1efba-121">Se si omette l'implementazione predefinita della classe base, la classe di base diventa una classe astratta.</span><span class="sxs-lookup"><span data-stu-id="1efba-121">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="1efba-122">L'esempio di codice seguente illustra la dichiarazione di un nuovo metodo virtuale `function1` in una classe di base e su come eseguirne l'override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="1efba-122">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a><span data-ttu-id="1efba-123">Costruttori ed ereditarietà</span><span class="sxs-lookup"><span data-stu-id="1efba-123">Constructors and Inheritance</span></span>

<span data-ttu-id="1efba-124">Il costruttore per la classe di base deve essere chiamato nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="1efba-124">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="1efba-125">Gli argomenti per il costruttore di classe di base vengono visualizzati nell'elenco di argomenti in di `inherit` clausola.</span><span class="sxs-lookup"><span data-stu-id="1efba-125">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="1efba-126">I valori utilizzati devono essere determinati dagli argomenti forniti al costruttore della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="1efba-126">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="1efba-127">Il codice seguente illustra una classe di base e una classe derivata, in cui la classe derivata chiama il costruttore di classe di base nella clausola eredita:</span><span class="sxs-lookup"><span data-stu-id="1efba-127">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="1efba-128">Nel caso di più costruttori, il codice seguente può essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="1efba-128">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="1efba-129">La prima riga dei costruttori di classe derivata è il `inherit` clausola e i campi vengono visualizzati come campi espliciti che vengono dichiarati con la `val` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="1efba-129">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="1efba-130">Per altre informazioni, vedere [i campi espliciti: il `val` parola chiave](members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="1efba-130">For more information, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

```fsharp
type BaseClass =
    val string1 : string
    new (str) = { string1 = str }
    new () = { string1 = "" }

type DerivedClass =
    inherit BaseClass

    val string2 : string
    new (str1, str2) = { inherit BaseClass(str1); string2 = str2 }
    new (str2) = { inherit BaseClass(); string2 = str2 }

let obj1 = DerivedClass("A", "B")
let obj2 = DerivedClass("A")
```

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="1efba-131">Alternative all'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="1efba-131">Alternatives to Inheritance</span></span>

<span data-ttu-id="1efba-132">Nei casi in cui è necessaria una modifica secondaria di un tipo, è consigliabile usare un'espressione di oggetto come un'alternativa all'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="1efba-132">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="1efba-133">Nell'esempio seguente viene illustrato l'utilizzo di un'espressione di oggetto come alternativa alla creazione di un nuovo tipo derivato:</span><span class="sxs-lookup"><span data-stu-id="1efba-133">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="1efba-134">Per altre informazioni sulle espressioni di oggetto, vedere [espressioni di oggetto](object-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="1efba-134">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="1efba-135">Quando si siano creando gerarchie di oggetti, utilizzare un'unione discriminata invece dell'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="1efba-135">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="1efba-136">Le unioni discriminate possono anche comportamento del modello consentono di variare di diversi oggetti che condividono un tipo globale comune.</span><span class="sxs-lookup"><span data-stu-id="1efba-136">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="1efba-137">Un'unione discriminata singola spesso possa eliminare la necessità di un numero di classi derivate che si lievi variazioni tra loro.</span><span class="sxs-lookup"><span data-stu-id="1efba-137">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="1efba-138">Per informazioni sulle unioni discriminate, vedere [unioni discriminate](discriminated-unions.md).</span><span class="sxs-lookup"><span data-stu-id="1efba-138">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1efba-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1efba-139">See also</span></span>

- [<span data-ttu-id="1efba-140">Espressioni di oggetto</span><span class="sxs-lookup"><span data-stu-id="1efba-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="1efba-141">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="1efba-141">F# Language Reference</span></span>](index.md)

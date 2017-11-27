---
title: "Ereditarietà (C#)"
description: "Informazioni su come specificare relazioni di ereditarietà F # utilizzando la parola chiave 'inherit'."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b38ab2f6-7ba7-4839-8eff-e6bd6cfd2b2f
ms.openlocfilehash: 331c8f4e39aacd9d5e55bfbaf584f037e58d36a1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="inheritance"></a><span data-ttu-id="4fd43-104">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="4fd43-104">Inheritance</span></span>

<span data-ttu-id="4fd43-105">Ereditarietà viene utilizzata per modellare la relazione "è-a", o definizione di sottotipo, nella programmazione orientata a oggetti.</span><span class="sxs-lookup"><span data-stu-id="4fd43-105">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>


## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="4fd43-106">Specificare le relazioni di ereditarietà</span><span class="sxs-lookup"><span data-stu-id="4fd43-106">Specifying Inheritance Relationships</span></span>
<span data-ttu-id="4fd43-107">Specificare le relazioni di ereditarietà utilizzando il `inherit` parola chiave in una dichiarazione di classe.</span><span class="sxs-lookup"><span data-stu-id="4fd43-107">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="4fd43-108">Il formato di sintassi di base è illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4fd43-108">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="4fd43-109">Una classe può avere al massimo una classe base diretta.</span><span class="sxs-lookup"><span data-stu-id="4fd43-109">A class can have at most one direct base class.</span></span> <span data-ttu-id="4fd43-110">Se non si specifica una classe di base utilizzando il `inherit` (parola chiave), la classe eredita in modo implicito da `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="4fd43-110">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>


## <a name="inherited-members"></a><span data-ttu-id="4fd43-111">Membri ereditati</span><span class="sxs-lookup"><span data-stu-id="4fd43-111">Inherited Members</span></span>
<span data-ttu-id="4fd43-112">Se una classe eredita da un'altra classe, i metodi e membri della classe di base sono disponibili per gli utenti della classe derivata, come se fossero membri diretti della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="4fd43-112">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="4fd43-113">Le associazioni let e i parametri del costruttore sono privati per una classe e, pertanto, non è possibile accedere dalle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="4fd43-113">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="4fd43-114">La parola chiave `base` è disponibile nelle classi derivate e fa riferimento all'istanza della classe base.</span><span class="sxs-lookup"><span data-stu-id="4fd43-114">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="4fd43-115">Viene utilizzato come identificatore Self-Service.</span><span class="sxs-lookup"><span data-stu-id="4fd43-115">It is used like the self-identifier.</span></span>


## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="4fd43-116">Metodi virtuali e override</span><span class="sxs-lookup"><span data-stu-id="4fd43-116">Virtual Methods and Overrides</span></span>
<span data-ttu-id="4fd43-117">Metodi virtuali (e proprietà) funzionano in modo diverso in F # rispetto ai linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="4fd43-117">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="4fd43-118">Per dichiarare un nuovo membro virtuale, utilizzare il `abstract` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="4fd43-118">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="4fd43-119">A tale scopo, indipendentemente dal fatto che venga fornita un'implementazione predefinita per tale metodo.</span><span class="sxs-lookup"><span data-stu-id="4fd43-119">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="4fd43-120">In questo modo una definizione completa di un metodo virtuale in una classe base segue questo modello:</span><span class="sxs-lookup"><span data-stu-id="4fd43-120">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="4fd43-121">E in una classe derivata, un override di questo metodo virtuale segue questo modello:</span><span class="sxs-lookup"><span data-stu-id="4fd43-121">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="4fd43-122">Se si omette l'implementazione predefinita della classe base, la classe di base diventa una classe astratta.</span><span class="sxs-lookup"><span data-stu-id="4fd43-122">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="4fd43-123">L'esempio di codice seguente illustra la dichiarazione di un nuovo metodo virtuale `function1` in una classe di base e come eseguirne l'override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="4fd43-123">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]
    
## <a name="constructors-and-inheritance"></a><span data-ttu-id="4fd43-124">Costruttori ed ereditarietà</span><span class="sxs-lookup"><span data-stu-id="4fd43-124">Constructors and Inheritance</span></span>
<span data-ttu-id="4fd43-125">Il costruttore per la classe di base deve essere chiamato nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="4fd43-125">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="4fd43-126">Gli argomenti del costruttore di classe di base sono visualizzati nell'elenco di argomenti in di `inherit` clausola.</span><span class="sxs-lookup"><span data-stu-id="4fd43-126">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="4fd43-127">I valori utilizzati devono essere determinati in base agli argomenti forniti al costruttore della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="4fd43-127">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="4fd43-128">Il codice seguente illustra una classe di base e una classe derivata, in cui la classe derivata chiama il costruttore di classe di base nella clausola inherit:</span><span class="sxs-lookup"><span data-stu-id="4fd43-128">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="4fd43-129">Nel caso di più costruttori, è possibile utilizzare il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="4fd43-129">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="4fd43-130">È la prima riga dei costruttori di classe derivata di `inherit` clausola e i campi vengono visualizzati come campi espliciti dichiarati con la `val` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="4fd43-130">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="4fd43-131">Per ulteriori informazioni, vedere [campi espliciti: il `val` parola chiave](members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="4fd43-131">For more information, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

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

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="4fd43-132">Alternative all'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="4fd43-132">Alternatives to Inheritance</span></span>
<span data-ttu-id="4fd43-133">Nei casi in cui una piccola modifica di un tipo è obbligatoria, considerare l'uso di un'espressione di oggetto come alternativa all'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="4fd43-133">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="4fd43-134">Nell'esempio seguente viene illustrato l'utilizzo di un'espressione di oggetto come alternativa alla creazione di un nuovo tipo derivato:</span><span class="sxs-lookup"><span data-stu-id="4fd43-134">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="4fd43-135">Per ulteriori informazioni sulle espressioni di oggetto, vedere [espressioni di oggetto](object-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="4fd43-135">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="4fd43-136">Durante la creazione di gerarchie di oggetti, considerare l'utilizzo di un'unione discriminata invece dell'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="4fd43-136">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="4fd43-137">Unioni discriminate possono modellare variato comportamenti di oggetti diversi che condividono un tipo globale comune.</span><span class="sxs-lookup"><span data-stu-id="4fd43-137">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="4fd43-138">Una singola unione discriminata consente spesso di eliminare la necessità di un numero di classi derivate che sono alcune piccole variazioni di altra.</span><span class="sxs-lookup"><span data-stu-id="4fd43-138">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="4fd43-139">Per informazioni sulle unioni discriminate, vedere [unioni discriminate](discriminated-unions.md).</span><span class="sxs-lookup"><span data-stu-id="4fd43-139">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="4fd43-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4fd43-140">See Also</span></span>
[<span data-ttu-id="4fd43-141">Espressioni di oggetto</span><span class="sxs-lookup"><span data-stu-id="4fd43-141">Object Expressions</span></span>](object-expressions.md)

[<span data-ttu-id="4fd43-142">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="4fd43-142">F# Language Reference</span></span>](index.md)

---
title: Ereditarietà
description: Informazioni su come specificare le relazioni di ereditarietà di F, usando la parola chiave 'inherit'.
ms.date: 05/16/2016
ms.openlocfilehash: 5ab891a93528427a66e4eb8f7bfeccbf6e4d2c7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400288"
---
# <a name="inheritance"></a><span data-ttu-id="db3f6-103">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="db3f6-103">Inheritance</span></span>

<span data-ttu-id="db3f6-104">L'ereditarietà viene utilizzata per modellare la relazione "è-a", o sottotipi, nella programmazione orientata agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="db3f6-104">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>

## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="db3f6-105">Specifica delle relazioni di ereditarietàSpecifying Inheritance Relationships</span><span class="sxs-lookup"><span data-stu-id="db3f6-105">Specifying Inheritance Relationships</span></span>

<span data-ttu-id="db3f6-106">È possibile specificare `inherit` le relazioni di ereditarietà utilizzando la parola chiave in una dichiarazione di classe.</span><span class="sxs-lookup"><span data-stu-id="db3f6-106">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="db3f6-107">La forma sintattica di base è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="db3f6-107">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="db3f6-108">Una classe può avere al massimo una classe base diretta.</span><span class="sxs-lookup"><span data-stu-id="db3f6-108">A class can have at most one direct base class.</span></span> <span data-ttu-id="db3f6-109">Se non si specifica una classe `inherit` base utilizzando la parola `System.Object`chiave , la classe eredita in modo implicito da .</span><span class="sxs-lookup"><span data-stu-id="db3f6-109">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>

## <a name="inherited-members"></a><span data-ttu-id="db3f6-110">Membri ereditati</span><span class="sxs-lookup"><span data-stu-id="db3f6-110">Inherited Members</span></span>

<span data-ttu-id="db3f6-111">Se una classe eredita da un'altra classe, i metodi e i membri della classe base sono disponibili per gli utenti della classe derivata come se fossero membri diretti della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="db3f6-111">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="db3f6-112">Le associazioni let e i parametri del costruttore sono privati per una classe e, pertanto, non sono accessibili dalle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="db3f6-112">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="db3f6-113">La `base` parola chiave è disponibile nelle classi derivate e fa riferimento all'istanza della classe base.</span><span class="sxs-lookup"><span data-stu-id="db3f6-113">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="db3f6-114">Viene utilizzato come l'autoidentificatore.</span><span class="sxs-lookup"><span data-stu-id="db3f6-114">It is used like the self-identifier.</span></span>

## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="db3f6-115">Metodi virtuali ed overrideVirtual Methods and Overrides</span><span class="sxs-lookup"><span data-stu-id="db3f6-115">Virtual Methods and Overrides</span></span>

<span data-ttu-id="db3f6-116">I metodi virtuali (e le proprietà) funzionano in modo leggermente diverso in F , rispetto ad altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="db3f6-116">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="db3f6-117">Per dichiarare un nuovo membro `abstract` virtuale, utilizzare la parola chiave .</span><span class="sxs-lookup"><span data-stu-id="db3f6-117">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="db3f6-118">Questa operazione viene estratta indipendentemente dal fatto che si fornisca un'implementazione predefinita per tale metodo.</span><span class="sxs-lookup"><span data-stu-id="db3f6-118">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="db3f6-119">Pertanto, una definizione completa di un metodo virtuale in una classe base segue questo modello:Thus a complete definition of a virtual method in a base class follows this pattern:</span><span class="sxs-lookup"><span data-stu-id="db3f6-119">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="db3f6-120">E in una classe derivata, un override di questo metodo virtuale segue questo modello:E in a derived class, an override of this virtual method follows this pattern:</span><span class="sxs-lookup"><span data-stu-id="db3f6-120">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="db3f6-121">Se si oma l'implementazione predefinita nella classe base, la classe base diventa una classe astratta.</span><span class="sxs-lookup"><span data-stu-id="db3f6-121">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="db3f6-122">Nell'esempio di codice riportato di `function1` seguito viene illustrata la dichiarazione di un nuovo metodo virtuale in una classe base e come eseguirne l'override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="db3f6-122">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a><span data-ttu-id="db3f6-123">Costruttori ed ereditarietà</span><span class="sxs-lookup"><span data-stu-id="db3f6-123">Constructors and Inheritance</span></span>

<span data-ttu-id="db3f6-124">Il costruttore per la classe base deve essere chiamato nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="db3f6-124">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="db3f6-125">Gli argomenti per il costruttore della classe `inherit` base vengono visualizzati nell'elenco di argomenti nella clausola.</span><span class="sxs-lookup"><span data-stu-id="db3f6-125">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="db3f6-126">I valori utilizzati devono essere determinati dagli argomenti forniti al costruttore della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="db3f6-126">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="db3f6-127">Nel codice seguente vengono illustrate una classe base e una classe derivata, in cui la classe derivata chiama il costruttore della classe base nella clausola inherit:</span><span class="sxs-lookup"><span data-stu-id="db3f6-127">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="db3f6-128">Nel caso di più costruttori, è possibile utilizzare il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="db3f6-128">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="db3f6-129">La prima riga dei costruttori `inherit` di classe derivata è la clausola `val` e i campi vengono visualizzati come campi espliciti dichiarati con la parola chiave .</span><span class="sxs-lookup"><span data-stu-id="db3f6-129">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="db3f6-130">Per ulteriori informazioni, vedere [Campi espliciti: `val` parola chiave](./members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="db3f6-130">For more information, see [Explicit Fields: The `val` Keyword](./members/explicit-fields-the-val-keyword.md).</span></span>

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

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="db3f6-131">Alternative all'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="db3f6-131">Alternatives to Inheritance</span></span>

<span data-ttu-id="db3f6-132">Nei casi in cui è necessaria una modifica minore di un tipo, è consigliabile usare un'espressione oggetto come alternativa all'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="db3f6-132">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="db3f6-133">Nell'esempio seguente viene illustrato l'utilizzo di un'espressione oggetto come alternativa alla creazione di un nuovo tipo derivato:</span><span class="sxs-lookup"><span data-stu-id="db3f6-133">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="db3f6-134">Per ulteriori informazioni sulle espressioni di oggetto, vedere [Espressioni oggetto](object-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="db3f6-134">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="db3f6-135">Quando si creano gerarchie di oggetti, è consigliabile utilizzare un'unione discriminata anziché l'ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="db3f6-135">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="db3f6-136">Le unioni discriminate possono anche modellare il comportamento varia togliendo diversi oggetti che condividono un tipo generale comune.</span><span class="sxs-lookup"><span data-stu-id="db3f6-136">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="db3f6-137">Una singola unione discriminata può spesso eliminare la necessità di un numero di classi derivate che sono variazioni minori l'una dell'altra.</span><span class="sxs-lookup"><span data-stu-id="db3f6-137">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="db3f6-138">Per informazioni sulle unioni discriminate, vedere [Unioni discriminate](discriminated-unions.md).</span><span class="sxs-lookup"><span data-stu-id="db3f6-138">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="db3f6-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db3f6-139">See also</span></span>

- [<span data-ttu-id="db3f6-140">Espressioni di oggetto</span><span class="sxs-lookup"><span data-stu-id="db3f6-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="db3f6-141">Guida di riferimento al linguaggio F</span><span class="sxs-lookup"><span data-stu-id="db3f6-141">F# Language Reference</span></span>](index.md)

---
title: Associazioni do nelle classi (F#)
description: "Informazioni su come usare un'associazione in una definizione di classe che esegue azioni quando l'oggetto viene costruito oppure quando viene utilizzato innanzitutto il tipo ' do' F #."
ms.date: 05/16/2016
ms.openlocfilehash: e54a5bde52bf6973cc338c929ba99e6fd5b53127
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "43801532"
---
# <a name="do-bindings-in-classes"></a><span data-ttu-id="c362e-103">Associazioni do nelle classi</span><span class="sxs-lookup"><span data-stu-id="c362e-103">do Bindings in Classes</span></span>

<span data-ttu-id="c362e-104">Oggetto `do` associazione in una definizione di classe esegue azioni quando viene costruito l'oggetto oppure, per un valore statico `do` binding, quando viene utilizzato il tipo prima di tutto.</span><span class="sxs-lookup"><span data-stu-id="c362e-104">A `do` binding in a class definition performs actions when the object is constructed or, for a static `do` binding, when the type is first used.</span></span>

## <a name="syntax"></a><span data-ttu-id="c362e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c362e-105">Syntax</span></span>

```fsharp
[static] do expression
```

## <a name="remarks"></a><span data-ttu-id="c362e-106">Note</span><span class="sxs-lookup"><span data-stu-id="c362e-106">Remarks</span></span>

<span data-ttu-id="c362e-107">Oggetto `do` associazione viene visualizzata insieme a o dopo `let` associazioni, ma prima le definizioni dei membri in una definizione di classe.</span><span class="sxs-lookup"><span data-stu-id="c362e-107">A `do` binding appears together with or after `let` bindings but before member definitions in a class definition.</span></span> <span data-ttu-id="c362e-108">Anche se il `do` è facoltativo per la parola chiave `do` associazioni a livello di modulo, non è facoltativo per `do` associazioni in una definizione di classe.</span><span class="sxs-lookup"><span data-stu-id="c362e-108">Although the `do` keyword is optional for `do` bindings at the module level, it is not optional for `do` bindings in a class definition.</span></span>

<span data-ttu-id="c362e-109">Per la costruzione di tutti gli oggetti di qualsiasi tipo specifico, non statici `do` associazioni e non statici `let` associazioni vengono eseguite nell'ordine in cui appaiono nella definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="c362e-109">For the construction of every object of any given type, non-static `do` bindings and non-static `let` bindings are executed in the order in which they appear in the class definition.</span></span> <span data-ttu-id="c362e-110">Più `do` associazioni possono verificarsi in un solo tipo.</span><span class="sxs-lookup"><span data-stu-id="c362e-110">Multiple `do` bindings can occur in one type.</span></span> <span data-ttu-id="c362e-111">Non statiche `let` associazioni e non statiche `do` associazioni diventano il corpo del costruttore primario.</span><span class="sxs-lookup"><span data-stu-id="c362e-111">The non-static `let` bindings and the non-static `do` bindings become the body of the primary constructor.</span></span> <span data-ttu-id="c362e-112">Il codice non statiche `do` può fare riferimento a parametri del costruttore primaria e qualsiasi valori o funzioni definite in sezione delle associazioni di `let` sezione delle associazioni.</span><span class="sxs-lookup"><span data-stu-id="c362e-112">The code in the non-static `do` bindings section can reference the primary constructor parameters and any values or functions that are defined in the `let` bindings section.</span></span>

<span data-ttu-id="c362e-113">Non statici `do` associazioni possono accedere ai membri della classe, purché la classe ha un identificatore automatico che è definito da un `as` parola chiave della classe sull'intestazione e fino a quando tutte le occorrenze di tali membri sono qualificate con l'identificatore utente per la classe.</span><span class="sxs-lookup"><span data-stu-id="c362e-113">Non-static `do` bindings can access members of the class as long as the class has a self identifier that is defined by an `as` keyword in the class heading, and as long as all uses of those members are qualified with the self identifier for the class.</span></span>

<span data-ttu-id="c362e-114">Perché `let` associazioni inizializzano i campi privati di una classe, che è spesso necessario garantire che i membri si comportino come previsto, `do` associazioni vengono in genere inserite dopo `let` associazioni in modo che il codice nel `do` can associazione esecuzione con un oggetto completamente inizializzato.</span><span class="sxs-lookup"><span data-stu-id="c362e-114">Because `let` bindings initialize the private fields of a class, which is often necessary to guarantee that members behave as expected, `do` bindings are usually put after `let` bindings so that code in the `do` binding can execute with a fully initialized object.</span></span> <span data-ttu-id="c362e-115">Se il codice tenta di usare un membro prima del completamento dell'inizializzazione, viene generata un'eccezione InvalidOperationException.</span><span class="sxs-lookup"><span data-stu-id="c362e-115">If your code attempts to use a member before the initialization is complete, an InvalidOperationException is raised.</span></span>

<span data-ttu-id="c362e-116">Statico `do` associazioni possono fare riferimento a membri statici o campi di inclusione classe ma non i membri o i campi di istanza.</span><span class="sxs-lookup"><span data-stu-id="c362e-116">Static `do` bindings can reference static members or fields of the enclosing class but not instance members or fields.</span></span> <span data-ttu-id="c362e-117">Statico `do` associazioni diventano parte dell'inizializzatore statico per la classe che viene sempre eseguito prima che la classe viene usata prima di tutto.</span><span class="sxs-lookup"><span data-stu-id="c362e-117">Static `do` bindings become part of the static initializer for the class, which is guaranteed to execute before the class is first used.</span></span>

<span data-ttu-id="c362e-118">Gli attributi vengono ignorati per `do` associazioni di tipi.</span><span class="sxs-lookup"><span data-stu-id="c362e-118">Attributes are ignored for `do` bindings in types.</span></span> <span data-ttu-id="c362e-119">Se un attributo è obbligatorio per il codice eseguito in un `do` associazione, deve essere applicata al costruttore primario.</span><span class="sxs-lookup"><span data-stu-id="c362e-119">If an attribute is required for code that executes in a `do` binding, it must be applied to the primary constructor.</span></span>

<span data-ttu-id="c362e-120">Nel codice seguente, una classe ha un valore statico `do` associazione e non statici `do` associazione.</span><span class="sxs-lookup"><span data-stu-id="c362e-120">In the following code, a class has a static `do` binding and a non-static `do` binding.</span></span> <span data-ttu-id="c362e-121">L'oggetto ha un costruttore che ha due parametri, `a` e `b`, e vengono definiti due campi privati nel `let` associazioni per la classe.</span><span class="sxs-lookup"><span data-stu-id="c362e-121">The object has a constructor that has two parameters, `a` and `b`, and two private fields are defined in the `let` bindings for the class.</span></span> <span data-ttu-id="c362e-122">Vengono definite anche due proprietà.</span><span class="sxs-lookup"><span data-stu-id="c362e-122">Two properties are also defined.</span></span> <span data-ttu-id="c362e-123">Tutti questi rientrano nell'ambito non statiche `do` sezione associazioni, come illustrato dalla riga che vengono stampati tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="c362e-123">All of these are in scope in the non-static `do` bindings section, as is illustrated by the line that prints all those values.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

<span data-ttu-id="c362e-124">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="c362e-124">The output is as follows.</span></span>

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a><span data-ttu-id="c362e-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c362e-125">See also</span></span>

- [<span data-ttu-id="c362e-126">Membri</span><span class="sxs-lookup"><span data-stu-id="c362e-126">Members</span></span>](index.md)
- [<span data-ttu-id="c362e-127">Classi</span><span class="sxs-lookup"><span data-stu-id="c362e-127">Classes</span></span>](../classes.md)
- [<span data-ttu-id="c362e-128">Costruttori</span><span class="sxs-lookup"><span data-stu-id="c362e-128">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="c362e-129">Associazioni `let` nelle classi</span><span class="sxs-lookup"><span data-stu-id="c362e-129">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)
- [<span data-ttu-id="c362e-130">`do` associazioni</span><span class="sxs-lookup"><span data-stu-id="c362e-130">`do` Bindings</span></span>](../functions/do-Bindings.md)

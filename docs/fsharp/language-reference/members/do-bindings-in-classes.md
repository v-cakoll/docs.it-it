---
title: Associazioni do nelle classi (F#)
description: "Informazioni su come utilizzare un'associazione in una definizione di classe che esegue azioni quando l'oggetto viene costruito o quando il tipo viene utilizzato prima ' do' F #."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 27c2372328c8b23b91239517271c0d71a672a34d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="do-bindings-in-classes"></a><span data-ttu-id="cd587-103">Associazioni do nelle classi</span><span class="sxs-lookup"><span data-stu-id="cd587-103">do Bindings in Classes</span></span>

<span data-ttu-id="cd587-104">Oggetto `do` associazione in una definizione di classe esegue azioni quando l'oggetto viene costruito o, per un valore statico `do` binding, quando il tipo viene innanzitutto utilizzato.</span><span class="sxs-lookup"><span data-stu-id="cd587-104">A `do` binding in a class definition performs actions when the object is constructed or, for a static `do` binding, when the type is first used.</span></span>


## <a name="syntax"></a><span data-ttu-id="cd587-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cd587-105">Syntax</span></span>

```fsharp
[static] do expression
```

## <a name="remarks"></a><span data-ttu-id="cd587-106">Note</span><span class="sxs-lookup"><span data-stu-id="cd587-106">Remarks</span></span>
<span data-ttu-id="cd587-107">Oggetto `do` associazione viene visualizzata insieme a o dopo `let` associazioni ma prima delle definizioni di membro in una definizione di classe.</span><span class="sxs-lookup"><span data-stu-id="cd587-107">A `do` binding appears together with or after `let` bindings but before member definitions in a class definition.</span></span> <span data-ttu-id="cd587-108">Sebbene il `do` parola chiave è facoltativa per `do` associazioni a livello di modulo, non è facoltativo per `do` binding in una definizione di classe.</span><span class="sxs-lookup"><span data-stu-id="cd587-108">Although the `do` keyword is optional for `do` bindings at the module level, it is not optional for `do` bindings in a class definition.</span></span>

<span data-ttu-id="cd587-109">Per la costruzione di ogni oggetto di qualsiasi tipo specifico, non statico `do` associazioni e non statici `let` associazioni vengono eseguite nell'ordine in cui appaiono nella definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="cd587-109">For the construction of every object of any given type, non-static `do` bindings and non-static `let` bindings are executed in the order in which they appear in the class definition.</span></span> <span data-ttu-id="cd587-110">Più `do` associazioni possono verificarsi in un solo tipo.</span><span class="sxs-lookup"><span data-stu-id="cd587-110">Multiple `do` bindings can occur in one type.</span></span> <span data-ttu-id="cd587-111">Non statiche `let` associazioni e non statiche `do` associazioni diventano il corpo del costruttore primario.</span><span class="sxs-lookup"><span data-stu-id="cd587-111">The non-static `let` bindings and the non-static `do` bindings become the body of the primary constructor.</span></span> <span data-ttu-id="cd587-112">Il codice non statiche `do` sezione delle associazioni può fare riferimento a parametri del costruttore primario e qualsiasi valori o funzioni che sono definite nel `let` sezione delle associazioni.</span><span class="sxs-lookup"><span data-stu-id="cd587-112">The code in the non-static `do` bindings section can reference the primary constructor parameters and any values or functions that are defined in the `let` bindings section.</span></span>

<span data-ttu-id="cd587-113">Non statico `do` associazioni possono accedere i membri della classe fino a quando la classe dispone di un autoidentificatore definito da un `as` parola chiave nella classe di intestazione e a condizione che tutte le occorrenze di tali membri sono qualificate con l'identificatore utente per la classe.</span><span class="sxs-lookup"><span data-stu-id="cd587-113">Non-static `do` bindings can access members of the class as long as the class has a self identifier that is defined by an `as` keyword in the class heading, and as long as all uses of those members are qualified with the self identifier for the class.</span></span>

<span data-ttu-id="cd587-114">Poiché `let` associazioni inizializzano i campi privati di una classe, che è spesso necessario garantire che i membri si comportino come previsto, `do` binding vengono in genere inseriti dopo `let` associazioni in modo che il codice nel `do` associazione può eseguire con un oggetto completamente inizializzato.</span><span class="sxs-lookup"><span data-stu-id="cd587-114">Because `let` bindings initialize the private fields of a class, which is often necessary to guarantee that members behave as expected, `do` bindings are usually put after `let` bindings so that code in the `do` binding can execute with a fully initialized object.</span></span> <span data-ttu-id="cd587-115">Se il codice tenta di usare un membro prima del completamento dell'inizializzazione, viene generata un'eccezione InvalidOperationException.</span><span class="sxs-lookup"><span data-stu-id="cd587-115">If your code attempts to use a member before the initialization is complete, an InvalidOperationException is raised.</span></span>

<span data-ttu-id="cd587-116">Statico `do` associazioni possono fare riferimento a membri statici o campi di inclusione classe ma non campi o membri di istanza.</span><span class="sxs-lookup"><span data-stu-id="cd587-116">Static `do` bindings can reference static members or fields of the enclosing class but not instance members or fields.</span></span> <span data-ttu-id="cd587-117">Statico `do` associazioni diventano parte dell'inizializzatore statico per la classe, che viene sempre eseguito prima che la classe viene utilizzata prima.</span><span class="sxs-lookup"><span data-stu-id="cd587-117">Static `do` bindings become part of the static initializer for the class, which is guaranteed to execute before the class is first used.</span></span>

<span data-ttu-id="cd587-118">Gli attributi vengono ignorati per `do` nei tipi di associazioni.</span><span class="sxs-lookup"><span data-stu-id="cd587-118">Attributes are ignored for `do` bindings in types.</span></span> <span data-ttu-id="cd587-119">Se un attributo è obbligatorio per il codice eseguito in un `do` associazione deve essere applicata al costruttore primario.</span><span class="sxs-lookup"><span data-stu-id="cd587-119">If an attribute is required for code that executes in a `do` binding, it must be applied to the primary constructor.</span></span>

<span data-ttu-id="cd587-120">Nel codice seguente, una classe dispone di un valore statico `do` associazione e non statici `do` associazione.</span><span class="sxs-lookup"><span data-stu-id="cd587-120">In the following code, a class has a static `do` binding and a non-static `do` binding.</span></span> <span data-ttu-id="cd587-121">L'oggetto ha un costruttore che ha due parametri, `a` e `b`, e due campi privati sono definiti nel `let` associazioni per la classe.</span><span class="sxs-lookup"><span data-stu-id="cd587-121">The object has a constructor that has two parameters, `a` and `b`, and two private fields are defined in the `let` bindings for the class.</span></span> <span data-ttu-id="cd587-122">Vengono definite anche due proprietà.</span><span class="sxs-lookup"><span data-stu-id="cd587-122">Two properties are also defined.</span></span> <span data-ttu-id="cd587-123">Tutti questi rientrano nell'ambito non statiche `do` sezione associazioni, come illustrato dalla riga che vengono stampati tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="cd587-123">All of these are in scope in the non-static `do` bindings section, as is illustrated by the line that prints all those values.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

<span data-ttu-id="cd587-124">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="cd587-124">The output is as follows.</span></span>

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a><span data-ttu-id="cd587-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd587-125">See Also</span></span>
[<span data-ttu-id="cd587-126">Membri</span><span class="sxs-lookup"><span data-stu-id="cd587-126">Members</span></span>](index.md)

[<span data-ttu-id="cd587-127">Classi</span><span class="sxs-lookup"><span data-stu-id="cd587-127">Classes</span></span>](../classes.md)

[<span data-ttu-id="cd587-128">Costruttori</span><span class="sxs-lookup"><span data-stu-id="cd587-128">Constructors</span></span>](constructors.md)

[<span data-ttu-id="cd587-129">Associazioni `let` nelle classi</span><span class="sxs-lookup"><span data-stu-id="cd587-129">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)

[<span data-ttu-id="cd587-130">`do` Associazioni</span><span class="sxs-lookup"><span data-stu-id="cd587-130">`do` Bindings</span></span>](../functions/do-Bindings.md)

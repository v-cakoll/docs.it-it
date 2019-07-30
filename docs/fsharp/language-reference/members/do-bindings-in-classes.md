---
title: Associazioni do nelle classi
description: Informazioni su come usare un F# binding ' do ' in una definizione di classe, che esegue azioni quando l'oggetto viene costruito o quando il tipo viene usato per la prima volta.
ms.date: 05/16/2016
ms.openlocfilehash: ced4f1bb17d9e23bf51cc79b5a275cc334cca013
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627583"
---
# <a name="do-bindings-in-classes"></a><span data-ttu-id="e70da-103">Associazioni do nelle classi</span><span class="sxs-lookup"><span data-stu-id="e70da-103">do Bindings in Classes</span></span>

<span data-ttu-id="e70da-104">Un' `do` associazione in una definizione di classe esegue azioni quando l'oggetto viene costruito o, per un' `do` associazione statica, quando il tipo viene usato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="e70da-104">A `do` binding in a class definition performs actions when the object is constructed or, for a static `do` binding, when the type is first used.</span></span>

## <a name="syntax"></a><span data-ttu-id="e70da-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e70da-105">Syntax</span></span>

```fsharp
[static] do expression
```

## <a name="remarks"></a><span data-ttu-id="e70da-106">Note</span><span class="sxs-lookup"><span data-stu-id="e70da-106">Remarks</span></span>

<span data-ttu-id="e70da-107">Un' `do` associazione viene visualizzata insieme a o `let` dopo le associazioni ma prima delle definizioni dei membri in una definizione di classe.</span><span class="sxs-lookup"><span data-stu-id="e70da-107">A `do` binding appears together with or after `let` bindings but before member definitions in a class definition.</span></span> <span data-ttu-id="e70da-108">Sebbene la `do` parola chiave sia facoltativa per `do` le associazioni a livello di modulo, non è facoltativa per `do` le associazioni in una definizione di classe.</span><span class="sxs-lookup"><span data-stu-id="e70da-108">Although the `do` keyword is optional for `do` bindings at the module level, it is not optional for `do` bindings in a class definition.</span></span>

<span data-ttu-id="e70da-109">Per la costruzione di ogni oggetto di un determinato tipo, le associazioni non `do` statiche e le associazioni non statiche `let` vengono eseguite nell'ordine in cui sono visualizzate nella definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="e70da-109">For the construction of every object of any given type, non-static `do` bindings and non-static `let` bindings are executed in the order in which they appear in the class definition.</span></span> <span data-ttu-id="e70da-110">In `do` un tipo possono essere presenti più associazioni.</span><span class="sxs-lookup"><span data-stu-id="e70da-110">Multiple `do` bindings can occur in one type.</span></span> <span data-ttu-id="e70da-111">Le associazioni non statiche `let` e le associazioni non statiche `do` diventano il corpo del costruttore primario.</span><span class="sxs-lookup"><span data-stu-id="e70da-111">The non-static `let` bindings and the non-static `do` bindings become the body of the primary constructor.</span></span> <span data-ttu-id="e70da-112">Il codice nella sezione associazioni non statiche `do` può fare riferimento ai parametri del costruttore primario e a qualsiasi valore o funzione definito `let` nella sezione Bindings.</span><span class="sxs-lookup"><span data-stu-id="e70da-112">The code in the non-static `do` bindings section can reference the primary constructor parameters and any values or functions that are defined in the `let` bindings section.</span></span>

<span data-ttu-id="e70da-113">Le associazioni non `do` statiche possono accedere ai membri della classe purché la classe disponga di un identificatore di autonomia definito da una `as` parola chiave nell'intestazione della classe e purché tutti gli utilizzi di tali membri siano qualificati con l'identificatore automatico per la classe.</span><span class="sxs-lookup"><span data-stu-id="e70da-113">Non-static `do` bindings can access members of the class as long as the class has a self identifier that is defined by an `as` keyword in the class heading, and as long as all uses of those members are qualified with the self identifier for the class.</span></span>

<span data-ttu-id="e70da-114">Poiché `let` le associazioni inizializzano i campi privati di una classe, che è spesso necessaria per garantire che i membri si comportino come previsto, `do` le `let` associazioni vengono in genere inserite dopo le `do` associazioni in modo tale che il codice nell'associazione possa eseguire con un oggetto completamente inizializzato.</span><span class="sxs-lookup"><span data-stu-id="e70da-114">Because `let` bindings initialize the private fields of a class, which is often necessary to guarantee that members behave as expected, `do` bindings are usually put after `let` bindings so that code in the `do` binding can execute with a fully initialized object.</span></span> <span data-ttu-id="e70da-115">Se il codice tenta di utilizzare un membro prima che l'inizializzazione venga completata, viene generata un'eccezione InvalidOperationException.</span><span class="sxs-lookup"><span data-stu-id="e70da-115">If your code attempts to use a member before the initialization is complete, an InvalidOperationException is raised.</span></span>

<span data-ttu-id="e70da-116">Le `do` associazioni statiche possono fare riferimento a membri o campi statici della classe contenitore, ma non a membri o campi di istanza.</span><span class="sxs-lookup"><span data-stu-id="e70da-116">Static `do` bindings can reference static members or fields of the enclosing class but not instance members or fields.</span></span> <span data-ttu-id="e70da-117">Le `do` associazioni statiche diventano parte dell'inizializzatore statico per la classe, che è garantita l'esecuzione prima che la classe venga usata per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="e70da-117">Static `do` bindings become part of the static initializer for the class, which is guaranteed to execute before the class is first used.</span></span>

<span data-ttu-id="e70da-118">Gli attributi vengono ignorati per `do` le associazioni nei tipi.</span><span class="sxs-lookup"><span data-stu-id="e70da-118">Attributes are ignored for `do` bindings in types.</span></span> <span data-ttu-id="e70da-119">Se è necessario un attributo per il codice eseguito in un' `do` associazione, è necessario applicarlo al costruttore primario.</span><span class="sxs-lookup"><span data-stu-id="e70da-119">If an attribute is required for code that executes in a `do` binding, it must be applied to the primary constructor.</span></span>

<span data-ttu-id="e70da-120">Nel codice seguente, una classe ha un'associazione statica `do` e un'associazione non statica. `do`</span><span class="sxs-lookup"><span data-stu-id="e70da-120">In the following code, a class has a static `do` binding and a non-static `do` binding.</span></span> <span data-ttu-id="e70da-121">L'oggetto ha un costruttore con due parametri, `a` e `b`e due `let` campi privati vengono definiti nelle associazioni per la classe.</span><span class="sxs-lookup"><span data-stu-id="e70da-121">The object has a constructor that has two parameters, `a` and `b`, and two private fields are defined in the `let` bindings for the class.</span></span> <span data-ttu-id="e70da-122">Sono definite anche due proprietà.</span><span class="sxs-lookup"><span data-stu-id="e70da-122">Two properties are also defined.</span></span> <span data-ttu-id="e70da-123">Tutti questi elementi sono inclusi nell'ambito della sezione associazioni non `do` statiche, come illustrato dalla riga che stampa tutti questi valori.</span><span class="sxs-lookup"><span data-stu-id="e70da-123">All of these are in scope in the non-static `do` bindings section, as is illustrated by the line that prints all those values.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

<span data-ttu-id="e70da-124">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="e70da-124">The output is as follows.</span></span>

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a><span data-ttu-id="e70da-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e70da-125">See also</span></span>

- [<span data-ttu-id="e70da-126">Membri</span><span class="sxs-lookup"><span data-stu-id="e70da-126">Members</span></span>](index.md)
- [<span data-ttu-id="e70da-127">Classi</span><span class="sxs-lookup"><span data-stu-id="e70da-127">Classes</span></span>](../classes.md)
- [<span data-ttu-id="e70da-128">Costruttori</span><span class="sxs-lookup"><span data-stu-id="e70da-128">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="e70da-129">Associazioni `let` nelle classi</span><span class="sxs-lookup"><span data-stu-id="e70da-129">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)
- [<span data-ttu-id="e70da-130">`do`Associazioni</span><span class="sxs-lookup"><span data-stu-id="e70da-130">`do` Bindings</span></span>](../functions/do-Bindings.md)

---
title: Costruttori
description: Informazioni su come definire e utilizzare i costruttori in F# per creare e inizializzare oggetti classe e struttura.
ms.date: 05/16/2016
ms.openlocfilehash: 6769ec7fc6768090d8ae68e21946a58829b6eea0
ms.sourcegitcommit: 878ca7550b653114c3968ef8906da2b3e60e3c7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736840"
---
# <a name="constructors"></a><span data-ttu-id="14833-103">Costruttori</span><span class="sxs-lookup"><span data-stu-id="14833-103">Constructors</span></span>

<span data-ttu-id="14833-104">Questo articolo descrive come definire e usare i costruttori per creare e inizializzare oggetti classe e struttura.</span><span class="sxs-lookup"><span data-stu-id="14833-104">This article describes how to define and use constructors to create and initialize class and structure objects.</span></span>

## <a name="construction-of-class-objects"></a><span data-ttu-id="14833-105">Costruzione di oggetti classe</span><span class="sxs-lookup"><span data-stu-id="14833-105">Construction of class objects</span></span>

<span data-ttu-id="14833-106">Gli oggetti dei tipi di classe hanno costruttori.</span><span class="sxs-lookup"><span data-stu-id="14833-106">Objects of class types have constructors.</span></span> <span data-ttu-id="14833-107">Esistono due tipi di costruttori.</span><span class="sxs-lookup"><span data-stu-id="14833-107">There are two kinds of constructors.</span></span> <span data-ttu-id="14833-108">Uno è il costruttore primario, i cui parametri vengono visualizzati tra parentesi subito dopo il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="14833-108">One is the primary constructor, whose parameters appear in parentheses just after the type name.</span></span> <span data-ttu-id="14833-109">Per specificare altri costruttori facoltativi aggiuntivi, usare la `new` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="14833-109">You specify other, optional additional constructors by using the `new` keyword.</span></span> <span data-ttu-id="14833-110">Tutti questi costruttori aggiuntivi devono chiamare il costruttore primario.</span><span class="sxs-lookup"><span data-stu-id="14833-110">Any such additional constructors must call the primary constructor.</span></span>

<span data-ttu-id="14833-111">Il costruttore primario contiene `let` le `do` associazioni e visualizzate all'inizio della definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="14833-111">The primary constructor contains `let` and `do` bindings that appear at the start of the class definition.</span></span> <span data-ttu-id="14833-112">Un' `let` associazione dichiara i metodi e i campi privati della classe; un' `do` associazione esegue il codice.</span><span class="sxs-lookup"><span data-stu-id="14833-112">A `let` binding declares private fields and methods of the class; a `do` binding executes code.</span></span> <span data-ttu-id="14833-113">Per ulteriori informazioni sulle `let` associazioni nei costruttori di classi, vedere [ `let` binding nelle classi](let-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="14833-113">For more information about `let` bindings in class constructors, see [`let` Bindings in Classes](let-bindings-in-classes.md).</span></span> <span data-ttu-id="14833-114">Per ulteriori informazioni sulle `do` associazioni nei costruttori, vedere [ `do` binding nelle classi](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="14833-114">For more information about `do` bindings in constructors, see [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

<span data-ttu-id="14833-115">Indipendentemente dal fatto che il costruttore che si vuole chiamare sia un costruttore primario o un costruttore aggiuntivo, è possibile creare oggetti usando un' `new` espressione, con o senza la parola `new` chiave Optional.</span><span class="sxs-lookup"><span data-stu-id="14833-115">Regardless of whether the constructor you want to call is a primary constructor or an additional constructor, you can create objects by using a `new` expression, with or without the optional `new` keyword.</span></span> <span data-ttu-id="14833-116">Gli oggetti vengono inizializzati insieme agli argomenti del costruttore, elencando gli argomenti nell'ordine e separati da virgole e racchiusi tra parentesi o utilizzando argomenti e valori denominati tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="14833-116">You initialize your objects together with constructor arguments, either by listing the arguments in order and separated by commas and enclosed in parentheses, or by using named arguments and values in parentheses.</span></span> <span data-ttu-id="14833-117">È inoltre possibile impostare le proprietà di un oggetto durante la costruzione dell'oggetto utilizzando i nomi delle proprietà e assegnando valori analogamente a come si utilizzano gli argomenti del costruttore denominati.</span><span class="sxs-lookup"><span data-stu-id="14833-117">You can also set properties on an object during the construction of the object by using the property names and assigning values just as you use named constructor arguments.</span></span>

<span data-ttu-id="14833-118">Nel codice seguente viene illustrata una classe che dispone di un costruttore e diversi modi per creare oggetti:</span><span class="sxs-lookup"><span data-stu-id="14833-118">The following code illustrates a class that has a constructor and various ways of creating objects:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

<span data-ttu-id="14833-119">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="14833-119">The output is as follows:</span></span>

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a><span data-ttu-id="14833-120">Costruzione di strutture</span><span class="sxs-lookup"><span data-stu-id="14833-120">Construction of structures</span></span>

<span data-ttu-id="14833-121">Le strutture seguono tutte le regole delle classi.</span><span class="sxs-lookup"><span data-stu-id="14833-121">Structures follow all the rules of classes.</span></span> <span data-ttu-id="14833-122">Pertanto, è possibile avere un costruttore primario ed è possibile fornire costruttori `new`aggiuntivi tramite.</span><span class="sxs-lookup"><span data-stu-id="14833-122">Therefore, you can have a primary constructor, and you can provide additional constructors by using `new`.</span></span> <span data-ttu-id="14833-123">Tuttavia, esiste una differenza importante tra le strutture e le classi: le strutture possono avere un costruttore senza parametri, ovvero uno senza argomenti, anche se non è stato definito alcun costruttore primario.</span><span class="sxs-lookup"><span data-stu-id="14833-123">However, there is one important difference between structures and classes: structures can have a parameterless constructor (that is, one with no arguments) even if no primary constructor is defined.</span></span> <span data-ttu-id="14833-124">Il costruttore senza parametri Inizializza tutti i campi sul valore predefinito per quel tipo, in genere zero o l'equivalente.</span><span class="sxs-lookup"><span data-stu-id="14833-124">The parameterless constructor initializes all the fields to the default value for that type, usually zero or its equivalent.</span></span> <span data-ttu-id="14833-125">Tutti i costruttori definiti per le strutture devono avere almeno un argomento in modo che non siano in conflitto con il costruttore senza parametri.</span><span class="sxs-lookup"><span data-stu-id="14833-125">Any constructors that you define for structures must have at least one argument so that they do not conflict with the parameterless constructor.</span></span>

<span data-ttu-id="14833-126">Inoltre, le strutture hanno spesso campi creati usando la `val` parola chiave. le classi possono anche avere questi campi.</span><span class="sxs-lookup"><span data-stu-id="14833-126">Also, structures often have fields that are created by using the `val` keyword; classes can also have these fields.</span></span> <span data-ttu-id="14833-127">Le strutture e le classi con campi definiti tramite la `val` parola chiave possono essere inizializzate anche in costruttori aggiuntivi tramite espressioni di record, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="14833-127">Structures and classes that have fields defined by using the `val` keyword can also be initialized in additional constructors by using record expressions, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

<span data-ttu-id="14833-128">Per ulteriori informazioni, vedere [campi espliciti: `val` Parola chiave](explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="14833-128">For more information, see [Explicit Fields: The `val` Keyword](explicit-fields-the-val-keyword.md).</span></span>

## <a name="executing-side-effects-in-constructors"></a><span data-ttu-id="14833-129">Esecuzione di effetti collaterali nei costruttori</span><span class="sxs-lookup"><span data-stu-id="14833-129">Executing side effects in constructors</span></span>

<span data-ttu-id="14833-130">Un costruttore primario in una classe può eseguire codice in un' `do` associazione.</span><span class="sxs-lookup"><span data-stu-id="14833-130">A primary constructor in a class can execute code in a `do` binding.</span></span> <span data-ttu-id="14833-131">Tuttavia, cosa accade se è necessario eseguire codice in un costruttore aggiuntivo, senza un' `do` associazione?</span><span class="sxs-lookup"><span data-stu-id="14833-131">However, what if you have to execute code in an additional constructor, without a `do` binding?</span></span> <span data-ttu-id="14833-132">A tale scopo, usare la `then` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="14833-132">To do this, you use the `then` keyword.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

<span data-ttu-id="14833-133">Gli effetti collaterali del costruttore primario continuano a essere eseguiti.</span><span class="sxs-lookup"><span data-stu-id="14833-133">The side effects of the primary constructor still execute.</span></span> <span data-ttu-id="14833-134">Di conseguenza, l'output è il seguente:</span><span class="sxs-lookup"><span data-stu-id="14833-134">Therefore, the output is as follows:</span></span>

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a><span data-ttu-id="14833-135">Identificatori autonomi nei costruttori</span><span class="sxs-lookup"><span data-stu-id="14833-135">Self identifiers in constructors</span></span>

<span data-ttu-id="14833-136">Gli altri membri forniscono un nome per l'oggetto corrente nella definizione di ogni membro.</span><span class="sxs-lookup"><span data-stu-id="14833-136">In other members, you provide a name for the current object in the definition of each member.</span></span> <span data-ttu-id="14833-137">È anche possibile inserire l'identificatore automatico nella prima riga della definizione della classe usando la `as` parola chiave immediatamente dopo i parametri del costruttore.</span><span class="sxs-lookup"><span data-stu-id="14833-137">You can also put the self identifier on the first line of the class definition by using the `as` keyword immediately following the constructor parameters.</span></span> <span data-ttu-id="14833-138">Nell'esempio seguente viene illustrata questa sintassi.</span><span class="sxs-lookup"><span data-stu-id="14833-138">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

<span data-ttu-id="14833-139">In costruttori aggiuntivi è inoltre possibile definire un identificatore autonomo inserendo la `as` clausola subito dopo i parametri del costruttore.</span><span class="sxs-lookup"><span data-stu-id="14833-139">In additional constructors, you can also define a self identifier by putting the `as` clause right after the constructor parameters.</span></span> <span data-ttu-id="14833-140">Nell'esempio seguente viene illustrata questa sintassi:</span><span class="sxs-lookup"><span data-stu-id="14833-140">The following example illustrates this syntax:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

<span data-ttu-id="14833-141">Possono verificarsi problemi quando si tenta di utilizzare un oggetto prima che sia completamente definito.</span><span class="sxs-lookup"><span data-stu-id="14833-141">Problems can occur when you try to use an object before it is fully defined.</span></span> <span data-ttu-id="14833-142">Pertanto, gli utilizzi dell'identificatore automatico possono causare la generazione di un avviso da parte del compilatore e l'inserimento di controlli aggiuntivi per garantire che i membri di un oggetto non accedano prima che l'oggetto venga inizializzato.</span><span class="sxs-lookup"><span data-stu-id="14833-142">Therefore, uses of the self identifier can cause the compiler to emit a warning and insert additional checks to ensure the members of an object are not accessed before the object is initialized.</span></span> <span data-ttu-id="14833-143">È consigliabile usare solo l'identificatore automatico nei `do` binding del costruttore primario o dopo la `then` parola chiave in costruttori aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="14833-143">You should only use the self identifier in the `do` bindings of the primary constructor, or after the `then` keyword in additional constructors.</span></span>

<span data-ttu-id="14833-144">Il nome dell'identificatore auto non deve essere `this`.</span><span class="sxs-lookup"><span data-stu-id="14833-144">The name of the self identifier does not have to be `this`.</span></span> <span data-ttu-id="14833-145">Può essere qualsiasi identificatore valido.</span><span class="sxs-lookup"><span data-stu-id="14833-145">It can be any valid identifier.</span></span>

## <a name="assigning-values-to-properties-at-initialization"></a><span data-ttu-id="14833-146">Assegnazione di valori a proprietà in fase di inizializzazione</span><span class="sxs-lookup"><span data-stu-id="14833-146">Assigning values to properties at initialization</span></span>

<span data-ttu-id="14833-147">È possibile assegnare valori alle proprietà di un oggetto classe nel codice di inizializzazione aggiungendo un elenco di assegnazioni del form `property = value` all'elenco di argomenti per un costruttore.</span><span class="sxs-lookup"><span data-stu-id="14833-147">You can assign values to the properties of a class object in the initialization code by appending a list of assignments of the form `property = value` to the argument list for a constructor.</span></span> <span data-ttu-id="14833-148">Questa operazione è illustrata nell'esempio di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="14833-148">This is shown in the following code example:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="14833-149">Nella versione seguente del codice precedente viene illustrata la combinazione di argomenti ordinari, argomenti facoltativi e impostazioni delle proprietà in una chiamata al costruttore:</span><span class="sxs-lookup"><span data-stu-id="14833-149">The following version of the previous code illustrates the combination of ordinary arguments, optional arguments, and property settings in one constructor call:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]

## <a name="constructors-in-inherited-class"></a><span data-ttu-id="14833-150">Costruttori nella classe ereditata</span><span class="sxs-lookup"><span data-stu-id="14833-150">Constructors in inherited class</span></span>

<span data-ttu-id="14833-151">Quando si eredita da una classe di base che dispone di un costruttore, è necessario specificare i relativi argomenti nella clausola inherit.</span><span class="sxs-lookup"><span data-stu-id="14833-151">When inheriting from a base class that has a constructor, you must specify its arguments in the inherit clause.</span></span> <span data-ttu-id="14833-152">Per ulteriori informazioni, vedere [costruttori ed ereditarietà](../inheritance.md#constructors-and-inheritance).</span><span class="sxs-lookup"><span data-stu-id="14833-152">For more information, see [Constructors and inheritance](../inheritance.md#constructors-and-inheritance).</span></span>

## <a name="static-constructors-or-type-constructors"></a><span data-ttu-id="14833-153">Costruttori statici o costruttori di tipo</span><span class="sxs-lookup"><span data-stu-id="14833-153">Static constructors or type constructors</span></span>

<span data-ttu-id="14833-154">Oltre a specificare il codice per la creazione di oggetti `let` , `do` le associazioni statiche e possono essere create in tipi di classe che vengono eseguite prima che il tipo venga usato per la prima volta per eseguire l'inizializzazione a livello di tipo.</span><span class="sxs-lookup"><span data-stu-id="14833-154">In addition to specifying code for creating objects, static `let` and `do` bindings can be authored in class types that execute before the type is first used to perform initialization at the type level.</span></span> <span data-ttu-id="14833-155">Per ulteriori informazioni, vedere [ `let` binding in classi](let-bindings-in-classes.md) e [ `do` associazioni nelle classi](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="14833-155">For more information, see [`let` Bindings in Classes](let-bindings-in-classes.md) and [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="14833-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14833-156">See also</span></span>

- [<span data-ttu-id="14833-157">Membri</span><span class="sxs-lookup"><span data-stu-id="14833-157">Members</span></span>](index.md)

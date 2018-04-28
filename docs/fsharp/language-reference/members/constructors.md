---
title: Costruttori (F#)
description: 'Informazioni su come definire e utilizzare i costruttori in F # per creare e inizializzare gli oggetti di classe e struttura.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: d9062ae747c37bdc14104658ad0ec7d11f5545f0
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="constructors"></a><span data-ttu-id="6fadd-103">Costruttori</span><span class="sxs-lookup"><span data-stu-id="6fadd-103">Constructors</span></span>

<span data-ttu-id="6fadd-104">In questo argomento viene descritto come definire e utilizzare i costruttori per creare e inizializzare gli oggetti di classe e struttura.</span><span class="sxs-lookup"><span data-stu-id="6fadd-104">This topic describes how to define and use constructors to create and initialize class and structure objects.</span></span>


## <a name="construction-of-class-objects"></a><span data-ttu-id="6fadd-105">Costruzione di oggetti classe</span><span class="sxs-lookup"><span data-stu-id="6fadd-105">Construction of Class Objects</span></span>
<span data-ttu-id="6fadd-106">Gli oggetti di tipi di classe hanno costruttori.</span><span class="sxs-lookup"><span data-stu-id="6fadd-106">Objects of class types have constructors.</span></span> <span data-ttu-id="6fadd-107">Esistono due tipi di costruttori.</span><span class="sxs-lookup"><span data-stu-id="6fadd-107">There are two kinds of constructors.</span></span> <span data-ttu-id="6fadd-108">Uno è il costruttore primario, i cui parametri sono inclusi tra parentesi subito dopo il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="6fadd-108">One is the primary constructor, whose parameters appear in parentheses just after the type name.</span></span> <span data-ttu-id="6fadd-109">Specificare gli altri costruttori aggiuntivi facoltativi utilizzando il `new` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="6fadd-109">You specify other, optional additional constructors by using the `new` keyword.</span></span> <span data-ttu-id="6fadd-110">Qualsiasi costruttore aggiuntivo devono chiamare il costruttore primario.</span><span class="sxs-lookup"><span data-stu-id="6fadd-110">Any such additional constructors must call the primary constructor.</span></span>

<span data-ttu-id="6fadd-111">Il costruttore primario contiene `let` e `do` associazioni che vengono visualizzati all'inizio della definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="6fadd-111">The primary constructor contains `let` and `do` bindings that appear at the start of the class definition.</span></span> <span data-ttu-id="6fadd-112">Oggetto `let` binding dichiara i campi privati e i metodi della classe; un `do` associazione esegue il codice.</span><span class="sxs-lookup"><span data-stu-id="6fadd-112">A `let` binding declares private fields and methods of the class; a `do` binding executes code.</span></span> <span data-ttu-id="6fadd-113">Per ulteriori informazioni su `let` associazioni nei costruttori di classe, vedere [ `let` associazioni nelle classi](let-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="6fadd-113">For more information about `let` bindings in class constructors, see [`let` Bindings in Classes](let-bindings-in-classes.md).</span></span> <span data-ttu-id="6fadd-114">Per ulteriori informazioni su `do` associazioni nei costruttori, vedere [ `do` associazioni nelle classi](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="6fadd-114">For more information about `do` bindings in constructors, see [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

<span data-ttu-id="6fadd-115">Indipendentemente dal fatto che il costruttore da chiamare sia un costruttore primario o un costruttore aggiuntivo, è possibile creare oggetti usando una `new` espressione, con o senza l'opzione facoltativa `new` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="6fadd-115">Regardless of whether the constructor you want to call is a primary constructor or an additional constructor, you can create objects by using a `new` expression, with or without the optional `new` keyword.</span></span> <span data-ttu-id="6fadd-116">Inizializzare gli oggetti con gli argomenti del costruttore, elencando gli argomenti nell'ordine e separati da virgole e racchiuso tra parentesi o utilizzando gli argomenti denominati e i valori tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="6fadd-116">You initialize your objects together with constructor arguments, either by listing the arguments in order and separated by commas and enclosed in parentheses, or by using named arguments and values in parentheses.</span></span> <span data-ttu-id="6fadd-117">È inoltre possibile impostare proprietà su un oggetto durante la costruzione dell'oggetto usando i nomi delle proprietà e l'assegnazione di valori come si utilizzano denominato gli argomenti del costruttore.</span><span class="sxs-lookup"><span data-stu-id="6fadd-117">You can also set properties on an object during the construction of the object by using the property names and assigning values just as you use named constructor arguments.</span></span>

<span data-ttu-id="6fadd-118">Il codice seguente viene illustrata una classe che ha un costruttore e diverse modalità di creazione di oggetti.</span><span class="sxs-lookup"><span data-stu-id="6fadd-118">The following code illustrates a class that has a constructor and various ways of creating objects.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

<span data-ttu-id="6fadd-119">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="6fadd-119">The output is as follows.</span></span>

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a><span data-ttu-id="6fadd-120">Costruzione di strutture</span><span class="sxs-lookup"><span data-stu-id="6fadd-120">Construction of Structures</span></span>
<span data-ttu-id="6fadd-121">Le strutture seguono tutte le regole delle classi.</span><span class="sxs-lookup"><span data-stu-id="6fadd-121">Structures follow all the rules of classes.</span></span> <span data-ttu-id="6fadd-122">Pertanto, è possibile avere un costruttore primario e fornire costruttori aggiuntivi utilizzando `new`.</span><span class="sxs-lookup"><span data-stu-id="6fadd-122">Therefore, you can have a primary constructor, and you can provide additional constructors by using `new`.</span></span> <span data-ttu-id="6fadd-123">Tuttavia, è una differenza importante tra classi e strutture: le strutture possono disporre di un costruttore predefinito (vale a dire uno senza argomenti) anche se è definito alcun costruttore primario.</span><span class="sxs-lookup"><span data-stu-id="6fadd-123">However, there is one important difference between structures and classes: structures can have a default constructor (that is, one with no arguments) even if no primary constructor is defined.</span></span> <span data-ttu-id="6fadd-124">Il costruttore predefinito inizializza tutti i campi per il valore predefinito per tale tipo, generalmente zero o equivalente.</span><span class="sxs-lookup"><span data-stu-id="6fadd-124">The default constructor initializes all the fields to the default value for that type, usually zero or its equivalent.</span></span> <span data-ttu-id="6fadd-125">Costruttori definiti per le strutture devono avere almeno un argomento in modo che non entrino in conflitto con il costruttore predefinito.</span><span class="sxs-lookup"><span data-stu-id="6fadd-125">Any constructors that you define for structures must have at least one argument so that they do not conflict with the default constructor.</span></span>

<span data-ttu-id="6fadd-126">Strutture, inoltre, hanno spesso i campi che vengono creati utilizzando il `val` (parola chiave); le classi possono disporre anche di questi campi.</span><span class="sxs-lookup"><span data-stu-id="6fadd-126">Also, structures often have fields that are created by using the `val` keyword; classes can also have these fields.</span></span> <span data-ttu-id="6fadd-127">Strutture e classi che dispongono di campi definiti tramite il `val` parola chiave può inoltre essere inizializzati in costruttori aggiuntivi utilizzando espressioni di record, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="6fadd-127">Structures and classes that have fields defined by using the `val` keyword can also be initialized in additional constructors by using record expressions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

<span data-ttu-id="6fadd-128">Per ulteriori informazioni, vedere [campi espliciti: il `val` parola chiave](explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="6fadd-128">For more information, see [Explicit Fields: The `val` Keyword](explicit-fields-the-val-keyword.md).</span></span>


## <a name="executing-side-effects-in-constructors"></a><span data-ttu-id="6fadd-129">L'esecuzione di effetti collaterali nei costruttori</span><span class="sxs-lookup"><span data-stu-id="6fadd-129">Executing Side Effects in Constructors</span></span>
<span data-ttu-id="6fadd-130">Un costruttore primario in una classe può eseguire codice in un `do` associazione.</span><span class="sxs-lookup"><span data-stu-id="6fadd-130">A primary constructor in a class can execute code in a `do` binding.</span></span> <span data-ttu-id="6fadd-131">Tuttavia, se è necessario eseguire codice in un costruttore aggiuntivo, senza un `do` associazione?</span><span class="sxs-lookup"><span data-stu-id="6fadd-131">However, what if you have to execute code in an additional constructor, without a `do` binding?</span></span> <span data-ttu-id="6fadd-132">A tale scopo, utilizzare il `then` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="6fadd-132">To do this, you use the `then` keyword.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

<span data-ttu-id="6fadd-133">Eseguire comunque gli effetti collaterali del costruttore primario.</span><span class="sxs-lookup"><span data-stu-id="6fadd-133">The side effects of the primary constructor still execute.</span></span> <span data-ttu-id="6fadd-134">Di conseguenza, l'output è il seguente.</span><span class="sxs-lookup"><span data-stu-id="6fadd-134">Therefore, the output is as follows.</span></span>

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a><span data-ttu-id="6fadd-135">Autoidentificatori nei costruttori</span><span class="sxs-lookup"><span data-stu-id="6fadd-135">Self Identifiers in Constructors</span></span>
<span data-ttu-id="6fadd-136">Negli altri membri, fornire un nome per l'oggetto corrente nella definizione di ogni membro.</span><span class="sxs-lookup"><span data-stu-id="6fadd-136">In other members, you provide a name for the current object in the definition of each member.</span></span> <span data-ttu-id="6fadd-137">È anche possibile inserire l'autoidentificatore nella prima riga della definizione della classe utilizzando il `as` parola chiave immediatamente dopo i parametri del costruttore.</span><span class="sxs-lookup"><span data-stu-id="6fadd-137">You can also put the self identifier on the first line of the class definition by using the `as` keyword immediately following the constructor parameters.</span></span> <span data-ttu-id="6fadd-138">Nell'esempio seguente viene illustrata questa sintassi.</span><span class="sxs-lookup"><span data-stu-id="6fadd-138">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

<span data-ttu-id="6fadd-139">Nei costruttori aggiuntivi, è anche possibile definire un autoidentificatore inserendo il `as` clausola subito dopo i parametri del costruttore.</span><span class="sxs-lookup"><span data-stu-id="6fadd-139">In additional constructors, you can also define a self identifier by putting the `as` clause right after the constructor parameters.</span></span> <span data-ttu-id="6fadd-140">Nell'esempio seguente viene illustrata questa sintassi.</span><span class="sxs-lookup"><span data-stu-id="6fadd-140">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

<span data-ttu-id="6fadd-141">Problemi possono verificarsi quando si tenta di utilizzare un oggetto prima che sia definita completamente.</span><span class="sxs-lookup"><span data-stu-id="6fadd-141">Problems can occur when you try to use an object before it is fully defined.</span></span> <span data-ttu-id="6fadd-142">Pertanto, Usa dello stesso identificatore può causare al compilatore di generare un avviso e l'inserimento di controlli aggiuntivi per assicurarsi che i membri di un oggetto non si accede prima l'oggetto viene inizializzato.</span><span class="sxs-lookup"><span data-stu-id="6fadd-142">Therefore, uses of the self identifier can cause the compiler to emit a warning and insert additional checks to ensure the members of an object are not accessed before the object is initialized.</span></span> <span data-ttu-id="6fadd-143">Utilizzare solo l'autoidentificatore nella `do` associazioni del costruttore primario o dopo il `then` (parola chiave) nei costruttori aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="6fadd-143">You should only use the self identifier in the `do` bindings of the primary constructor, or after the `then` keyword in additional constructors.</span></span>

<span data-ttu-id="6fadd-144">Il nome dello stesso identificatore non deve essere `this`.</span><span class="sxs-lookup"><span data-stu-id="6fadd-144">The name of the self identifier does not have to be `this`.</span></span> <span data-ttu-id="6fadd-145">Può essere qualsiasi identificatore valido.</span><span class="sxs-lookup"><span data-stu-id="6fadd-145">It can be any valid identifier.</span></span>


## <a name="assigning-values-to-properties-at-initialization"></a><span data-ttu-id="6fadd-146">L'assegnazione di valori alle proprietà in fase di inizializzazione</span><span class="sxs-lookup"><span data-stu-id="6fadd-146">Assigning Values to Properties at Initialization</span></span>
<span data-ttu-id="6fadd-147">È possibile assegnare valori alle proprietà di un oggetto di classe nel codice di inizializzazione aggiungendo un elenco di assegnazioni nel formato `property = value` all'elenco di argomenti per un costruttore.</span><span class="sxs-lookup"><span data-stu-id="6fadd-147">You can assign values to the properties of a class object in the initialization code by appending a list of assignments of the form `property = value` to the argument list for a constructor.</span></span> <span data-ttu-id="6fadd-148">Queste operazioni sono illustrate nell'esempio di codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="6fadd-148">This is shown in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="6fadd-149">La seguente versione del codice precedente viene illustrata la combinazione di argomenti normali, gli argomenti facoltativi e le impostazioni delle proprietà nella chiamata di un costruttore.</span><span class="sxs-lookup"><span data-stu-id="6fadd-149">The following version of the previous code illustrates the combination of ordinary arguments, optional arguments, and property settings in one constructor call.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]
    
## <a name="constructors-in-inherited-class"></a><span data-ttu-id="6fadd-150">Costruttori di classe ereditata</span><span class="sxs-lookup"><span data-stu-id="6fadd-150">Constructors in inherited class</span></span>
<span data-ttu-id="6fadd-151">Quando si eredita da una classe di base che ha un costruttore, è necessario specificare gli argomenti nella clausola eredita.</span><span class="sxs-lookup"><span data-stu-id="6fadd-151">When inheriting from a base class that has a constructor, you must specify its arguments in the inherit clause.</span></span> <span data-ttu-id="6fadd-152">Per ulteriori informazioni, vedere [costruttori ed ereditarietà](../inheritance.md#constructors-and-inheritance).</span><span class="sxs-lookup"><span data-stu-id="6fadd-152">For more information, see [Constructors and inheritance](../inheritance.md#constructors-and-inheritance).</span></span>

## <a name="static-constructors-or-type-constructors"></a><span data-ttu-id="6fadd-153">Costruttori statici o costruttori di tipo</span><span class="sxs-lookup"><span data-stu-id="6fadd-153">Static Constructors or Type Constructors</span></span>
<span data-ttu-id="6fadd-154">Oltre a specificare il codice per la creazione di oggetti, statici `let` e `do` associazioni possono essere create in tipi di classe da eseguire prima che il tipo viene innanzitutto utilizzato per eseguire l'inizializzazione a livello di tipo.</span><span class="sxs-lookup"><span data-stu-id="6fadd-154">In addition to specifying code for creating objects, static `let` and `do` bindings can be authored in class types that execute before the type is first used to perform initialization at the type level.</span></span> <span data-ttu-id="6fadd-155">Per ulteriori informazioni, vedere [ `let` associazioni nelle classi](let-bindings-in-classes.md) e [ `do` associazioni nelle classi](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="6fadd-155">For more information, see [`let` Bindings in Classes](let-bindings-in-classes.md) and [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6fadd-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fadd-156">See Also</span></span>
[<span data-ttu-id="6fadd-157">Membri</span><span class="sxs-lookup"><span data-stu-id="6fadd-157">Members</span></span>](index.md)

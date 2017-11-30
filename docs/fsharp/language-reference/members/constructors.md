---
title: Costruttori (F#)
description: 'Informazioni su come definire e utilizzare i costruttori in F # per creare e inizializzare gli oggetti di classe e struttura.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e0da2250-29de-4145-a1be-e5faff080759
ms.openlocfilehash: 60ed93f1c1dc15e99465d969c9e4fd3e61c28ffa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="constructors"></a><span data-ttu-id="97a89-104">Costruttori</span><span class="sxs-lookup"><span data-stu-id="97a89-104">Constructors</span></span>

<span data-ttu-id="97a89-105">In questo argomento viene descritto come definire e utilizzare i costruttori per creare e inizializzare gli oggetti di classe e struttura.</span><span class="sxs-lookup"><span data-stu-id="97a89-105">This topic describes how to define and use constructors to create and initialize class and structure objects.</span></span>


## <a name="construction-of-class-objects"></a><span data-ttu-id="97a89-106">Costruzione di oggetti classe</span><span class="sxs-lookup"><span data-stu-id="97a89-106">Construction of Class Objects</span></span>
<span data-ttu-id="97a89-107">Gli oggetti di tipi di classe hanno costruttori.</span><span class="sxs-lookup"><span data-stu-id="97a89-107">Objects of class types have constructors.</span></span> <span data-ttu-id="97a89-108">Esistono due tipi di costruttori.</span><span class="sxs-lookup"><span data-stu-id="97a89-108">There are two kinds of constructors.</span></span> <span data-ttu-id="97a89-109">Uno è il costruttore primario, i cui parametri sono inclusi tra parentesi subito dopo il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="97a89-109">One is the primary constructor, whose parameters appear in parentheses just after the type name.</span></span> <span data-ttu-id="97a89-110">Specificare gli altri costruttori aggiuntivi facoltativi utilizzando il `new` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="97a89-110">You specify other, optional additional constructors by using the `new` keyword.</span></span> <span data-ttu-id="97a89-111">Qualsiasi costruttore aggiuntivo devono chiamare il costruttore primario.</span><span class="sxs-lookup"><span data-stu-id="97a89-111">Any such additional constructors must call the primary constructor.</span></span>

<span data-ttu-id="97a89-112">Il costruttore primario contiene `let` e `do` associazioni che vengono visualizzati all'inizio della definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="97a89-112">The primary constructor contains `let` and `do` bindings that appear at the start of the class definition.</span></span> <span data-ttu-id="97a89-113">Oggetto `let` binding dichiara i campi privati e i metodi della classe; un `do` associazione esegue il codice.</span><span class="sxs-lookup"><span data-stu-id="97a89-113">A `let` binding declares private fields and methods of the class; a `do` binding executes code.</span></span> <span data-ttu-id="97a89-114">Per ulteriori informazioni su `let` associazioni nei costruttori di classe, vedere [ `let` associazioni nelle classi](let-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="97a89-114">For more information about `let` bindings in class constructors, see [`let` Bindings in Classes](let-bindings-in-classes.md).</span></span> <span data-ttu-id="97a89-115">Per ulteriori informazioni su `do` associazioni nei costruttori, vedere [ `do` associazioni nelle classi](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="97a89-115">For more information about `do` bindings in constructors, see [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

<span data-ttu-id="97a89-116">Indipendentemente dal fatto che il costruttore da chiamare sia un costruttore primario o un costruttore aggiuntivo, è possibile creare oggetti usando una `new` espressione, con o senza l'opzione facoltativa `new` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="97a89-116">Regardless of whether the constructor you want to call is a primary constructor or an additional constructor, you can create objects by using a `new` expression, with or without the optional `new` keyword.</span></span> <span data-ttu-id="97a89-117">Inizializzare gli oggetti con gli argomenti del costruttore, elencando gli argomenti nell'ordine e separati da virgole e racchiuso tra parentesi o utilizzando gli argomenti denominati e i valori tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="97a89-117">You initialize your objects together with constructor arguments, either by listing the arguments in order and separated by commas and enclosed in parentheses, or by using named arguments and values in parentheses.</span></span> <span data-ttu-id="97a89-118">È inoltre possibile impostare proprietà su un oggetto durante la costruzione dell'oggetto usando i nomi delle proprietà e l'assegnazione di valori come si utilizzano denominato gli argomenti del costruttore.</span><span class="sxs-lookup"><span data-stu-id="97a89-118">You can also set properties on an object during the construction of the object by using the property names and assigning values just as you use named constructor arguments.</span></span>

<span data-ttu-id="97a89-119">Il codice seguente viene illustrata una classe che ha un costruttore e diverse modalità di creazione di oggetti.</span><span class="sxs-lookup"><span data-stu-id="97a89-119">The following code illustrates a class that has a constructor and various ways of creating objects.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

<span data-ttu-id="97a89-120">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="97a89-120">The output is as follows.</span></span>

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a><span data-ttu-id="97a89-121">Costruzione di strutture</span><span class="sxs-lookup"><span data-stu-id="97a89-121">Construction of Structures</span></span>
<span data-ttu-id="97a89-122">Le strutture seguono tutte le regole delle classi.</span><span class="sxs-lookup"><span data-stu-id="97a89-122">Structures follow all the rules of classes.</span></span> <span data-ttu-id="97a89-123">Pertanto, è possibile avere un costruttore primario e fornire costruttori aggiuntivi utilizzando `new`.</span><span class="sxs-lookup"><span data-stu-id="97a89-123">Therefore, you can have a primary constructor, and you can provide additional constructors by using `new`.</span></span> <span data-ttu-id="97a89-124">Tuttavia, è una differenza importante tra classi e strutture: le strutture possono disporre di un costruttore predefinito (vale a dire uno senza argomenti) anche se è definito alcun costruttore primario.</span><span class="sxs-lookup"><span data-stu-id="97a89-124">However, there is one important difference between structures and classes: structures can have a default constructor (that is, one with no arguments) even if no primary constructor is defined.</span></span> <span data-ttu-id="97a89-125">Il costruttore predefinito inizializza tutti i campi per il valore predefinito per tale tipo, generalmente zero o equivalente.</span><span class="sxs-lookup"><span data-stu-id="97a89-125">The default constructor initializes all the fields to the default value for that type, usually zero or its equivalent.</span></span> <span data-ttu-id="97a89-126">Costruttori definiti per le strutture devono avere almeno un argomento in modo che non entrino in conflitto con il costruttore predefinito.</span><span class="sxs-lookup"><span data-stu-id="97a89-126">Any constructors that you define for structures must have at least one argument so that they do not conflict with the default constructor.</span></span>

<span data-ttu-id="97a89-127">Strutture, inoltre, hanno spesso i campi che vengono creati utilizzando il `val` (parola chiave); le classi possono disporre anche di questi campi.</span><span class="sxs-lookup"><span data-stu-id="97a89-127">Also, structures often have fields that are created by using the `val` keyword; classes can also have these fields.</span></span> <span data-ttu-id="97a89-128">Strutture e classi che dispongono di campi definiti tramite il `val` parola chiave può inoltre essere inizializzati in costruttori aggiuntivi utilizzando espressioni di record, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="97a89-128">Structures and classes that have fields defined by using the `val` keyword can also be initialized in additional constructors by using record expressions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

<span data-ttu-id="97a89-129">Per ulteriori informazioni, vedere [campi espliciti: il `val` parola chiave](explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="97a89-129">For more information, see [Explicit Fields: The `val` Keyword](explicit-fields-the-val-keyword.md).</span></span>


## <a name="executing-side-effects-in-constructors"></a><span data-ttu-id="97a89-130">L'esecuzione di effetti collaterali nei costruttori</span><span class="sxs-lookup"><span data-stu-id="97a89-130">Executing Side Effects in Constructors</span></span>
<span data-ttu-id="97a89-131">Un costruttore primario in una classe può eseguire codice in un `do` associazione.</span><span class="sxs-lookup"><span data-stu-id="97a89-131">A primary constructor in a class can execute code in a `do` binding.</span></span> <span data-ttu-id="97a89-132">Tuttavia, se è necessario eseguire codice in un costruttore aggiuntivo, senza un `do` associazione?</span><span class="sxs-lookup"><span data-stu-id="97a89-132">However, what if you have to execute code in an additional constructor, without a `do` binding?</span></span> <span data-ttu-id="97a89-133">A tale scopo, utilizzare il `then` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="97a89-133">To do this, you use the `then` keyword.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

<span data-ttu-id="97a89-134">Eseguire comunque gli effetti collaterali del costruttore primario.</span><span class="sxs-lookup"><span data-stu-id="97a89-134">The side effects of the primary constructor still execute.</span></span> <span data-ttu-id="97a89-135">Di conseguenza, l'output è il seguente.</span><span class="sxs-lookup"><span data-stu-id="97a89-135">Therefore, the output is as follows.</span></span>

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a><span data-ttu-id="97a89-136">Autoidentificatori nei costruttori</span><span class="sxs-lookup"><span data-stu-id="97a89-136">Self Identifiers in Constructors</span></span>
<span data-ttu-id="97a89-137">Negli altri membri, fornire un nome per l'oggetto corrente nella definizione di ogni membro.</span><span class="sxs-lookup"><span data-stu-id="97a89-137">In other members, you provide a name for the current object in the definition of each member.</span></span> <span data-ttu-id="97a89-138">È anche possibile inserire l'autoidentificatore nella prima riga della definizione della classe utilizzando il `as` parola chiave immediatamente dopo i parametri del costruttore.</span><span class="sxs-lookup"><span data-stu-id="97a89-138">You can also put the self identifier on the first line of the class definition by using the `as` keyword immediately following the constructor parameters.</span></span> <span data-ttu-id="97a89-139">Nell'esempio seguente viene illustrata questa sintassi.</span><span class="sxs-lookup"><span data-stu-id="97a89-139">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

<span data-ttu-id="97a89-140">Nei costruttori aggiuntivi, è anche possibile definire un autoidentificatore inserendo il `as` clausola subito dopo i parametri del costruttore.</span><span class="sxs-lookup"><span data-stu-id="97a89-140">In additional constructors, you can also define a self identifier by putting the `as` clause right after the constructor parameters.</span></span> <span data-ttu-id="97a89-141">Nell'esempio seguente viene illustrata questa sintassi.</span><span class="sxs-lookup"><span data-stu-id="97a89-141">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

<span data-ttu-id="97a89-142">Problemi possono verificarsi quando si tenta di utilizzare un oggetto prima che sia definita completamente.</span><span class="sxs-lookup"><span data-stu-id="97a89-142">Problems can occur when you try to use an object before it is fully defined.</span></span> <span data-ttu-id="97a89-143">Pertanto, Usa dello stesso identificatore può causare al compilatore di generare un avviso e l'inserimento di controlli aggiuntivi per assicurarsi che i membri di un oggetto non si accede prima l'oggetto viene inizializzato.</span><span class="sxs-lookup"><span data-stu-id="97a89-143">Therefore, uses of the self identifier can cause the compiler to emit a warning and insert additional checks to ensure the members of an object are not accessed before the object is initialized.</span></span> <span data-ttu-id="97a89-144">Utilizzare solo l'autoidentificatore nella `do` associazioni del costruttore primario o dopo il `then` (parola chiave) nei costruttori aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="97a89-144">You should only use the self identifier in the `do` bindings of the primary constructor, or after the `then` keyword in additional constructors.</span></span>

<span data-ttu-id="97a89-145">Il nome dello stesso identificatore non deve essere `this`.</span><span class="sxs-lookup"><span data-stu-id="97a89-145">The name of the self identifier does not have to be `this`.</span></span> <span data-ttu-id="97a89-146">Può essere qualsiasi identificatore valido.</span><span class="sxs-lookup"><span data-stu-id="97a89-146">It can be any valid identifier.</span></span>


## <a name="assigning-values-to-properties-at-initialization"></a><span data-ttu-id="97a89-147">L'assegnazione di valori alle proprietà in fase di inizializzazione</span><span class="sxs-lookup"><span data-stu-id="97a89-147">Assigning Values to Properties at Initialization</span></span>
<span data-ttu-id="97a89-148">È possibile assegnare valori alle proprietà di un oggetto di classe nel codice di inizializzazione aggiungendo un elenco di assegnazioni nel formato `property = value` all'elenco di argomenti per un costruttore.</span><span class="sxs-lookup"><span data-stu-id="97a89-148">You can assign values to the properties of a class object in the initialization code by appending a list of assignments of the form `property = value` to the argument list for a constructor.</span></span> <span data-ttu-id="97a89-149">Queste operazioni sono illustrate nell'esempio di codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="97a89-149">This is shown in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="97a89-150">La seguente versione del codice precedente viene illustrata la combinazione di argomenti normali, gli argomenti facoltativi e le impostazioni delle proprietà nella chiamata di un costruttore.</span><span class="sxs-lookup"><span data-stu-id="97a89-150">The following version of the previous code illustrates the combination of ordinary arguments, optional arguments, and property settings in one constructor call.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]
    
## <a name="constructors-in-inherited-class"></a><span data-ttu-id="97a89-151">Costruttori di classe ereditata</span><span class="sxs-lookup"><span data-stu-id="97a89-151">Constructors in inherited class</span></span>
<span data-ttu-id="97a89-152">Quando si eredita da una classe di base che ha un costruttore, è necessario specificare gli argomenti nella clausola eredita.</span><span class="sxs-lookup"><span data-stu-id="97a89-152">When inheriting from a base class that has a constructor, you must specify its arguments in the inherit clause.</span></span> <span data-ttu-id="97a89-153">Per ulteriori informazioni, vedere [costruttori ed ereditarietà](../inheritance.md#constructors-and-inheritance).</span><span class="sxs-lookup"><span data-stu-id="97a89-153">For more information, see [Constructors and inheritance](../inheritance.md#constructors-and-inheritance).</span></span>

## <a name="static-constructors-or-type-constructors"></a><span data-ttu-id="97a89-154">Costruttori statici o costruttori di tipo</span><span class="sxs-lookup"><span data-stu-id="97a89-154">Static Constructors or Type Constructors</span></span>
<span data-ttu-id="97a89-155">Oltre a specificare il codice per la creazione di oggetti, statici `let` e `do` associazioni possono essere create in tipi di classe da eseguire prima che il tipo viene innanzitutto utilizzato per eseguire l'inizializzazione a livello di tipo.</span><span class="sxs-lookup"><span data-stu-id="97a89-155">In addition to specifying code for creating objects, static `let` and `do` bindings can be authored in class types that execute before the type is first used to perform initialization at the type level.</span></span> <span data-ttu-id="97a89-156">Per ulteriori informazioni, vedere [ `let` associazioni nelle classi](let-bindings-in-classes.md) e [ `do` associazioni nelle classi](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="97a89-156">For more information, see [`let` Bindings in Classes](let-bindings-in-classes.md) and [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="97a89-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97a89-157">See Also</span></span>
[<span data-ttu-id="97a89-158">Membri</span><span class="sxs-lookup"><span data-stu-id="97a89-158">Members</span></span>](index.md)

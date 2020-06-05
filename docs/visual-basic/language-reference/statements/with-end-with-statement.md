---
title: Istruzione With...End With
ms.date: 07/20/2015
f1_keywords:
- vb.With
helpviewer_keywords:
- With keyword [Visual Basic]
- loop structures [Visual Basic], and With...End With statements
- execution [Visual Basic], on object
- instructions, repeating
- With...End With statements [Visual Basic]
- With statement [Visual Basic]
- With statement [Visual Basic], nesting
- objects [Visual Basic], accessing
- With block
- End keyword [Visual Basic], With...End With statements
ms.assetid: 340d5fbb-4f43-48ec-a024-80843c137817
ms.openlocfilehash: 50f3bd0c6e96254274b429794901e2e4ac719ad0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401381"
---
# <a name="withend-with-statement-visual-basic"></a><span data-ttu-id="4b449-102">Istruzione With...End With (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b449-102">With...End With Statement (Visual Basic)</span></span>

<span data-ttu-id="4b449-103">Esegue una serie di istruzioni che fanno riferimento più volte a un singolo oggetto o struttura in modo da poter utilizzare una sintassi semplificata per le istruzioni quando si accede ai membri dell'oggetto o della struttura.</span><span class="sxs-lookup"><span data-stu-id="4b449-103">Executes a series of statements that repeatedly refer to a single object or structure so that the statements can use a simplified syntax when accessing members of the object or structure.</span></span>  <span data-ttu-id="4b449-104">Quando si utilizza una struttura, è possibile leggere solo i valori dei membri o i metodi invoke e ottenere un errore se si tenta di assegnare valori ai membri di una struttura utilizzata in un'istruzione `With...End With`.</span><span class="sxs-lookup"><span data-stu-id="4b449-104">When using a structure, you can only read the values of members or invoke methods, and you get an error if you try to assign values to members of a structure used in a `With...End With` statement.</span></span>

## <a name="syntax"></a><span data-ttu-id="4b449-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b449-105">Syntax</span></span>

```vb
With objectExpression
    [ statements ]
End With
```

## <a name="parts"></a><span data-ttu-id="4b449-106">Parti</span><span class="sxs-lookup"><span data-stu-id="4b449-106">Parts</span></span>

|<span data-ttu-id="4b449-107">Termine</span><span class="sxs-lookup"><span data-stu-id="4b449-107">Term</span></span>|<span data-ttu-id="4b449-108">Definizione</span><span class="sxs-lookup"><span data-stu-id="4b449-108">Definition</span></span>|
|---|---|
|`objectExpression`|<span data-ttu-id="4b449-109">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4b449-109">Required.</span></span> <span data-ttu-id="4b449-110">Espressione che restituisce un oggetto.</span><span class="sxs-lookup"><span data-stu-id="4b449-110">An expression that evaluates to an object.</span></span> <span data-ttu-id="4b449-111">L'espressione può essere arbitrariamente complessa ed essere valutata solo una volta.</span><span class="sxs-lookup"><span data-stu-id="4b449-111">The expression may be arbitrarily complex and is evaluated only once.</span></span> <span data-ttu-id="4b449-112">Può restituire qualsiasi tipo di dati, compresi i tipi di base.</span><span class="sxs-lookup"><span data-stu-id="4b449-112">The expression can evaluate to any data type, including elementary types.</span></span>|
|`statements`|<span data-ttu-id="4b449-113">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="4b449-113">Optional.</span></span> <span data-ttu-id="4b449-114">Una o più istruzioni tra `With` e `End With` che possono fare riferimento ai membri di un oggetto che verrà prodotto dalla valutazione di `objectExpression`.</span><span class="sxs-lookup"><span data-stu-id="4b449-114">One or more statements between `With` and `End With` that may refer to members of an object that's produced by the evaluation of `objectExpression`.</span></span>|
|`End With`|<span data-ttu-id="4b449-115">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4b449-115">Required.</span></span> <span data-ttu-id="4b449-116">Termina la definizione del blocco `With`.</span><span class="sxs-lookup"><span data-stu-id="4b449-116">Terminates the definition of the `With` block.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4b449-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="4b449-117">Remarks</span></span>

<span data-ttu-id="4b449-118">Utilizzando `With...End With`, è possibile eseguire una serie di istruzioni in un oggetto specificato senza specificare il nome dell'oggetto più volte.</span><span class="sxs-lookup"><span data-stu-id="4b449-118">By using `With...End With`, you can perform a series of statements on a specified object without specifying the name of the object multiple times.</span></span> <span data-ttu-id="4b449-119">All'interno di un blocco di istruzioni `With`, è possibile specificare un membro dell'oggetto che inizia con un punto, come se l'oggetto dell'istruzione `With` lo precedesse.</span><span class="sxs-lookup"><span data-stu-id="4b449-119">Within a `With` statement block, you can specify a member of the object starting with a period, as if the `With` statement object preceded it.</span></span>

<span data-ttu-id="4b449-120">Per modificare più proprietà in un singolo oggetto, ad esempio, è possibile inserire le istruzioni di assegnazione delle proprietà all'interno del blocco `With...End With`, facendo riferimento all'oggetto una sola volta anziché una volta per assegnazione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="4b449-120">For example, to change multiple properties on a single object, place the property assignment statements inside the `With...End With` block, referring to the object only once instead of once for each property assignment.</span></span>

<span data-ttu-id="4b449-121">Se il codice accede allo stesso oggetto in più istruzioni, utilizzando l'istruzione di `With` si ottengono i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b449-121">If your code accesses the same object in multiple statements, you gain the following benefits by using the `With` statement:</span></span>

- <span data-ttu-id="4b449-122">Non è necessario valutare più volte un'espressione complessa o assegnare il risultato a una variabile temporanea per fare riferimento ai membri più volte.</span><span class="sxs-lookup"><span data-stu-id="4b449-122">You don't need to evaluate a complex expression multiple times or assign the result to a temporary variable to refer to its members multiple times.</span></span>

- <span data-ttu-id="4b449-123">È possibile rendere il codice più leggibile eliminando le espressioni di qualificazione ripetitive.</span><span class="sxs-lookup"><span data-stu-id="4b449-123">You make your code more readable by eliminating repetitive qualifying expressions.</span></span>

<span data-ttu-id="4b449-124">Il tipo di dati `objectExpression` può essere qualsiasi tipo di classe o struttura o anche un tipo elementare di Visual Basic come `Integer`.</span><span class="sxs-lookup"><span data-stu-id="4b449-124">The data type of `objectExpression` can be any class or structure type or even a Visual Basic elementary type such as `Integer`.</span></span>  <span data-ttu-id="4b449-125">Se `objectExpression` restituisce qualcosa di diverso da un oggetto, è possibile leggere solo i valori dei membri o i metodi invoke e ottenere un errore se si tenta di assegnare valori ai membri di una struttura utilizzata in un'istruzione `With...End With`.</span><span class="sxs-lookup"><span data-stu-id="4b449-125">If `objectExpression` results in anything other than an object, you can only read the values of its members or invoke methods, and you get an error if you try to assign values to members of a structure used in a `With...End With` statement.</span></span>  <span data-ttu-id="4b449-126">Si tratta dello stesso errore che si otterrebbe se viene richiamato un metodo che restituisce una struttura e immediatamente si accede e si assegna un valore a un membro del risultato della funzione, come `GetAPoint().x = 1`.</span><span class="sxs-lookup"><span data-stu-id="4b449-126">This is the same error you would get if you invoked a method that returned a structure and immediately accessed and assigned a value to a member of the function’s result, such as `GetAPoint().x = 1`.</span></span>  <span data-ttu-id="4b449-127">Il problema in entrambi i casi è che la struttura esiste solo nello stack di chiamate e in nessun caso un membro di una struttura modificata in tali situazioni può scrivere in una posizione in modo che altro codice del programma può osservare la modifica.</span><span class="sxs-lookup"><span data-stu-id="4b449-127">The problem in both cases is that the structure exists only on the call stack, and there is no way a modified structure member in these situations can write to  a location such that any other code in the program can observe the change.</span></span>

<span data-ttu-id="4b449-128">`objectExpression` viene valutato una volta, all'ingresso nel blocco.</span><span class="sxs-lookup"><span data-stu-id="4b449-128">The `objectExpression` is evaluated once, upon entry into the block.</span></span> <span data-ttu-id="4b449-129">Non è possibile riassegnare `objectExpression` dall'interno del blocco `With`.</span><span class="sxs-lookup"><span data-stu-id="4b449-129">You can't reassign the `objectExpression` from within the `With` block.</span></span>

<span data-ttu-id="4b449-130">Dal blocco `With`, è possibile accedere ai metodi e alle proprietà del solo oggetto specificato senza qualifica.</span><span class="sxs-lookup"><span data-stu-id="4b449-130">Within a `With` block, you can access the methods and properties of only the specified object without qualifying them.</span></span> <span data-ttu-id="4b449-131">Metodi e proprietà di altri oggetti possono essere utilizzati ma è necessario qualificarli con i relativi nomi di oggetto.</span><span class="sxs-lookup"><span data-stu-id="4b449-131">You can use methods and properties of other objects, but you must qualify them with their object names.</span></span>

<span data-ttu-id="4b449-132">È possibile inserire un'istruzione `With...End With` in un'altra.</span><span class="sxs-lookup"><span data-stu-id="4b449-132">You can place one `With...End With` statement within another.</span></span> <span data-ttu-id="4b449-133">Le istruzioni `With...End With` annidate possono creare confusione se gli oggetti a cui si fa riferimento non sono chiari dal contesto.</span><span class="sxs-lookup"><span data-stu-id="4b449-133">Nested `With...End With` statements may be confusing if the objects that are being referred to aren't clear from context.</span></span> <span data-ttu-id="4b449-134">È necessario fornire un riferimento completo a un oggetto che si trova in un blocco `With` esterno quando si fa riferimento all'oggetto dal un blocco `With` interno.</span><span class="sxs-lookup"><span data-stu-id="4b449-134">You must provide a fully qualified reference to an object that's in an outer `With` block when the object is referenced from within an inner `With` block.</span></span>

<span data-ttu-id="4b449-135">Non è consentita la creazione di rami in un'istruzione `With` dall'esterno del blocco.</span><span class="sxs-lookup"><span data-stu-id="4b449-135">You can't branch into a `With` statement block from outside the block.</span></span>

<span data-ttu-id="4b449-136">A meno che il blocco non contenga un ciclo, le istruzioni vengono eseguite una sola volta.</span><span class="sxs-lookup"><span data-stu-id="4b449-136">Unless the block contains a loop, the statements run only once.</span></span> <span data-ttu-id="4b449-137">È possibile annidare tipi diversi di strutture di controllo.</span><span class="sxs-lookup"><span data-stu-id="4b449-137">You can nest different kinds of control structures.</span></span> <span data-ttu-id="4b449-138">Per altre informazioni, vedere [strutture di controlli annidati](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="4b449-138">For more information, see [Nested Control Structures](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4b449-139">È possibile utilizzare la parola chiave `With` anche negli inizializzatori di oggetto.</span><span class="sxs-lookup"><span data-stu-id="4b449-139">You can use the `With` keyword in object initializers also.</span></span> <span data-ttu-id="4b449-140">Per ulteriori informazioni ed esempi, vedere [inizializzatori di oggetto: tipi denominati e anonimi](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) e [tipi anonimi](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="4b449-140">For more information and examples, see [Object Initializers: Named and Anonymous Types](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) and [Anonymous Types](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>
>
> <span data-ttu-id="4b449-141">Se si utilizza un blocco `With` solo per inizializzare le proprietà o i campi di un oggetto di cui è stata appena creata un'istanza, è possibile utilizzare un inizializzatore di oggetto.</span><span class="sxs-lookup"><span data-stu-id="4b449-141">If you're using a `With` block only to initialize the properties or fields of an object that you've just instantiated, consider using an object initializer instead.</span></span>

## <a name="example"></a><span data-ttu-id="4b449-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="4b449-142">Example</span></span>

<span data-ttu-id="4b449-143">Nell'esempio riportato di seguito, ogni blocco `With` esegue una serie di istruzioni su un singolo oggetto.</span><span class="sxs-lookup"><span data-stu-id="4b449-143">In the following example, each `With` block executes a series of statements on a single object.</span></span>

[!code-vb[VbVbalrWithStatement#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrwithstatement/vb/mainwindow.xaml.vb#2)]

## <a name="example"></a><span data-ttu-id="4b449-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="4b449-144">Example</span></span>

<span data-ttu-id="4b449-145">Nell'esempio seguente vengono annidate le istruzioni `With…End With`.</span><span class="sxs-lookup"><span data-stu-id="4b449-145">The following example nests `With…End With` statements.</span></span> <span data-ttu-id="4b449-146">Nell'istruzione `With` annidata, la sintassi fa riferimento all'oggetto interno.</span><span class="sxs-lookup"><span data-stu-id="4b449-146">Within the nested `With` statement, the syntax refers to the inner object.</span></span>

[!code-vb[VbVbalrWithStatement#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrwithstatement/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="4b449-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b449-147">See also</span></span>

- <xref:System.Collections.Generic.List%601>
- [<span data-ttu-id="4b449-148">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="4b449-148">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="4b449-149">Inizializzatori di oggetto: tipi denominati e tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="4b449-149">Object Initializers: Named and Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="4b449-150">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="4b449-150">Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)

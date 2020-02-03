---
title: Dim (istruzione)
ms.date: 05/12/2018
f1_keywords:
- vb.Dim
- Dim
helpviewer_keywords:
- Public keyword [Visual Basic], in Dim statement
- Dim statement [Visual Basic]
- fixed-length strings [Visual Basic], declaring
- variables [Visual Basic], declaring
- WithEvents keyword [Visual Basic], Dim statement
- dynamic arrays [Visual Basic], Dim statement
- variables [Visual Basic], initializing
- '{} braces'
- fields [Visual Basic], as member variables
- declarations [Visual Basic], dynamic arrays
- member variables [Visual Basic]
- default values [Visual Basic]
- data types [Visual Basic], assigning
- braces {}
- As keyword [Visual Basic], in Dim statement
- arrays [Visual Basic], declaring
- New keyword [Visual Basic], Dim statement
- To keyword [Visual Basic], in Dim statement
- storage [Visual Basic], allocating
- local variables [Visual Basic]
- declaration statements [Visual Basic]
- Dim statement [Visual Basic], syntax
- variables [Visual Basic], member and local
ms.assetid: fae3eca1-f0b2-4400-994b-7aa58a848448
ms.openlocfilehash: 1b0c3089c366c417af926c8c0703cea021674432
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744731"
---
# <a name="dim-statement-visual-basic"></a><span data-ttu-id="a6d99-102">Istruzione Dim (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6d99-102">Dim statement (Visual Basic)</span></span>

<span data-ttu-id="a6d99-103">Dichiara e alloca lo spazio di archiviazione per una o più variabili.</span><span class="sxs-lookup"><span data-stu-id="a6d99-103">Declares and allocates storage space for one or more variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="a6d99-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6d99-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]
Dim [ WithEvents ] variablelist
```

## <a name="parts"></a><span data-ttu-id="a6d99-105">Parti</span><span class="sxs-lookup"><span data-stu-id="a6d99-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="a6d99-106">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a6d99-106">Optional.</span></span> <span data-ttu-id="a6d99-107">Vedere [elenco attributi](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="a6d99-107">See [Attribute List](attribute-list.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="a6d99-108">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a6d99-108">Optional.</span></span> <span data-ttu-id="a6d99-109">Può essere uno dei collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a6d99-109">Can be one of the following:</span></span>

  - [<span data-ttu-id="a6d99-110">Public</span><span class="sxs-lookup"><span data-stu-id="a6d99-110">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="a6d99-111">Protected</span><span class="sxs-lookup"><span data-stu-id="a6d99-111">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="a6d99-112">Friend</span><span class="sxs-lookup"><span data-stu-id="a6d99-112">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="a6d99-113">Private</span><span class="sxs-lookup"><span data-stu-id="a6d99-113">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="a6d99-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="a6d99-114">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="a6d99-115">Private Protected</span><span class="sxs-lookup"><span data-stu-id="a6d99-115">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="a6d99-116">Vedere [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a6d99-116">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `Shared`

  <span data-ttu-id="a6d99-117">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a6d99-117">Optional.</span></span> <span data-ttu-id="a6d99-118">Vedere [Shared](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="a6d99-118">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="a6d99-119">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a6d99-119">Optional.</span></span> <span data-ttu-id="a6d99-120">Vedere [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="a6d99-120">See [Shadows](../modifiers/shadows.md).</span></span>

- `Static`

  <span data-ttu-id="a6d99-121">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a6d99-121">Optional.</span></span> <span data-ttu-id="a6d99-122">Vedere [static](../modifiers/static.md).</span><span class="sxs-lookup"><span data-stu-id="a6d99-122">See [Static](../modifiers/static.md).</span></span>

- `ReadOnly`

  <span data-ttu-id="a6d99-123">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a6d99-123">Optional.</span></span> <span data-ttu-id="a6d99-124">Vedere [ReadOnly](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="a6d99-124">See [ReadOnly](../modifiers/readonly.md).</span></span>

- `WithEvents`

  <span data-ttu-id="a6d99-125">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a6d99-125">Optional.</span></span> <span data-ttu-id="a6d99-126">Specifica che si tratta di variabili oggetto che fanno riferimento a istanze di una classe in grado di generare eventi.</span><span class="sxs-lookup"><span data-stu-id="a6d99-126">Specifies that these are object variables that refer to instances of a class that can raise events.</span></span> <span data-ttu-id="a6d99-127">Vedere [WithEvents](../modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="a6d99-127">See [WithEvents](../modifiers/withevents.md).</span></span>

- `variablelist`

  <span data-ttu-id="a6d99-128">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="a6d99-128">Required.</span></span> <span data-ttu-id="a6d99-129">Elenco delle variabili dichiarate in questa istruzione.</span><span class="sxs-lookup"><span data-stu-id="a6d99-129">List of variables being declared in this statement.</span></span>

  `variable [ , variable ... ]`

  <span data-ttu-id="a6d99-130">Ogni `variable` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a6d99-130">Each `variable` has the following syntax and parts:</span></span>

  <span data-ttu-id="a6d99-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="a6d99-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span></span>

  |<span data-ttu-id="a6d99-132">Parte</span><span class="sxs-lookup"><span data-stu-id="a6d99-132">Part</span></span>|<span data-ttu-id="a6d99-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6d99-133">Description</span></span>|
  |---|---|
  |`variablename`|<span data-ttu-id="a6d99-134">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="a6d99-134">Required.</span></span> <span data-ttu-id="a6d99-135">Nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="a6d99-135">Name of the variable.</span></span> <span data-ttu-id="a6d99-136">Vedere [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="a6d99-136">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
  |`boundslist`|<span data-ttu-id="a6d99-137">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a6d99-137">Optional.</span></span> <span data-ttu-id="a6d99-138">Elenco di limiti di ogni dimensione di una variabile di matrice.</span><span class="sxs-lookup"><span data-stu-id="a6d99-138">List of bounds of each dimension of an array variable.</span></span>|
  |`New`|<span data-ttu-id="a6d99-139">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a6d99-139">Optional.</span></span> <span data-ttu-id="a6d99-140">Crea una nuova istanza della classe quando viene eseguita l'istruzione `Dim`.</span><span class="sxs-lookup"><span data-stu-id="a6d99-140">Creates a new instance of the class when the `Dim` statement runs.</span></span>|
  |`datatype`|<span data-ttu-id="a6d99-141">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a6d99-141">Optional.</span></span> <span data-ttu-id="a6d99-142">Tipo di dati della variabile.</span><span class="sxs-lookup"><span data-stu-id="a6d99-142">Data type of the variable.</span></span>|
  |`With`|<span data-ttu-id="a6d99-143">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a6d99-143">Optional.</span></span> <span data-ttu-id="a6d99-144">Introduce l'elenco di inizializzatori di oggetto.</span><span class="sxs-lookup"><span data-stu-id="a6d99-144">Introduces the object initializer list.</span></span>|
  |`propertyname`|<span data-ttu-id="a6d99-145">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a6d99-145">Optional.</span></span> <span data-ttu-id="a6d99-146">Nome di una proprietà nella classe di cui si sta creando un'istanza.</span><span class="sxs-lookup"><span data-stu-id="a6d99-146">The name of a property in the class you are making an instance of.</span></span>|
  |`propinitializer`|<span data-ttu-id="a6d99-147">Obbligatorio dopo `propertyname` =.</span><span class="sxs-lookup"><span data-stu-id="a6d99-147">Required after `propertyname` =.</span></span> <span data-ttu-id="a6d99-148">Espressione valutata e assegnata al nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="a6d99-148">The expression that is evaluated and assigned to the property name.</span></span>|
  |`initializer`|<span data-ttu-id="a6d99-149">Facoltativo se `New` non è specificato.</span><span class="sxs-lookup"><span data-stu-id="a6d99-149">Optional if `New` is not specified.</span></span> <span data-ttu-id="a6d99-150">Espressione valutata e assegnata alla variabile al momento della creazione.</span><span class="sxs-lookup"><span data-stu-id="a6d99-150">Expression that is evaluated and assigned to the variable when it is created.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a6d99-151">Note</span><span class="sxs-lookup"><span data-stu-id="a6d99-151">Remarks</span></span>

<span data-ttu-id="a6d99-152">Il compilatore Visual Basic utilizza l'istruzione `Dim` per determinare il tipo di dati della variabile e altre informazioni, ad esempio il codice che può accedere alla variabile.</span><span class="sxs-lookup"><span data-stu-id="a6d99-152">The Visual Basic compiler uses the `Dim` statement to determine the variable's data type and other information, such as what code can access the variable.</span></span> <span data-ttu-id="a6d99-153">Nell'esempio seguente viene dichiarata una variabile per includere un valore `Integer`.</span><span class="sxs-lookup"><span data-stu-id="a6d99-153">The following example declares a variable to hold an `Integer` value.</span></span>

```vb
Dim numberOfStudents As Integer
```

<span data-ttu-id="a6d99-154">È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, una struttura, una classe o un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a6d99-154">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>

```vb
Dim finished As Boolean
Dim monitorBox As System.Windows.Forms.Form
```

<span data-ttu-id="a6d99-155">Per un tipo riferimento, usare la parola chiave `New` per creare una nuova istanza della classe o della struttura specificata dal tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="a6d99-155">For a reference type, you use the `New` keyword to create a new instance of the class or structure that is specified by the data type.</span></span> <span data-ttu-id="a6d99-156">Se si utilizza `New`, non viene utilizzata un'espressione di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="a6d99-156">If you use `New`, you do not use an initializer expression.</span></span> <span data-ttu-id="a6d99-157">Vengono invece forniti gli argomenti, se necessari, al costruttore della classe da cui si crea la variabile.</span><span class="sxs-lookup"><span data-stu-id="a6d99-157">Instead, you supply arguments, if they are required, to the constructor of the class from which you are creating the variable.</span></span>

```vb
Dim bottomLabel As New System.Windows.Forms.Label
```

<span data-ttu-id="a6d99-158">È possibile dichiarare una variabile in una routine, un blocco, una classe, una struttura o un modulo.</span><span class="sxs-lookup"><span data-stu-id="a6d99-158">You can declare a variable in a procedure, block, class, structure, or module.</span></span> <span data-ttu-id="a6d99-159">Non è possibile dichiarare una variabile in un file di origine, uno spazio dei nomi o un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a6d99-159">You cannot declare a variable in a source file, namespace, or interface.</span></span> <span data-ttu-id="a6d99-160">Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a6d99-160">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="a6d99-161">Una variabile dichiarata a livello di modulo, all'esterno di qualsiasi routine, è una *variabile membro* o un *campo*.</span><span class="sxs-lookup"><span data-stu-id="a6d99-161">A variable that is declared at module level, outside any procedure, is a *member variable* or *field*.</span></span> <span data-ttu-id="a6d99-162">Le variabili membro sono nell'ambito della classe, della struttura o del modulo.</span><span class="sxs-lookup"><span data-stu-id="a6d99-162">Member variables are in scope throughout their class, structure, or module.</span></span> <span data-ttu-id="a6d99-163">Una variabile dichiarata a livello di routine è una *variabile locale*.</span><span class="sxs-lookup"><span data-stu-id="a6d99-163">A variable that is declared at procedure level is a *local variable*.</span></span> <span data-ttu-id="a6d99-164">Le variabili locali si trovano nell'ambito solo all'interno della routine o del blocco.</span><span class="sxs-lookup"><span data-stu-id="a6d99-164">Local variables are in scope only within their procedure or block.</span></span>

<span data-ttu-id="a6d99-165">I modificatori di accesso seguenti vengono utilizzati per dichiarare le variabili all'esterno di una routine: `Public`, `Protected`, `Friend`, `Protected Friend`e `Private`.</span><span class="sxs-lookup"><span data-stu-id="a6d99-165">The following access modifiers are used to declare variables outside a procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private`.</span></span> <span data-ttu-id="a6d99-166">Per altre informazioni, vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a6d99-166">For more information, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="a6d99-167">La parola chiave `Dim` è facoltativa e in genere omessa se si specifica uno dei modificatori seguenti: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`o `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="a6d99-167">The `Dim` keyword is optional and usually omitted if you specify any of the following modifiers: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, or `WithEvents`.</span></span>

```vb
Public maximumAllowed As Double
Protected Friend currentUserName As String
Private salary As Decimal
Static runningTotal As Integer
```

<span data-ttu-id="a6d99-168">Se `Option Explicit` è on (impostazione predefinita), il compilatore richiede una dichiarazione per ogni variabile utilizzata.</span><span class="sxs-lookup"><span data-stu-id="a6d99-168">If `Option Explicit` is on (the default), the compiler requires a declaration for every variable you use.</span></span> <span data-ttu-id="a6d99-169">Per altre informazioni, vedere [istruzione Option Explicit](option-explicit-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a6d99-169">For more information, see [Option Explicit Statement](option-explicit-statement.md).</span></span>

## <a name="specifying-an-initial-value"></a><span data-ttu-id="a6d99-170">Specifica di un valore iniziale</span><span class="sxs-lookup"><span data-stu-id="a6d99-170">Specifying an initial value</span></span>

<span data-ttu-id="a6d99-171">È possibile assegnare un valore a una variabile al momento della creazione.</span><span class="sxs-lookup"><span data-stu-id="a6d99-171">You can assign a value to a variable when it is created.</span></span> <span data-ttu-id="a6d99-172">Per un tipo di valore, si usa un *inizializzatore* per fornire un'espressione da assegnare alla variabile.</span><span class="sxs-lookup"><span data-stu-id="a6d99-172">For a value type, you use an *initializer* to supply an expression to be assigned to the variable.</span></span> <span data-ttu-id="a6d99-173">L'espressione deve restituire una costante che può essere calcolata in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a6d99-173">The expression must evaluate to a constant that can be calculated at compile time.</span></span>

```vb
Dim quantity As Integer = 10
Dim message As String = "Just started"
```

<span data-ttu-id="a6d99-174">Se viene specificato un inizializzatore e non viene specificato un tipo di dati in una clausola `As`, viene utilizzata l' *inferenza del tipo* per dedurre il tipo di dati dall'inizializzatore.</span><span class="sxs-lookup"><span data-stu-id="a6d99-174">If an initializer is specified and a data type is not specified in an `As` clause, *type inference* is used to infer the data type from the initializer.</span></span> <span data-ttu-id="a6d99-175">Nell'esempio seguente `num1` e `num2` sono fortemente tipizzati come numeri interi.</span><span class="sxs-lookup"><span data-stu-id="a6d99-175">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span> <span data-ttu-id="a6d99-176">Nella seconda dichiarazione, l'inferenza del tipo deduce il tipo dal valore 3.</span><span class="sxs-lookup"><span data-stu-id="a6d99-176">In the second declaration, type inference infers the type from the value 3.</span></span>

```vb
' Use explicit typing.
Dim num1 As Integer = 3

' Use local type inference.
Dim num2 = 3
```

<span data-ttu-id="a6d99-177">L'inferenza del tipo si applica a livello di routine.</span><span class="sxs-lookup"><span data-stu-id="a6d99-177">Type inference applies at the procedure level.</span></span> <span data-ttu-id="a6d99-178">Non si applica all'esterno di una routine in una classe, una struttura, un modulo o un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a6d99-178">It does not apply outside a procedure in a class, structure, module, or interface.</span></span> <span data-ttu-id="a6d99-179">Per ulteriori informazioni sull'inferenza del tipo, vedere l' [istruzione Option deduce](option-infer-statement.md) e l' [inferenza del tipo locale](../../programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="a6d99-179">For more information about type inference, see [Option Infer Statement](option-infer-statement.md) and [Local Type Inference](../../programming-guide/language-features/variables/local-type-inference.md).</span></span>

<span data-ttu-id="a6d99-180">Per informazioni su cosa accade quando un tipo di dati o un inizializzatore non viene specificato, vedere [valori e tipi di dati predefiniti](dim-statement.md#default) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a6d99-180">For information about what happens when a data type or initializer is not specified, see [Default Data Types and Values](dim-statement.md#default) later in this topic.</span></span>

<span data-ttu-id="a6d99-181">È possibile utilizzare un *inizializzatore di oggetto* per dichiarare istanze di tipi denominati e anonimi.</span><span class="sxs-lookup"><span data-stu-id="a6d99-181">You can use an *object initializer* to declare instances of named and anonymous types.</span></span> <span data-ttu-id="a6d99-182">Il codice seguente crea un'istanza di una classe `Student` e usa un inizializzatore di oggetto per inizializzare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="a6d99-182">The following code creates an instance of a `Student` class and uses an object initializer to initialize properties.</span></span>

```vb
Dim student1 As New Student With {.First = "Michael",
                                  .Last = "Tucker"}
```

<span data-ttu-id="a6d99-183">Per altre informazioni sugli inizializzatori di oggetto, vedere [procedura: dichiarare un oggetto usando un inizializzatore di](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)oggetto, [inizializzatori di oggetto: tipi denominati e anonimi](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)e [tipi anonimi](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="a6d99-183">For more information about object initializers, see [How to: Declare an Object by Using an Object Initializer](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Object Initializers: Named and Anonymous Types](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), and [Anonymous Types](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>

## <a name="declaring-multiple-variables"></a><span data-ttu-id="a6d99-184">Dichiarazione di più variabili</span><span class="sxs-lookup"><span data-stu-id="a6d99-184">Declaring multiple variables</span></span>

<span data-ttu-id="a6d99-185">È possibile dichiarare diverse variabili in un'unica istruzione di dichiarazione, specificando il nome della variabile per ciascuna di esse e seguendo ogni nome di matrice con le parentesi.</span><span class="sxs-lookup"><span data-stu-id="a6d99-185">You can declare several variables in one declaration statement, specifying the variable name for each one, and following each array name with parentheses.</span></span> <span data-ttu-id="a6d99-186">Nel caso di più variabili, è possibile separarle mediante virgole.</span><span class="sxs-lookup"><span data-stu-id="a6d99-186">Multiple variables are separated by commas.</span></span>

```vb
Dim lastTime, nextTime, allTimes() As Date
```

<span data-ttu-id="a6d99-187">Se si dichiara più di una variabile con una clausola `As`, non è possibile fornire un inizializzatore per quel gruppo di variabili.</span><span class="sxs-lookup"><span data-stu-id="a6d99-187">If you declare more than one variable with one `As` clause, you cannot supply an initializer for that group of variables.</span></span>

<span data-ttu-id="a6d99-188">È possibile specificare tipi di dati diversi per variabili diverse utilizzando una clausola `As` separata per ogni variabile dichiarata.</span><span class="sxs-lookup"><span data-stu-id="a6d99-188">You can specify different data types for different variables by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="a6d99-189">Ogni variabile accetta il tipo di dati specificato nella prima clausola `As` rilevata dopo la relativa parte `variablename`.</span><span class="sxs-lookup"><span data-stu-id="a6d99-189">Each variable takes the data type specified in the first `As` clause encountered after its `variablename` part.</span></span>

```vb
Dim a, b, c As Single, x, y As Double, i As Integer
' a, b, and c are all Single; x and y are both Double
```

## <a name="arrays"></a><span data-ttu-id="a6d99-190">Matrici</span><span class="sxs-lookup"><span data-stu-id="a6d99-190">Arrays</span></span>

<span data-ttu-id="a6d99-191">È possibile dichiarare una variabile in modo che contenga una *matrice*, che può includere più valori.</span><span class="sxs-lookup"><span data-stu-id="a6d99-191">You can declare a variable to hold an *array*, which can hold multiple values.</span></span> <span data-ttu-id="a6d99-192">Per specificare che una variabile include una matrice, seguire immediatamente la `variablename` con le parentesi.</span><span class="sxs-lookup"><span data-stu-id="a6d99-192">To specify that a variable holds an array, follow its `variablename` immediately with parentheses.</span></span> <span data-ttu-id="a6d99-193">Per altre informazioni sulle matrici, vedere [Matrici](../../programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="a6d99-193">For more information about arrays, see [Arrays](../../programming-guide/language-features/arrays/index.md).</span></span>

<span data-ttu-id="a6d99-194">È possibile specificare il limite inferiore e superiore di ogni dimensione di una matrice.</span><span class="sxs-lookup"><span data-stu-id="a6d99-194">You can specify the lower and upper bound of each dimension of an array.</span></span> <span data-ttu-id="a6d99-195">A tale scopo, includere un `boundslist` all'interno delle parentesi.</span><span class="sxs-lookup"><span data-stu-id="a6d99-195">To do this, include a `boundslist` inside the parentheses.</span></span> <span data-ttu-id="a6d99-196">Per ogni dimensione, il `boundslist` specifica il limite superiore e, facoltativamente, il limite inferiore.</span><span class="sxs-lookup"><span data-stu-id="a6d99-196">For each dimension, the `boundslist` specifies the upper bound and optionally the lower bound.</span></span> <span data-ttu-id="a6d99-197">Il limite inferiore è sempre zero, indipendentemente dal fatto che sia specificato o meno.</span><span class="sxs-lookup"><span data-stu-id="a6d99-197">The lower bound is always zero, whether you specify it or not.</span></span> <span data-ttu-id="a6d99-198">Ogni indice può variare da zero al valore del limite superiore.</span><span class="sxs-lookup"><span data-stu-id="a6d99-198">Each index can vary from zero through its upper bound value.</span></span>

<span data-ttu-id="a6d99-199">Le due istruzioni seguenti sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="a6d99-199">The following two statements are equivalent.</span></span> <span data-ttu-id="a6d99-200">Ogni istruzione dichiara una matrice di 21 elementi `Integer`.</span><span class="sxs-lookup"><span data-stu-id="a6d99-200">Each statement declares an array of 21 `Integer` elements.</span></span> <span data-ttu-id="a6d99-201">Quando si accede alla matrice, l'indice può variare da 0 a 20.</span><span class="sxs-lookup"><span data-stu-id="a6d99-201">When you access the array, the index can vary from 0 through 20.</span></span>

```vb
Dim totals(20) As Integer
Dim totals(0 To 20) As Integer
```

<span data-ttu-id="a6d99-202">Nell'istruzione seguente viene dichiarata una matrice bidimensionale di tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="a6d99-202">The following statement declares a two-dimensional array of type `Double`.</span></span> <span data-ttu-id="a6d99-203">La matrice include 4 righe (3 + 1) di 6 colonne (5 + 1) ognuna.</span><span class="sxs-lookup"><span data-stu-id="a6d99-203">The array has 4 rows (3 + 1) of 6 columns (5 + 1) each.</span></span> <span data-ttu-id="a6d99-204">Si noti che un limite superiore rappresenta il valore massimo possibile per l'indice e non la lunghezza della dimensione.</span><span class="sxs-lookup"><span data-stu-id="a6d99-204">Note that an upper bound represents the highest possible value for the index, not the length of the dimension.</span></span> <span data-ttu-id="a6d99-205">La lunghezza della dimensione è il limite superiore più uno.</span><span class="sxs-lookup"><span data-stu-id="a6d99-205">The length of the dimension is the upper bound plus one.</span></span>

```vb
Dim matrix2(3, 5) As Double
```

<span data-ttu-id="a6d99-206">Una matrice può avere dimensioni da 1 a 32.</span><span class="sxs-lookup"><span data-stu-id="a6d99-206">An array can have from 1 to 32 dimensions.</span></span>

<span data-ttu-id="a6d99-207">È possibile lasciare vuoti tutti i limiti in una dichiarazione di matrice.</span><span class="sxs-lookup"><span data-stu-id="a6d99-207">You can leave all the bounds blank in an array declaration.</span></span> <span data-ttu-id="a6d99-208">In tal caso, la matrice ha il numero di dimensioni specificate, ma non è inizializzata.</span><span class="sxs-lookup"><span data-stu-id="a6d99-208">If you do this, the array has the number of dimensions you specify, but it is uninitialized.</span></span> <span data-ttu-id="a6d99-209">Ha un valore di `Nothing` fino a quando non si inizializzano almeno alcuni dei relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="a6d99-209">It has a value of `Nothing` until you initialize at least some of its elements.</span></span> <span data-ttu-id="a6d99-210">Nell'istruzione `Dim` devono essere specificati i limiti per tutte le dimensioni o per nessuna dimensione.</span><span class="sxs-lookup"><span data-stu-id="a6d99-210">The `Dim` statement must specify bounds either for all dimensions or for no dimensions.</span></span>

```vb
' Declare an array with blank array bounds.
Dim messages() As String
' Initialize the array.
ReDim messages(4)
```

<span data-ttu-id="a6d99-211">Se la matrice ha più di una dimensione, è necessario includere virgole tra le parentesi per indicare il numero di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="a6d99-211">If the array has more than one dimension, you must include commas between the parentheses to indicate the number of dimensions.</span></span>

```vb
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte
```

<span data-ttu-id="a6d99-212">È possibile dichiarare una *matrice di lunghezza zero* dichiarando una delle dimensioni della matrice come-1.</span><span class="sxs-lookup"><span data-stu-id="a6d99-212">You can declare a *zero-length array* by declaring one of the array's dimensions to be -1.</span></span> <span data-ttu-id="a6d99-213">Una variabile che contiene una matrice di lunghezza zero non ha il valore `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="a6d99-213">A variable that holds a zero-length array does not have the value `Nothing`.</span></span> <span data-ttu-id="a6d99-214">Le matrici di lunghezza zero sono richieste da alcune funzioni Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a6d99-214">Zero-length arrays are required by certain common language runtime functions.</span></span> <span data-ttu-id="a6d99-215">Se si tenta di accedere a una matrice di questo tipo, si verifica un'eccezione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a6d99-215">If you try to access such an array, a runtime exception occurs.</span></span> <span data-ttu-id="a6d99-216">Per altre informazioni, vedere [Matrici](../../programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="a6d99-216">For more information, see [Arrays](../../programming-guide/language-features/arrays/index.md).</span></span>

<span data-ttu-id="a6d99-217">È possibile inizializzare i valori di una matrice usando un valore letterale di matrice.</span><span class="sxs-lookup"><span data-stu-id="a6d99-217">You can initialize the values of an array by using an array literal.</span></span> <span data-ttu-id="a6d99-218">A tale scopo, racchiudere i valori di inizializzazione tra parentesi graffe (`{}`).</span><span class="sxs-lookup"><span data-stu-id="a6d99-218">To do this, surround the initialization values with braces (`{}`).</span></span>

```vb
Dim longArray() As Long = {0, 1, 2, 3}
```

<span data-ttu-id="a6d99-219">Per le matrici multidimensionali, l'inizializzazione di ogni dimensione separata è racchiusa tra parentesi graffe nella dimensione esterna.</span><span class="sxs-lookup"><span data-stu-id="a6d99-219">For multidimensional arrays, the initialization for each separate dimension is enclosed in braces in the outer dimension.</span></span> <span data-ttu-id="a6d99-220">Gli elementi vengono specificati in ordine di riga.</span><span class="sxs-lookup"><span data-stu-id="a6d99-220">The elements are specified in row-major order.</span></span>

```vb
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}
```

<span data-ttu-id="a6d99-221">Per ulteriori informazioni sui valori letterali di matrice, vedere [matrici](../../programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="a6d99-221">For more information about array literals, see [Arrays](../../programming-guide/language-features/arrays/index.md).</span></span>

## <a name="default"></a><span data-ttu-id="a6d99-222">Tipi di dati e valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="a6d99-222">Default data types and values</span></span>

<span data-ttu-id="a6d99-223">Nella tabella seguente vengono descritti i risultati di varie combinazioni della specifica del tipo di dati e dell'inizializzatore in un'istruzione `Dim`.</span><span class="sxs-lookup"><span data-stu-id="a6d99-223">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>

|<span data-ttu-id="a6d99-224">Tipo di dati specificato?</span><span class="sxs-lookup"><span data-stu-id="a6d99-224">Data type specified?</span></span>|<span data-ttu-id="a6d99-225">Inizializzatore specificato?</span><span class="sxs-lookup"><span data-stu-id="a6d99-225">Initializer specified?</span></span>|<span data-ttu-id="a6d99-226">Esempio</span><span class="sxs-lookup"><span data-stu-id="a6d99-226">Example</span></span>|<span data-ttu-id="a6d99-227">Risultato</span><span class="sxs-lookup"><span data-stu-id="a6d99-227">Result</span></span>|
|---|---|---|---|
|<span data-ttu-id="a6d99-228">No</span><span class="sxs-lookup"><span data-stu-id="a6d99-228">No</span></span>|<span data-ttu-id="a6d99-229">No</span><span class="sxs-lookup"><span data-stu-id="a6d99-229">No</span></span>|`Dim qty`|<span data-ttu-id="a6d99-230">Se [Option Strict](option-strict-statement.md) è disattivato (impostazione predefinita), la variabile viene impostata su `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="a6d99-230">If [Option Strict](option-strict-statement.md) is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="a6d99-231">Se `Option Strict` è abilitato, si verifica un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a6d99-231">If `Option Strict` is on, a compile-time error occurs.</span></span>|
|<span data-ttu-id="a6d99-232">No</span><span class="sxs-lookup"><span data-stu-id="a6d99-232">No</span></span>|<span data-ttu-id="a6d99-233">Sì</span><span class="sxs-lookup"><span data-stu-id="a6d99-233">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="a6d99-234">Se l' [opzione deduce](option-infer-statement.md) è on (impostazione predefinita), la variabile accetta il tipo di dati dell'inizializzatore.</span><span class="sxs-lookup"><span data-stu-id="a6d99-234">If [Option Infer](option-infer-statement.md) is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="a6d99-235">Vedere [inferenza del tipo locale](../../programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="a6d99-235">See [Local Type Inference](../../programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="a6d99-236">Se le istruzioni `Option Infer` e `Option Strict` sono disabilitate, il tipo di dati accettato dalla variabile è `Object`.</span><span class="sxs-lookup"><span data-stu-id="a6d99-236">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="a6d99-237">Se `Option Infer` è disabilitato e `Option Strict` è abilitato, si verifica un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a6d99-237">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|
|<span data-ttu-id="a6d99-238">Sì</span><span class="sxs-lookup"><span data-stu-id="a6d99-238">Yes</span></span>|<span data-ttu-id="a6d99-239">No</span><span class="sxs-lookup"><span data-stu-id="a6d99-239">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="a6d99-240">La variabile viene inizializzata sul valore predefinito per il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="a6d99-240">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="a6d99-241">Vedere la tabella più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="a6d99-241">See the table later in this section.</span></span>|
|<span data-ttu-id="a6d99-242">Sì</span><span class="sxs-lookup"><span data-stu-id="a6d99-242">Yes</span></span>|<span data-ttu-id="a6d99-243">Sì</span><span class="sxs-lookup"><span data-stu-id="a6d99-243">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="a6d99-244">Se il tipo di dati dell'inizializzatore non è convertibile nel tipo di dati specificato, si verifica un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="a6d99-244">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|

<span data-ttu-id="a6d99-245">Se si specifica un tipo di dati ma non si specifica un inizializzatore, Visual Basic inizializza la variabile sul valore predefinito per il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="a6d99-245">If you specify a data type but do not specify an initializer, Visual Basic initializes the variable to the default value for its data type.</span></span> <span data-ttu-id="a6d99-246">Nella tabella seguente vengono illustrati i valori di inizializzazione predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a6d99-246">The following table shows the default initialization values.</span></span>

|<span data-ttu-id="a6d99-247">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a6d99-247">Data type</span></span>|<span data-ttu-id="a6d99-248">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="a6d99-248">Default value</span></span>|
|---|---|
|<span data-ttu-id="a6d99-249">Tutti i tipi numerici (inclusi `Byte` e `SByte`)</span><span class="sxs-lookup"><span data-stu-id="a6d99-249">All numeric types (including `Byte` and `SByte`)</span></span>|<span data-ttu-id="a6d99-250">0</span><span class="sxs-lookup"><span data-stu-id="a6d99-250">0</span></span>|
|`Char`|<span data-ttu-id="a6d99-251">Binario 0</span><span class="sxs-lookup"><span data-stu-id="a6d99-251">Binary 0</span></span>|
|<span data-ttu-id="a6d99-252">Tutti i tipi di riferimento (inclusi `Object`, `String`e tutte le matrici)</span><span class="sxs-lookup"><span data-stu-id="a6d99-252">All reference types (including `Object`, `String`, and all arrays)</span></span>|`Nothing`|
|`Boolean`|`False`|
|`Date`|<span data-ttu-id="a6d99-253">12:00 del 1 ° gennaio dell'anno 1 (01/01/0001 12:00:00 AM)</span><span class="sxs-lookup"><span data-stu-id="a6d99-253">12:00 AM of January 1 of the year 1 (01/01/0001 12:00:00 AM)</span></span>|

<span data-ttu-id="a6d99-254">Ogni elemento di una struttura viene inizializzato come se fosse una variabile separata.</span><span class="sxs-lookup"><span data-stu-id="a6d99-254">Each element of a structure is initialized as if it were a separate variable.</span></span> <span data-ttu-id="a6d99-255">Se si dichiara la lunghezza di una matrice senza inizializzarne gli elementi, ogni elemento viene inizializzato come se fosse una variabile separata.</span><span class="sxs-lookup"><span data-stu-id="a6d99-255">If you declare the length of an array but do not initialize its elements, each element is initialized as if it were a separate variable.</span></span>

## <a name="static-local-variable-lifetime"></a><span data-ttu-id="a6d99-256">Durata variabile locale statica</span><span class="sxs-lookup"><span data-stu-id="a6d99-256">Static local variable lifetime</span></span>

<span data-ttu-id="a6d99-257">Una `Static` variabile locale ha una durata maggiore di quella della routine in cui è dichiarata.</span><span class="sxs-lookup"><span data-stu-id="a6d99-257">A `Static` local variable has a longer lifetime than that of the procedure in which it is declared.</span></span> <span data-ttu-id="a6d99-258">I limiti della durata della variabile dipendono dalla posizione in cui la procedura viene dichiarata e dal fatto che sia `Shared`.</span><span class="sxs-lookup"><span data-stu-id="a6d99-258">The boundaries of the variable's lifetime depend on where the procedure is declared and whether it is `Shared`.</span></span>

|<span data-ttu-id="a6d99-259">Dichiarazione di routine</span><span class="sxs-lookup"><span data-stu-id="a6d99-259">Procedure declaration</span></span>|<span data-ttu-id="a6d99-260">Variabile inizializzata</span><span class="sxs-lookup"><span data-stu-id="a6d99-260">Variable initialized</span></span>|<span data-ttu-id="a6d99-261">La variabile smette di esistere</span><span class="sxs-lookup"><span data-stu-id="a6d99-261">Variable stops existing</span></span>|
|---|---|---|
|<span data-ttu-id="a6d99-262">In un modulo</span><span class="sxs-lookup"><span data-stu-id="a6d99-262">In a module</span></span>|<span data-ttu-id="a6d99-263">La prima volta che viene chiamata la stored procedure</span><span class="sxs-lookup"><span data-stu-id="a6d99-263">The first time the procedure is called</span></span>|<span data-ttu-id="a6d99-264">Quando il programma interrompe l'esecuzione</span><span class="sxs-lookup"><span data-stu-id="a6d99-264">When your program stops execution</span></span>|
|<span data-ttu-id="a6d99-265">In una classe o una struttura, la procedura è `Shared`</span><span class="sxs-lookup"><span data-stu-id="a6d99-265">In a class or structure, procedure is `Shared`</span></span>|<span data-ttu-id="a6d99-266">La prima volta che la stored procedure viene chiamata su un'istanza specifica o sulla classe o sulla struttura stessa</span><span class="sxs-lookup"><span data-stu-id="a6d99-266">The first time the procedure is called either on a specific instance or on the class or structure itself</span></span>|<span data-ttu-id="a6d99-267">Quando il programma interrompe l'esecuzione</span><span class="sxs-lookup"><span data-stu-id="a6d99-267">When your program stops execution</span></span>|
|<span data-ttu-id="a6d99-268">In una classe o una struttura, la routine non è `Shared`</span><span class="sxs-lookup"><span data-stu-id="a6d99-268">In a class or structure, procedure isn't `Shared`</span></span>|<span data-ttu-id="a6d99-269">La prima volta che la stored procedure viene chiamata su un'istanza specifica</span><span class="sxs-lookup"><span data-stu-id="a6d99-269">The first time the procedure is called on a specific instance</span></span>|<span data-ttu-id="a6d99-270">Quando l'istanza viene rilasciata per Garbage Collection (GC)</span><span class="sxs-lookup"><span data-stu-id="a6d99-270">When the instance is released for garbage collection (GC)</span></span>|

## <a name="attributes-and-modifiers"></a><span data-ttu-id="a6d99-271">Attributi e modificatori</span><span class="sxs-lookup"><span data-stu-id="a6d99-271">Attributes and modifiers</span></span>

<span data-ttu-id="a6d99-272">È possibile applicare attributi solo alle variabili membro e non alle variabili locali.</span><span class="sxs-lookup"><span data-stu-id="a6d99-272">You can apply attributes only to member variables, not to local variables.</span></span> <span data-ttu-id="a6d99-273">Un attributo fornisce informazioni ai metadati dell'assembly, che non è significativo per l'archiviazione temporanea, ad esempio le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="a6d99-273">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local variables.</span></span>

<span data-ttu-id="a6d99-274">A livello di modulo, non è possibile usare il modificatore `Static` per dichiarare le variabili membro.</span><span class="sxs-lookup"><span data-stu-id="a6d99-274">At module level, you cannot use the `Static` modifier to declare member variables.</span></span> <span data-ttu-id="a6d99-275">A livello di procedura, non è possibile utilizzare `Shared`, `Shadows`, `ReadOnly`, `WithEvents`o qualsiasi modificatore di accesso per dichiarare le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="a6d99-275">At procedure level, you cannot use `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, or any access modifiers to declare local variables.</span></span>

<span data-ttu-id="a6d99-276">È possibile specificare quale codice può accedere a una variabile fornendo un `accessmodifier`.</span><span class="sxs-lookup"><span data-stu-id="a6d99-276">You can specify what code can access a variable by supplying an `accessmodifier`.</span></span> <span data-ttu-id="a6d99-277">Le variabili membro della classe e del modulo (all'esterno di qualsiasi routine) sono predefinite per l'accesso privato e le variabili membro della struttura sono predefinite per l'accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="a6d99-277">Class and module member variables (outside any procedure) default to private access, and structure member variables default to public access.</span></span> <span data-ttu-id="a6d99-278">È possibile modificare i livelli di accesso con i modificatori di accesso.</span><span class="sxs-lookup"><span data-stu-id="a6d99-278">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="a6d99-279">Non è possibile usare i modificatori di accesso per le variabili locali (all'interno di una routine).</span><span class="sxs-lookup"><span data-stu-id="a6d99-279">You cannot use access modifiers on local variables (inside a procedure).</span></span>

<span data-ttu-id="a6d99-280">È possibile specificare `WithEvents` solo sulle variabili membro, non sulle variabili locali all'interno di una routine.</span><span class="sxs-lookup"><span data-stu-id="a6d99-280">You can specify `WithEvents` only on member variables, not on local variables inside a procedure.</span></span> <span data-ttu-id="a6d99-281">Se si specifica `WithEvents`, il tipo di dati della variabile deve essere un tipo di classe specifico, non `Object`.</span><span class="sxs-lookup"><span data-stu-id="a6d99-281">If you specify `WithEvents`, the data type of the variable must be a specific class type, not `Object`.</span></span> <span data-ttu-id="a6d99-282">Non è possibile dichiarare una matrice con `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="a6d99-282">You cannot declare an array with `WithEvents`.</span></span> <span data-ttu-id="a6d99-283">Per ulteriori informazioni sugli eventi, vedere [eventi](../../programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="a6d99-283">For more information about events, see [Events](../../programming-guide/language-features/events/index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a6d99-284">Il codice esterno a una classe, una struttura o un modulo deve qualificare il nome di una variabile membro con il nome della classe, della struttura o del modulo.</span><span class="sxs-lookup"><span data-stu-id="a6d99-284">Code outside a class, structure, or module must qualify a member variable's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="a6d99-285">Il codice esterno a una procedura o a un blocco non può fare riferimento ad alcuna variabile locale all'interno di tale procedura o blocco.</span><span class="sxs-lookup"><span data-stu-id="a6d99-285">Code outside a procedure or block cannot refer to any local variables within that procedure or block.</span></span>

## <a name="releasing-managed-resources"></a><span data-ttu-id="a6d99-286">Rilascio di risorse gestite</span><span class="sxs-lookup"><span data-stu-id="a6d99-286">Releasing managed resources</span></span>

<span data-ttu-id="a6d99-287">Il .NET Framework Garbage Collector elimina le risorse gestite senza alcuna codifica aggiuntiva da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a6d99-287">The .NET Framework garbage collector disposes of managed resources without any extra coding on your part.</span></span> <span data-ttu-id="a6d99-288">Tuttavia, è possibile forzare l'eliminazione di una risorsa gestita anziché attendere il Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="a6d99-288">However, you can force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>

<span data-ttu-id="a6d99-289">Se una classe dispone di una risorsa particolarmente preziosa e limitata (ad esempio una connessione al database o un handle di file), è possibile che non si desideri attendere fino al Garbage Collection successivo per eliminare un'istanza di classe che non è più in uso.</span><span class="sxs-lookup"><span data-stu-id="a6d99-289">If a class holds onto a particularly valuable and scarce resource (such as a database connection or file handle), you might not want to wait until the next garbage collection to clean up a class instance that's no longer in use.</span></span> <span data-ttu-id="a6d99-290">Una classe può implementare l'interfaccia <xref:System.IDisposable> per fornire un modo per rilasciare le risorse prima di un Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a6d99-290">A class may implement the <xref:System.IDisposable> interface to provide a way to release resources before a garbage collection.</span></span> <span data-ttu-id="a6d99-291">Una classe che implementa tale interfaccia espone un metodo di `Dispose` che può essere chiamato per forzare il rilascio immediato di risorse preziose.</span><span class="sxs-lookup"><span data-stu-id="a6d99-291">A class that implements that interface exposes a `Dispose` method that can be called to force valuable resources to be released immediately.</span></span>

<span data-ttu-id="a6d99-292">L'istruzione `Using` automatizza il processo di acquisizione di una risorsa, l'esecuzione di un set di istruzioni e quindi l'eliminazione della risorsa.</span><span class="sxs-lookup"><span data-stu-id="a6d99-292">The `Using` statement automates the process of acquiring a resource, executing a set of statements, and then disposing of the resource.</span></span> <span data-ttu-id="a6d99-293">Tuttavia, la risorsa deve implementare l'interfaccia <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="a6d99-293">However, the resource must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="a6d99-294">Per altre informazioni, vedere [Istruzione using](using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a6d99-294">For more information, see [Using Statement](using-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="a6d99-295">Esempio</span><span class="sxs-lookup"><span data-stu-id="a6d99-295">Example</span></span>

<span data-ttu-id="a6d99-296">Nell'esempio seguente vengono dichiarate le variabili usando l'istruzione `Dim` con varie opzioni.</span><span class="sxs-lookup"><span data-stu-id="a6d99-296">The following example declares variables by using the `Dim` statement with various options.</span></span>

[!code-vb[VbVbalrStatements#141](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#141)]

## <a name="example"></a><span data-ttu-id="a6d99-297">Esempio</span><span class="sxs-lookup"><span data-stu-id="a6d99-297">Example</span></span>

<span data-ttu-id="a6d99-298">Nell'esempio seguente vengono elencati i numeri primi compresi tra 1 e 30.</span><span class="sxs-lookup"><span data-stu-id="a6d99-298">The following example lists the prime numbers between 1 and 30.</span></span> <span data-ttu-id="a6d99-299">L'ambito delle variabili locali è descritto nei commenti del codice.</span><span class="sxs-lookup"><span data-stu-id="a6d99-299">The scope of local variables is described in code comments.</span></span>

[!code-vb[VbVbalrStatements#142](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#142)]

## <a name="example"></a><span data-ttu-id="a6d99-300">Esempio</span><span class="sxs-lookup"><span data-stu-id="a6d99-300">Example</span></span>

<span data-ttu-id="a6d99-301">Nell'esempio seguente, la variabile `speedValue` viene dichiarata a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="a6d99-301">In the following example, the `speedValue` variable is declared at the class level.</span></span> <span data-ttu-id="a6d99-302">La parola chiave `Private` viene utilizzata per dichiarare la variabile.</span><span class="sxs-lookup"><span data-stu-id="a6d99-302">The `Private` keyword is used to declare the variable.</span></span> <span data-ttu-id="a6d99-303">È possibile accedere alla variabile da qualsiasi routine della classe `Car`.</span><span class="sxs-lookup"><span data-stu-id="a6d99-303">The variable can be accessed by any procedure in the `Car` class.</span></span>

[!code-vb[VbVbalrStatements#144](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#144)]

[!code-vb[VbVbalrStatements#145](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#145)]

## <a name="see-also"></a><span data-ttu-id="a6d99-304">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6d99-304">See also</span></span>

- [<span data-ttu-id="a6d99-305">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="a6d99-305">Const Statement</span></span>](const-statement.md)
- [<span data-ttu-id="a6d99-306">Istruzione ReDim</span><span class="sxs-lookup"><span data-stu-id="a6d99-306">ReDim Statement</span></span>](redim-statement.md)
- [<span data-ttu-id="a6d99-307">Istruzione Option Explicit</span><span class="sxs-lookup"><span data-stu-id="a6d99-307">Option Explicit Statement</span></span>](option-explicit-statement.md)
- [<span data-ttu-id="a6d99-308">Istruzione Option Infer</span><span class="sxs-lookup"><span data-stu-id="a6d99-308">Option Infer Statement</span></span>](option-infer-statement.md)
- [<span data-ttu-id="a6d99-309">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="a6d99-309">Option Strict Statement</span></span>](option-strict-statement.md)
- [<span data-ttu-id="a6d99-310">Pagina Compilazione, Creazione progetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6d99-310">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [<span data-ttu-id="a6d99-311">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="a6d99-311">Variable Declaration</span></span>](../../programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="a6d99-312">Array</span><span class="sxs-lookup"><span data-stu-id="a6d99-312">Arrays</span></span>](../../programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="a6d99-313">Inizializzatori di oggetto: tipi denominati e tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="a6d99-313">Object Initializers: Named and Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="a6d99-314">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="a6d99-314">Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="a6d99-315">Inizializzatori di oggetto: tipi denominati e tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="a6d99-315">Object Initializers: Named and Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="a6d99-316">Procedura: Dichiarare un oggetto usando un inizializzatore di oggetto</span><span class="sxs-lookup"><span data-stu-id="a6d99-316">How to: Declare an Object by Using an Object Initializer</span></span>](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
- [<span data-ttu-id="a6d99-317">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="a6d99-317">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)

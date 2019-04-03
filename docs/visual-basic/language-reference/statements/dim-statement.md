---
title: Istruzione Dim (Visual Basic)
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
ms.openlocfilehash: cab1cc07d23a44e57bdb0962a323b014308cb1e5
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58836558"
---
# <a name="dim-statement-visual-basic"></a><span data-ttu-id="1ff84-102">Istruzione Dim (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ff84-102">Dim Statement (Visual Basic)</span></span>
<span data-ttu-id="1ff84-103">Dichiara e alloca spazio di archiviazione per una o più variabili.</span><span class="sxs-lookup"><span data-stu-id="1ff84-103">Declares and allocates storage space for one or more variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ff84-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1ff84-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]   
Dim [ WithEvents ] variablelist  
```  
  
## <a name="parts"></a><span data-ttu-id="1ff84-105">Parti</span><span class="sxs-lookup"><span data-stu-id="1ff84-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="1ff84-106">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1ff84-106">Optional.</span></span> <span data-ttu-id="1ff84-107">Visualizzare [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="1ff84-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="1ff84-108">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1ff84-108">Optional.</span></span> <span data-ttu-id="1ff84-109">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="1ff84-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="1ff84-110">Public</span><span class="sxs-lookup"><span data-stu-id="1ff84-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="1ff84-111">Protected</span><span class="sxs-lookup"><span data-stu-id="1ff84-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="1ff84-112">Friend</span><span class="sxs-lookup"><span data-stu-id="1ff84-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="1ff84-113">Private</span><span class="sxs-lookup"><span data-stu-id="1ff84-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   [<span data-ttu-id="1ff84-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="1ff84-114">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)
    
    - [<span data-ttu-id="1ff84-115">Private Protected</span><span class="sxs-lookup"><span data-stu-id="1ff84-115">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

     <span data-ttu-id="1ff84-116">Vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="1ff84-116">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `Shared`  
  
     <span data-ttu-id="1ff84-117">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1ff84-117">Optional.</span></span> <span data-ttu-id="1ff84-118">Visualizzare [condiviso](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="1ff84-118">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="1ff84-119">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1ff84-119">Optional.</span></span> <span data-ttu-id="1ff84-120">Visualizzare [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="1ff84-120">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Static`  
  
     <span data-ttu-id="1ff84-121">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1ff84-121">Optional.</span></span> <span data-ttu-id="1ff84-122">Visualizzare [statici](../../../visual-basic/language-reference/modifiers/static.md).</span><span class="sxs-lookup"><span data-stu-id="1ff84-122">See [Static](../../../visual-basic/language-reference/modifiers/static.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="1ff84-123">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1ff84-123">Optional.</span></span> <span data-ttu-id="1ff84-124">Visualizzare [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="1ff84-124">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WithEvents`  
  
     <span data-ttu-id="1ff84-125">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1ff84-125">Optional.</span></span> <span data-ttu-id="1ff84-126">Specifica che si tratta di oggetti variabili che fanno riferimento alle istanze di una classe che può generare eventi.</span><span class="sxs-lookup"><span data-stu-id="1ff84-126">Specifies that these are object variables that refer to instances of a class that can raise events.</span></span> <span data-ttu-id="1ff84-127">Visualizzare [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="1ff84-127">See [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span></span>  
  
-   `variablelist`  
  
     <span data-ttu-id="1ff84-128">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1ff84-128">Required.</span></span> <span data-ttu-id="1ff84-129">Elenco di variabili dichiarate in questa istruzione.</span><span class="sxs-lookup"><span data-stu-id="1ff84-129">List of variables being declared in this statement.</span></span>  
  
     `variable [ , variable ... ]`  
  
     <span data-ttu-id="1ff84-130">Ogni `variable` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1ff84-130">Each `variable` has the following syntax and parts:</span></span>  
  
     <span data-ttu-id="1ff84-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="1ff84-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="1ff84-132">Parte</span><span class="sxs-lookup"><span data-stu-id="1ff84-132">Part</span></span>|<span data-ttu-id="1ff84-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ff84-133">Description</span></span>|  
    |---|---|  
    |`variablename`|<span data-ttu-id="1ff84-134">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1ff84-134">Required.</span></span> <span data-ttu-id="1ff84-135">Nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="1ff84-135">Name of the variable.</span></span> <span data-ttu-id="1ff84-136">Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="1ff84-136">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
    |`boundslist`|<span data-ttu-id="1ff84-137">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1ff84-137">Optional.</span></span> <span data-ttu-id="1ff84-138">Elenco dei limiti di ogni dimensione di una variabile di matrice.</span><span class="sxs-lookup"><span data-stu-id="1ff84-138">List of bounds of each dimension of an array variable.</span></span>|  
    |`New`|<span data-ttu-id="1ff84-139">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1ff84-139">Optional.</span></span> <span data-ttu-id="1ff84-140">Crea una nuova istanza della classe quando il `Dim` istruzione viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="1ff84-140">Creates a new instance of the class when the `Dim` statement runs.</span></span>|  
    |`datatype`|<span data-ttu-id="1ff84-141">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1ff84-141">Optional.</span></span> <span data-ttu-id="1ff84-142">Tipo di dati della variabile.</span><span class="sxs-lookup"><span data-stu-id="1ff84-142">Data type of the variable.</span></span>|  
    |`With`|<span data-ttu-id="1ff84-143">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1ff84-143">Optional.</span></span> <span data-ttu-id="1ff84-144">Introduce l'elenco di inizializzatori di oggetto.</span><span class="sxs-lookup"><span data-stu-id="1ff84-144">Introduces the object initializer list.</span></span>|  
    |`propertyname`|<span data-ttu-id="1ff84-145">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1ff84-145">Optional.</span></span> <span data-ttu-id="1ff84-146">Il nome di una proprietà nella classe si sta creando un'istanza di.</span><span class="sxs-lookup"><span data-stu-id="1ff84-146">The name of a property in the class you are making an instance of.</span></span>|  
    |`propinitializer`|<span data-ttu-id="1ff84-147">Dopo necessario `propertyname` =.</span><span class="sxs-lookup"><span data-stu-id="1ff84-147">Required after `propertyname` =.</span></span> <span data-ttu-id="1ff84-148">L'espressione che viene valutata e assegnata al nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="1ff84-148">The expression that is evaluated and assigned to the property name.</span></span>|  
    |`initializer`|<span data-ttu-id="1ff84-149">Facoltativo se `New` non è specificato.</span><span class="sxs-lookup"><span data-stu-id="1ff84-149">Optional if `New` is not specified.</span></span> <span data-ttu-id="1ff84-150">Espressione che viene valutata e assegnato alla variabile quando viene creato.</span><span class="sxs-lookup"><span data-stu-id="1ff84-150">Expression that is evaluated and assigned to the variable when it is created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ff84-151">Note</span><span class="sxs-lookup"><span data-stu-id="1ff84-151">Remarks</span></span>  
 <span data-ttu-id="1ff84-152">Il compilatore Visual Basic Usa la `Dim` istruzione per determinare il tipo di dati della variabile e altre informazioni, ad esempio il tipo di codice può accedere alla variabile.</span><span class="sxs-lookup"><span data-stu-id="1ff84-152">The Visual Basic compiler uses the `Dim` statement to determine the variable's data type and other information, such as what code can access the variable.</span></span> <span data-ttu-id="1ff84-153">L'esempio seguente dichiara una variabile per contenere un `Integer` valore.</span><span class="sxs-lookup"><span data-stu-id="1ff84-153">The following example declares a variable to hold an `Integer` value.</span></span>  
  
```vb  
Dim numberOfStudents As Integer  
```  
  
 <span data-ttu-id="1ff84-154">È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, struttura, classe o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="1ff84-154">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
```vb  
Dim finished As Boolean  
Dim monitorBox As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="1ff84-155">Per un tipo riferimento, si utilizza il `New` (parola chiave) per creare una nuova istanza della classe o una struttura che viene specificato dal tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="1ff84-155">For a reference type, you use the `New` keyword to create a new instance of the class or structure that is specified by the data type.</span></span> <span data-ttu-id="1ff84-156">Se si usa `New`, non si utilizza un'espressione dell'inizializzatore.</span><span class="sxs-lookup"><span data-stu-id="1ff84-156">If you use `New`, you do not use an initializer expression.</span></span> <span data-ttu-id="1ff84-157">In alternativa, è fornire argomenti, se sono necessarie, per il costruttore della classe da cui si sta creando la variabile.</span><span class="sxs-lookup"><span data-stu-id="1ff84-157">Instead, you supply arguments, if they are required, to the constructor of the class from which you are creating the variable.</span></span>  
  
```vb  
Dim bottomLabel As New System.Windows.Forms.Label  
```  
  
 <span data-ttu-id="1ff84-158">È possibile dichiarare una variabile in una routine, blocco, classe, struttura o modulo.</span><span class="sxs-lookup"><span data-stu-id="1ff84-158">You can declare a variable in a procedure, block, class, structure, or module.</span></span> <span data-ttu-id="1ff84-159">È possibile dichiarare una variabile in un file di origine, lo spazio dei nomi o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="1ff84-159">You cannot declare a variable in a source file, namespace, or interface.</span></span> <span data-ttu-id="1ff84-160">Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="1ff84-160">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="1ff84-161">Una variabile dichiarata a livello di modulo, all'esterno di qualsiasi routine è una *variabile membro* oppure *campo*.</span><span class="sxs-lookup"><span data-stu-id="1ff84-161">A variable that is declared at module level, outside any procedure, is a *member variable* or *field*.</span></span> <span data-ttu-id="1ff84-162">Le variabili membro rientrano nell'ambito in tutta la classe, struttura o modulo.</span><span class="sxs-lookup"><span data-stu-id="1ff84-162">Member variables are in scope throughout their class, structure, or module.</span></span> <span data-ttu-id="1ff84-163">Una variabile dichiarata a livello di routine è una *variabile locale*.</span><span class="sxs-lookup"><span data-stu-id="1ff84-163">A variable that is declared at procedure level is a *local variable*.</span></span> <span data-ttu-id="1ff84-164">Le variabili locali sono nell'ambito solo all'interno della routine o un blocco.</span><span class="sxs-lookup"><span data-stu-id="1ff84-164">Local variables are in scope only within their procedure or block.</span></span>  
  
 <span data-ttu-id="1ff84-165">I seguenti modificatori di accesso vengono usati per dichiarare le variabili all'esterno di una routine: `Public`, `Protected`, `Friend`, `Protected Friend`, e `Private`.</span><span class="sxs-lookup"><span data-stu-id="1ff84-165">The following access modifiers are used to declare variables outside a procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private`.</span></span> <span data-ttu-id="1ff84-166">Per altre informazioni, vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="1ff84-166">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="1ff84-167">Il `Dim` parola chiave è facoltativa e in genere omessi se si specifica uno dei modificatori seguenti: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, o `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="1ff84-167">The `Dim` keyword is optional and usually omitted if you specify any of the following modifiers: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, or `WithEvents`.</span></span>  
  
```vb  
Public maximumAllowed As Double  
Protected Friend currentUserName As String  
Private salary As Decimal  
Static runningTotal As Integer  
```  
  
 <span data-ttu-id="1ff84-168">Se `Option Explicit` è abilitata (impostazione predefinita), il compilatore richiede una dichiarazione per tutte le variabili utilizzate.</span><span class="sxs-lookup"><span data-stu-id="1ff84-168">If `Option Explicit` is on (the default), the compiler requires a declaration for every variable you use.</span></span> <span data-ttu-id="1ff84-169">Per altre informazioni, vedere [istruzione Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span><span class="sxs-lookup"><span data-stu-id="1ff84-169">For more information, see [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span></span>  
  
## <a name="specifying-an-initial-value"></a><span data-ttu-id="1ff84-170">Se si specifica un valore iniziale</span><span class="sxs-lookup"><span data-stu-id="1ff84-170">Specifying an Initial Value</span></span>  
 <span data-ttu-id="1ff84-171">È possibile assegnare un valore a una variabile quando viene creato.</span><span class="sxs-lookup"><span data-stu-id="1ff84-171">You can assign a value to a variable when it is created.</span></span> <span data-ttu-id="1ff84-172">Per un tipo di valore, Usa un' *inizializzatore* per fornire un'espressione da assegnare alla variabile.</span><span class="sxs-lookup"><span data-stu-id="1ff84-172">For a value type, you use an *initializer* to supply an expression to be assigned to the variable.</span></span> <span data-ttu-id="1ff84-173">L'espressione deve restituire una costante che può essere calcolato in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="1ff84-173">The expression must evaluate to a constant that can be calculated at compile time.</span></span>  
  
```vb  
Dim quantity As Integer = 10  
Dim message As String = "Just started"  
```  
  
 <span data-ttu-id="1ff84-174">Se viene specificato un inizializzatore e non viene specificato un tipo di dati un' `As` clausola *inferenza del tipo* viene usato per dedurre il tipo di dati dall'inizializzatore.</span><span class="sxs-lookup"><span data-stu-id="1ff84-174">If an initializer is specified and a data type is not specified in an `As` clause, *type inference* is used to infer the data type from the initializer.</span></span> <span data-ttu-id="1ff84-175">Nell'esempio seguente, entrambe `num1` e `num2` sono fortemente tipizzati come numeri interi.</span><span class="sxs-lookup"><span data-stu-id="1ff84-175">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span> <span data-ttu-id="1ff84-176">Nella seconda dichiarazione, inferenza dei tipi deduce il tipo rispetto al valore 3.</span><span class="sxs-lookup"><span data-stu-id="1ff84-176">In the second declaration, type inference infers the type from the value 3.</span></span>  
  
```vb  
' Use explicit typing.  
Dim num1 As Integer = 3  
  
' Use local type inference.  
Dim num2 = 3  
```  
  
 <span data-ttu-id="1ff84-177">L'inferenza del tipo si applica a livello di routine.</span><span class="sxs-lookup"><span data-stu-id="1ff84-177">Type inference applies at the procedure level.</span></span> <span data-ttu-id="1ff84-178">Non è applicabile all'esterno di una routine in una classe, struttura, modulo o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="1ff84-178">It does not apply outside a procedure in a class, structure, module, or interface.</span></span> <span data-ttu-id="1ff84-179">Per altre informazioni sull'inferenza del tipo, vedere [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) e [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="1ff84-179">For more information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
 <span data-ttu-id="1ff84-180">Per informazioni su cosa accade quando un tipo di dati o l'inizializzatore viene omesso, vedere [tipi di dati predefiniti e i valori](../../../visual-basic/language-reference/statements/dim-statement.md#default) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="1ff84-180">For information about what happens when a data type or initializer is not specified, see [Default Data Types and Values](../../../visual-basic/language-reference/statements/dim-statement.md#default) later in this topic.</span></span>  
  
 <span data-ttu-id="1ff84-181">È possibile usare un *inizializzatore di oggetto* per dichiarare le istanze di tipi denominati e anonimi.</span><span class="sxs-lookup"><span data-stu-id="1ff84-181">You can use an *object initializer* to declare instances of named and anonymous types.</span></span> <span data-ttu-id="1ff84-182">Il codice seguente crea un'istanza di un `Student` classe e Usa un inizializzatore di oggetto per inizializzare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="1ff84-182">The following code creates an instance of a `Student` class and uses an object initializer to initialize properties.</span></span>  
  
```vb  
Dim student1 As New Student With {.First = "Michael",   
                                  .Last = "Tucker"}  
```  
  
 <span data-ttu-id="1ff84-183">Per altre informazioni sugli inizializzatori di oggetto, vedere [come: Dichiarare un oggetto usando un inizializzatore di oggetto](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [inizializzatori di oggetto: Tipi denominati e anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), e [tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="1ff84-183">For more information about object initializers, see [How to: Declare an Object by Using an Object Initializer](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), and [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="declaring-multiple-variables"></a><span data-ttu-id="1ff84-184">Dichiarare più variabili</span><span class="sxs-lookup"><span data-stu-id="1ff84-184">Declaring Multiple Variables</span></span>  
 <span data-ttu-id="1ff84-185">È possibile dichiarare più variabili in un'istruzione di dichiarazione, specificando il nome della variabile per ognuno di essi e dopo ogni nome di matrice con parentesi.</span><span class="sxs-lookup"><span data-stu-id="1ff84-185">You can declare several variables in one declaration statement, specifying the variable name for each one, and following each array name with parentheses.</span></span> <span data-ttu-id="1ff84-186">Nel caso di più variabili, è possibile separarle mediante virgole.</span><span class="sxs-lookup"><span data-stu-id="1ff84-186">Multiple variables are separated by commas.</span></span>  
  
```vb  
Dim lastTime, nextTime, allTimes() As Date  
```  
  
 <span data-ttu-id="1ff84-187">Se si dichiara più di una variabile con uno `As` clausola, non è possibile specificare un inizializzatore per il gruppo di variabili.</span><span class="sxs-lookup"><span data-stu-id="1ff84-187">If you declare more than one variable with one `As` clause, you cannot supply an initializer for that group of variables.</span></span>  
  
 <span data-ttu-id="1ff84-188">È possibile specificare tipi di dati diversi per diverse variabili utilizzando un oggetto separato `As` clausola per ogni variabile è dichiarata.</span><span class="sxs-lookup"><span data-stu-id="1ff84-188">You can specify different data types for different variables by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="1ff84-189">Ogni variabile ha il tipo di dati specificato nel primo `As` clausola rilevata dopo il relativo `variablename` parte.</span><span class="sxs-lookup"><span data-stu-id="1ff84-189">Each variable takes the data type specified in the first `As` clause encountered after its `variablename` part.</span></span>  
  
```vb  
Dim a, b, c As Single, x, y As Double, i As Integer  
' a, b, and c are all Single; x and y are both Double  
```  
  
## <a name="arrays"></a><span data-ttu-id="1ff84-190">Matrici</span><span class="sxs-lookup"><span data-stu-id="1ff84-190">Arrays</span></span>  
 <span data-ttu-id="1ff84-191">È possibile dichiarare una variabile per contenere un *matrice*, che può contenere più valori.</span><span class="sxs-lookup"><span data-stu-id="1ff84-191">You can declare a variable to hold an *array*, which can hold multiple values.</span></span> <span data-ttu-id="1ff84-192">Per specificare che una variabile contiene una matrice, seguire le `variablename` immediatamente con le parentesi.</span><span class="sxs-lookup"><span data-stu-id="1ff84-192">To specify that a variable holds an array, follow its `variablename` immediately with parentheses.</span></span> <span data-ttu-id="1ff84-193">Per altre informazioni sulle matrici, vedere [Matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="1ff84-193">For more information about arrays, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="1ff84-194">È possibile specificare il limite inferiore e superiore di ogni dimensione della matrice.</span><span class="sxs-lookup"><span data-stu-id="1ff84-194">You can specify the lower and upper bound of each dimension of an array.</span></span> <span data-ttu-id="1ff84-195">A tale scopo, includere un `boundslist` all'interno delle parentesi.</span><span class="sxs-lookup"><span data-stu-id="1ff84-195">To do this, include a `boundslist` inside the parentheses.</span></span> <span data-ttu-id="1ff84-196">Per ogni dimensione, il `boundslist` specifica il limite superiore e, facoltativamente, il limite inferiore.</span><span class="sxs-lookup"><span data-stu-id="1ff84-196">For each dimension, the `boundslist` specifies the upper bound and optionally the lower bound.</span></span> <span data-ttu-id="1ff84-197">Il limite inferiore è sempre uguale a zero, se si specifichi o meno.</span><span class="sxs-lookup"><span data-stu-id="1ff84-197">The lower bound is always zero, whether you specify it or not.</span></span> <span data-ttu-id="1ff84-198">Ogni indice può variare da zero tramite il relativo valore limite superiore.</span><span class="sxs-lookup"><span data-stu-id="1ff84-198">Each index can vary from zero through its upper bound value.</span></span>  
  
 <span data-ttu-id="1ff84-199">Le due istruzioni seguenti sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="1ff84-199">The following two statements are equivalent.</span></span> <span data-ttu-id="1ff84-200">Ogni istruzione dichiara una matrice di 21 `Integer` elementi.</span><span class="sxs-lookup"><span data-stu-id="1ff84-200">Each statement declares an array of 21 `Integer` elements.</span></span> <span data-ttu-id="1ff84-201">Quando si accede a matrice, l'indice può variare da 0 a 20.</span><span class="sxs-lookup"><span data-stu-id="1ff84-201">When you access the array, the index can vary from 0 through 20.</span></span>  
  
```vb  
Dim totals(20) As Integer  
Dim totals(0 To 20) As Integer  
```  
  
 <span data-ttu-id="1ff84-202">L'istruzione seguente dichiara una matrice bidimensionale di tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="1ff84-202">The following statement declares a two-dimensional array of type `Double`.</span></span> <span data-ttu-id="1ff84-203">La matrice ha 4 righe (3 + 1) di 6 (5 + 1) ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="1ff84-203">The array has 4 rows (3 + 1) of 6 columns (5 + 1) each.</span></span> <span data-ttu-id="1ff84-204">Si noti che il limite superiore rappresenta il valore massimo possibile per l'indice, non la lunghezza della dimensione.</span><span class="sxs-lookup"><span data-stu-id="1ff84-204">Note that an upper bound represents the highest possible value for the index, not the length of the dimension.</span></span> <span data-ttu-id="1ff84-205">La lunghezza della dimensione è il limite superiore più uno.</span><span class="sxs-lookup"><span data-stu-id="1ff84-205">The length of the dimension is the upper bound plus one.</span></span>  
  
```vb  
Dim matrix2(3, 5) As Double  
```  
  
 <span data-ttu-id="1ff84-206">Una matrice può avere da 1 a 32 dimensioni.</span><span class="sxs-lookup"><span data-stu-id="1ff84-206">An array can have from 1 to 32 dimensions.</span></span>  
  
 <span data-ttu-id="1ff84-207">È possibile lasciare vuoto in una dichiarazione di matrice tutti i limiti.</span><span class="sxs-lookup"><span data-stu-id="1ff84-207">You can leave all the bounds blank in an array declaration.</span></span> <span data-ttu-id="1ff84-208">In questo caso, la matrice disponga del numero di dimensioni specificato, ma è non inizializzato.</span><span class="sxs-lookup"><span data-stu-id="1ff84-208">If you do this, the array has the number of dimensions you specify, but it is uninitialized.</span></span> <span data-ttu-id="1ff84-209">Assume un valore di `Nothing` finché non viene inizializzata almeno alcuni dei relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="1ff84-209">It has a value of `Nothing` until you initialize at least some of its elements.</span></span> <span data-ttu-id="1ff84-210">Il `Dim` istruzione deve specificare i limiti per tutte le dimensioni o per nessuna dimensione.</span><span class="sxs-lookup"><span data-stu-id="1ff84-210">The `Dim` statement must specify bounds either for all dimensions or for no dimensions.</span></span>  
  
```vb  
' Declare an array with blank array bounds.  
Dim messages() As String  
' Initialize the array.  
ReDim messages(4)  
```  
  
 <span data-ttu-id="1ff84-211">Se la matrice ha più di una dimensione, è necessario includere virgole tra parentesi per indicare il numero di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="1ff84-211">If the array has more than one dimension, you must include commas between the parentheses to indicate the number of dimensions.</span></span>  
  
```vb  
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte  
```  
  
 <span data-ttu-id="1ff84-212">È possibile dichiarare un *matrice di lunghezza zero* dichiarando una delle dimensioni della matrice-1.</span><span class="sxs-lookup"><span data-stu-id="1ff84-212">You can declare a *zero-length array* by declaring one of the array's dimensions to be -1.</span></span> <span data-ttu-id="1ff84-213">Una variabile che contiene una matrice di lunghezza zero non ha il valore `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="1ff84-213">A variable that holds a zero-length array does not have the value `Nothing`.</span></span> <span data-ttu-id="1ff84-214">Matrici di lunghezza zero sono richiesti da alcune funzioni di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="1ff84-214">Zero-length arrays are required by certain common language runtime functions.</span></span> <span data-ttu-id="1ff84-215">Se si tenta di accedere ad esempio una matrice, si verifica un'eccezione di runtime.</span><span class="sxs-lookup"><span data-stu-id="1ff84-215">If you try to access such an array, a runtime exception occurs.</span></span> <span data-ttu-id="1ff84-216">Per altre informazioni, vedere [matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="1ff84-216">For more information, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="1ff84-217">È possibile inizializzare i valori di una matrice con un valore letterale di matrice.</span><span class="sxs-lookup"><span data-stu-id="1ff84-217">You can initialize the values of an array by using an array literal.</span></span> <span data-ttu-id="1ff84-218">A tale scopo, racchiudere i valori di inizializzazione con parentesi graffe (`{}`).</span><span class="sxs-lookup"><span data-stu-id="1ff84-218">To do this, surround the initialization values with braces (`{}`).</span></span>  
  
```vb  
Dim longArray() As Long = {0, 1, 2, 3}  
```  
  
 <span data-ttu-id="1ff84-219">Per le matrici multidimensionali, l'inizializzazione di ogni dimensione separata è racchiuso tra parentesi graffe nella dimensione esterna.</span><span class="sxs-lookup"><span data-stu-id="1ff84-219">For multidimensional arrays, the initialization for each separate dimension is enclosed in braces in the outer dimension.</span></span> <span data-ttu-id="1ff84-220">Gli elementi vengono specificati in ordine di riga.</span><span class="sxs-lookup"><span data-stu-id="1ff84-220">The elements are specified in row-major order.</span></span>  
  
```vb  
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}  
```  
  
 <span data-ttu-id="1ff84-221">Per altre informazioni sui valori letterali di matrice, vedere [matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="1ff84-221">For more information about array literals, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="default"></a> <span data-ttu-id="1ff84-222">Tipi di dati predefiniti e i valori</span><span class="sxs-lookup"><span data-stu-id="1ff84-222">Default Data Types and Values</span></span>  
 <span data-ttu-id="1ff84-223">Nella tabella seguente vengono descritti i risultati di varie combinazioni della specifica del tipo di dati e dell'inizializzatore in un'istruzione `Dim`.</span><span class="sxs-lookup"><span data-stu-id="1ff84-223">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>  
  
|<span data-ttu-id="1ff84-224">Tipo di dati specificato?</span><span class="sxs-lookup"><span data-stu-id="1ff84-224">Data type specified?</span></span>|<span data-ttu-id="1ff84-225">Inizializzatore specificato?</span><span class="sxs-lookup"><span data-stu-id="1ff84-225">Initializer specified?</span></span>|<span data-ttu-id="1ff84-226">Esempio</span><span class="sxs-lookup"><span data-stu-id="1ff84-226">Example</span></span>|<span data-ttu-id="1ff84-227">Risultato</span><span class="sxs-lookup"><span data-stu-id="1ff84-227">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="1ff84-228">No</span><span class="sxs-lookup"><span data-stu-id="1ff84-228">No</span></span>|<span data-ttu-id="1ff84-229">No</span><span class="sxs-lookup"><span data-stu-id="1ff84-229">No</span></span>|`Dim qty`|<span data-ttu-id="1ff84-230">Se [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) è disattivata (impostazione predefinita), la variabile è impostata su `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="1ff84-230">If [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="1ff84-231">Se `Option Strict` è abilitato, si verifica un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="1ff84-231">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="1ff84-232">No</span><span class="sxs-lookup"><span data-stu-id="1ff84-232">No</span></span>|<span data-ttu-id="1ff84-233">Yes</span><span class="sxs-lookup"><span data-stu-id="1ff84-233">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="1ff84-234">Se [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) è abilitata (impostazione predefinita), la variabile accetta i dati di tipo dell'inizializzatore.</span><span class="sxs-lookup"><span data-stu-id="1ff84-234">If [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="1ff84-235">Visualizzare [inferenza del tipo locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="1ff84-235">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="1ff84-236">Se le istruzioni `Option Infer` e `Option Strict` sono disabilitate, il tipo di dati accettato dalla variabile è `Object`.</span><span class="sxs-lookup"><span data-stu-id="1ff84-236">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="1ff84-237">Se `Option Infer` è disabilitato e `Option Strict` è abilitato, si verifica un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="1ff84-237">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="1ff84-238">Yes</span><span class="sxs-lookup"><span data-stu-id="1ff84-238">Yes</span></span>|<span data-ttu-id="1ff84-239">No</span><span class="sxs-lookup"><span data-stu-id="1ff84-239">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="1ff84-240">La variabile viene inizializzata sul valore predefinito per il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="1ff84-240">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="1ff84-241">Vedere la tabella più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="1ff84-241">See the table later in this section.</span></span>|  
|<span data-ttu-id="1ff84-242">Yes</span><span class="sxs-lookup"><span data-stu-id="1ff84-242">Yes</span></span>|<span data-ttu-id="1ff84-243">Yes</span><span class="sxs-lookup"><span data-stu-id="1ff84-243">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="1ff84-244">Se il tipo di dati dell'inizializzatore non è convertibile nel tipo di dati specificato, si verifica un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="1ff84-244">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
 <span data-ttu-id="1ff84-245">Se si specifica un tipo di dati ma non si specifica un inizializzatore, Visual Basic consente di inizializzare la variabile sul valore predefinito per il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="1ff84-245">If you specify a data type but do not specify an initializer, Visual Basic initializes the variable to the default value for its data type.</span></span> <span data-ttu-id="1ff84-246">La tabella seguente illustra l'impostazione predefinita i valori di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="1ff84-246">The following table shows the default initialization values.</span></span>  
  
|<span data-ttu-id="1ff84-247">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="1ff84-247">Data type</span></span>|<span data-ttu-id="1ff84-248">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="1ff84-248">Default value</span></span>|  
|---|---|  
|<span data-ttu-id="1ff84-249">Tutti i tipi numerici (incluso `Byte` e `SByte`)</span><span class="sxs-lookup"><span data-stu-id="1ff84-249">All numeric types (including `Byte` and `SByte`)</span></span>|<span data-ttu-id="1ff84-250">0</span><span class="sxs-lookup"><span data-stu-id="1ff84-250">0</span></span>|  
|`Char`|<span data-ttu-id="1ff84-251">Binario 0</span><span class="sxs-lookup"><span data-stu-id="1ff84-251">Binary 0</span></span>|  
|<span data-ttu-id="1ff84-252">I tipi di riferimento (incluso `Object`, `String`e tutte le matrici)</span><span class="sxs-lookup"><span data-stu-id="1ff84-252">All reference types (including `Object`, `String`, and all arrays)</span></span>|`Nothing`|  
|`Boolean`|`False`|  
|`Date`|<span data-ttu-id="1ff84-253">Dalle 24.00 del 1 ° gennaio dell'anno 1 (01/01/0001 12:00:00 AM)</span><span class="sxs-lookup"><span data-stu-id="1ff84-253">12:00 AM of January 1 of the year 1 (01/01/0001 12:00:00 AM)</span></span>|  
  
 <span data-ttu-id="1ff84-254">Ogni elemento di struttura viene inizializzato come se fosse una variabile separata.</span><span class="sxs-lookup"><span data-stu-id="1ff84-254">Each element of a structure is initialized as if it were a separate variable.</span></span> <span data-ttu-id="1ff84-255">Se si dichiara la lunghezza di una matrice, ma non si inizializzano gli elementi, ogni elemento viene inizializzato come se fosse una variabile separata.</span><span class="sxs-lookup"><span data-stu-id="1ff84-255">If you declare the length of an array but do not initialize its elements, each element is initialized as if it were a separate variable.</span></span>  
  
## <a name="static-local-variable-lifetime"></a><span data-ttu-id="1ff84-256">Durata delle variabili locale statica</span><span class="sxs-lookup"><span data-stu-id="1ff84-256">Static Local Variable Lifetime</span></span>  
 <span data-ttu-id="1ff84-257">Oggetto `Static` variabile locale ha una durata maggiore rispetto a quello della routine in cui è dichiarata.</span><span class="sxs-lookup"><span data-stu-id="1ff84-257">A `Static` local variable has a longer lifetime than that of the procedure in which it is declared.</span></span> <span data-ttu-id="1ff84-258">I limiti di durata della variabile dipendono in cui la routine è dichiarata e se è `Shared`.</span><span class="sxs-lookup"><span data-stu-id="1ff84-258">The boundaries of the variable's lifetime depend on where the procedure is declared and whether it is `Shared`.</span></span>  
  
|<span data-ttu-id="1ff84-259">Dichiarazione di routine</span><span class="sxs-lookup"><span data-stu-id="1ff84-259">Procedure declaration</span></span>|<span data-ttu-id="1ff84-260">Variabile inizializzata</span><span class="sxs-lookup"><span data-stu-id="1ff84-260">Variable initialized</span></span>|<span data-ttu-id="1ff84-261">Variabile arresta esistente</span><span class="sxs-lookup"><span data-stu-id="1ff84-261">Variable stops existing</span></span>|  
|---|---|---|  
|<span data-ttu-id="1ff84-262">In un modulo</span><span class="sxs-lookup"><span data-stu-id="1ff84-262">In a module</span></span>|<span data-ttu-id="1ff84-263">La prima volta che viene chiamata la procedura</span><span class="sxs-lookup"><span data-stu-id="1ff84-263">The first time the procedure is called</span></span>|<span data-ttu-id="1ff84-264">Quando il programma interrompe l'esecuzione</span><span class="sxs-lookup"><span data-stu-id="1ff84-264">When your program stops execution</span></span>|  
|<span data-ttu-id="1ff84-265">In una classe o struttura, è procedura `Shared`</span><span class="sxs-lookup"><span data-stu-id="1ff84-265">In a class or structure, procedure is `Shared`</span></span>|<span data-ttu-id="1ff84-266">La prima volta la procedura viene chiamata su un'istanza specifica o nella classe o struttura stessa</span><span class="sxs-lookup"><span data-stu-id="1ff84-266">The first time the procedure is called either on a specific instance or on the class or structure itself</span></span>|<span data-ttu-id="1ff84-267">Quando il programma interrompe l'esecuzione</span><span class="sxs-lookup"><span data-stu-id="1ff84-267">When your program stops execution</span></span>|  
|<span data-ttu-id="1ff84-268">In una classe o struttura, non è procedure `Shared`</span><span class="sxs-lookup"><span data-stu-id="1ff84-268">In a class or structure, procedure isn't `Shared`</span></span>|<span data-ttu-id="1ff84-269">La prima volta la procedura viene chiamata su una specifica istanza</span><span class="sxs-lookup"><span data-stu-id="1ff84-269">The first time the procedure is called on a specific instance</span></span>|<span data-ttu-id="1ff84-270">Quando l'istanza viene rilasciata per la garbage collection (GC)</span><span class="sxs-lookup"><span data-stu-id="1ff84-270">When the instance is released for garbage collection (GC)</span></span>|  
  
## <a name="attributes-and-modifiers"></a><span data-ttu-id="1ff84-271">Attributi e i modificatori</span><span class="sxs-lookup"><span data-stu-id="1ff84-271">Attributes and Modifiers</span></span>  
 <span data-ttu-id="1ff84-272">È possibile applicare gli attributi solo per le variabili membro, non per le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="1ff84-272">You can apply attributes only to member variables, not to local variables.</span></span> <span data-ttu-id="1ff84-273">Un attributo fornisce informazioni per i metadati dell'assembly, che non è significativo per l'archiviazione temporanea, ad esempio le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="1ff84-273">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local variables.</span></span>  
  
 <span data-ttu-id="1ff84-274">A livello di modulo, non è possibile usare il `Static` modificatore per dichiarare le variabili membro.</span><span class="sxs-lookup"><span data-stu-id="1ff84-274">At module level, you cannot use the `Static` modifier to declare member variables.</span></span> <span data-ttu-id="1ff84-275">A livello di routine, non è possibile usare `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, o qualsiasi modificatori di accesso per dichiarare le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="1ff84-275">At procedure level, you cannot use `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, or any access modifiers to declare local variables.</span></span>  
  
 <span data-ttu-id="1ff84-276">È possibile specificare il tipo di codice può accedere a una variabile, fornendo un `accessmodifier`.</span><span class="sxs-lookup"><span data-stu-id="1ff84-276">You can specify what code can access a variable by supplying an `accessmodifier`.</span></span> <span data-ttu-id="1ff84-277">Classe e il modulo predefinito di variabili (all'esterno di qualsiasi routine) membri per accesso privato e predefinita di variabili di membro di struttura per l'accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="1ff84-277">Class and module member variables (outside any procedure) default to private access, and structure member variables default to public access.</span></span> <span data-ttu-id="1ff84-278">È possibile modificare i livelli di accesso con i modificatori di accesso.</span><span class="sxs-lookup"><span data-stu-id="1ff84-278">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="1ff84-279">È possibile usare i modificatori di accesso con le variabili locali (all'interno di una routine).</span><span class="sxs-lookup"><span data-stu-id="1ff84-279">You cannot use access modifiers on local variables (inside a procedure).</span></span>  
  
 <span data-ttu-id="1ff84-280">È possibile specificare `WithEvents` solo le variabili membro, non le variabili locali all'interno di una routine.</span><span class="sxs-lookup"><span data-stu-id="1ff84-280">You can specify `WithEvents` only on member variables, not on local variables inside a procedure.</span></span> <span data-ttu-id="1ff84-281">Se si specifica `WithEvents`, il tipo di dati della variabile deve essere un tipo di classe specifica, non `Object`.</span><span class="sxs-lookup"><span data-stu-id="1ff84-281">If you specify `WithEvents`, the data type of the variable must be a specific class type, not `Object`.</span></span> <span data-ttu-id="1ff84-282">Non è possibile dichiarare una matrice con `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="1ff84-282">You cannot declare an array with `WithEvents`.</span></span> <span data-ttu-id="1ff84-283">Per altre informazioni sugli eventi, vedere [eventi](../../../visual-basic/programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="1ff84-283">For more information about events, see [Events](../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ff84-284">Codice esterno di una classe, struttura o un modulo necessario qualificare il nome della variabile di un membro con il nome di tale classe, struttura o modulo.</span><span class="sxs-lookup"><span data-stu-id="1ff84-284">Code outside a class, structure, or module must qualify a member variable's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="1ff84-285">All'esterno di che una routine o un blocco non può fare riferimento a variabili locali all'interno di tale routine o un blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="1ff84-285">Code outside a procedure or block cannot refer to any local variables within that procedure or block.</span></span>  
  
## <a name="releasing-managed-resources"></a><span data-ttu-id="1ff84-286">Rilasciare le risorse gestite</span><span class="sxs-lookup"><span data-stu-id="1ff84-286">Releasing Managed Resources</span></span>  
 <span data-ttu-id="1ff84-287">Il garbage collector di .NET Framework elimina le risorse gestite senza alcuna codifica aggiuntiva da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1ff84-287">The .NET Framework garbage collector disposes of managed resources without any extra coding on your part.</span></span> <span data-ttu-id="1ff84-288">Tuttavia, è possibile forzare l'eliminazione di una risorsa gestita anziché attendere che il garbage collector.</span><span class="sxs-lookup"><span data-stu-id="1ff84-288">However, you can force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="1ff84-289">Se una classe mantiene una risorsa particolarmente preziosa e scarsa (ad esempio, un handle di connessione o file di database), è possibile evitare di attendere la successiva garbage collection per pulire un'istanza della classe che non è più in uso.</span><span class="sxs-lookup"><span data-stu-id="1ff84-289">If a class holds onto a particularly valuable and scarce resource (such as a database connection or file handle), you might not want to wait until the next garbage collection to clean up a class instance that's no longer in use.</span></span> <span data-ttu-id="1ff84-290">Una classe può implementare il <xref:System.IDisposable> interfaccia per fornire un modo per rilasciare le risorse prima di un'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="1ff84-290">A class may implement the <xref:System.IDisposable> interface to provide a way to release resources before a garbage collection.</span></span> <span data-ttu-id="1ff84-291">Una classe che implementa l'interfaccia espone un `Dispose` metodo che può essere chiamato per forzare il rilascio immediato delle risorse preziose.</span><span class="sxs-lookup"><span data-stu-id="1ff84-291">A class that implements that interface exposes a `Dispose` method that can be called to force valuable resources to be released immediately.</span></span>  
  
 <span data-ttu-id="1ff84-292">Il `Using` istruzione consente di automatizzare il processo di acquisizione di una risorsa, l'esecuzione di un set di istruzioni e successivamente eliminando la risorsa.</span><span class="sxs-lookup"><span data-stu-id="1ff84-292">The `Using` statement automates the process of acquiring a resource, executing a set of statements, and then disposing of the resource.</span></span> <span data-ttu-id="1ff84-293">Tuttavia, è necessario implementare la risorsa di <xref:System.IDisposable> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="1ff84-293">However, the resource must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="1ff84-294">Per altre informazioni, vedere [Istruzione using](../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="1ff84-294">For more information, see [Using Statement](../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ff84-295">Esempio</span><span class="sxs-lookup"><span data-stu-id="1ff84-295">Example</span></span>  
 <span data-ttu-id="1ff84-296">L'esempio seguente dichiara le variabili usando i `Dim` istruzione con varie opzioni.</span><span class="sxs-lookup"><span data-stu-id="1ff84-296">The following example declares variables by using the `Dim` statement with various options.</span></span>  
  
 [!code-vb[VbVbalrStatements#141](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#141)]  
  
## <a name="example"></a><span data-ttu-id="1ff84-297">Esempio</span><span class="sxs-lookup"><span data-stu-id="1ff84-297">Example</span></span>  
 <span data-ttu-id="1ff84-298">L'esempio seguente elenca i numeri primi compreso tra 1 e 30.</span><span class="sxs-lookup"><span data-stu-id="1ff84-298">The following example lists the prime numbers between 1 and 30.</span></span> <span data-ttu-id="1ff84-299">L'ambito delle variabili locali è descritto nei commenti di codice.</span><span class="sxs-lookup"><span data-stu-id="1ff84-299">The scope of local variables is described in code comments.</span></span>  
  
 [!code-vb[VbVbalrStatements#142](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#142)]  
  
## <a name="example"></a><span data-ttu-id="1ff84-300">Esempio</span><span class="sxs-lookup"><span data-stu-id="1ff84-300">Example</span></span>  
 <span data-ttu-id="1ff84-301">Nell'esempio seguente, il `speedValue` variabile viene dichiarata a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="1ff84-301">In the following example, the `speedValue` variable is declared at the class level.</span></span> <span data-ttu-id="1ff84-302">Il `Private` parola chiave viene usata per dichiarare la variabile.</span><span class="sxs-lookup"><span data-stu-id="1ff84-302">The `Private` keyword is used to declare the variable.</span></span> <span data-ttu-id="1ff84-303">La variabile è accessibile da qualsiasi routine di `Car` classe.</span><span class="sxs-lookup"><span data-stu-id="1ff84-303">The variable can be accessed by any procedure in the `Car` class.</span></span>  
  
 [!code-vb[VbVbalrStatements#144](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#144)]  
  
 [!code-vb[VbVbalrStatements#145](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#145)]  
  
## <a name="see-also"></a><span data-ttu-id="1ff84-304">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ff84-304">See also</span></span>

- [<span data-ttu-id="1ff84-305">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="1ff84-305">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="1ff84-306">Istruzione ReDim</span><span class="sxs-lookup"><span data-stu-id="1ff84-306">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="1ff84-307">Istruzione Option Explicit</span><span class="sxs-lookup"><span data-stu-id="1ff84-307">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="1ff84-308">Istruzione Option Infer</span><span class="sxs-lookup"><span data-stu-id="1ff84-308">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="1ff84-309">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="1ff84-309">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="1ff84-310">Pagina Compilazione, Creazione progetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ff84-310">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [<span data-ttu-id="1ff84-311">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="1ff84-311">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="1ff84-312">Matrici</span><span class="sxs-lookup"><span data-stu-id="1ff84-312">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="1ff84-313">Inizializzatori di oggetto: Tipi denominati e anonimi</span><span class="sxs-lookup"><span data-stu-id="1ff84-313">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="1ff84-314">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="1ff84-314">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="1ff84-315">Inizializzatori di oggetto: Tipi denominati e anonimi</span><span class="sxs-lookup"><span data-stu-id="1ff84-315">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="1ff84-316">Procedura: Dichiarare un oggetto usando un inizializzatore di oggetto</span><span class="sxs-lookup"><span data-stu-id="1ff84-316">How to: Declare an Object by Using an Object Initializer</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
- [<span data-ttu-id="1ff84-317">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="1ff84-317">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)

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
ms.openlocfilehash: b3384b771748a1f2c9e841407042f81ce6ebe76d
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2018
ms.locfileid: "34234727"
---
# <a name="dim-statement-visual-basic"></a><span data-ttu-id="7f0a8-102">Istruzione Dim (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f0a8-102">Dim Statement (Visual Basic)</span></span>
<span data-ttu-id="7f0a8-103">Dichiara e alloca spazio di archiviazione per una o più variabili.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-103">Declares and allocates storage space for one or more variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f0a8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f0a8-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]   
Dim [ WithEvents ] variablelist  
```  
  
## <a name="parts"></a><span data-ttu-id="7f0a8-105">Parti</span><span class="sxs-lookup"><span data-stu-id="7f0a8-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="7f0a8-106">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-106">Optional.</span></span> <span data-ttu-id="7f0a8-107">Vedere [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="7f0a8-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="7f0a8-108">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-108">Optional.</span></span> <span data-ttu-id="7f0a8-109">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f0a8-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="7f0a8-110">Public</span><span class="sxs-lookup"><span data-stu-id="7f0a8-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="7f0a8-111">Protected</span><span class="sxs-lookup"><span data-stu-id="7f0a8-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="7f0a8-112">Friend</span><span class="sxs-lookup"><span data-stu-id="7f0a8-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="7f0a8-113">Private</span><span class="sxs-lookup"><span data-stu-id="7f0a8-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   [<span data-ttu-id="7f0a8-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="7f0a8-114">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)
    
    - [<span data-ttu-id="7f0a8-115">Protetto privato</span><span class="sxs-lookup"><span data-stu-id="7f0a8-115">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

     <span data-ttu-id="7f0a8-116">Vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="7f0a8-116">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `Shared`  
  
     <span data-ttu-id="7f0a8-117">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-117">Optional.</span></span> <span data-ttu-id="7f0a8-118">Vedere [condiviso](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="7f0a8-118">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="7f0a8-119">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-119">Optional.</span></span> <span data-ttu-id="7f0a8-120">Vedere [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="7f0a8-120">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Static`  
  
     <span data-ttu-id="7f0a8-121">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-121">Optional.</span></span> <span data-ttu-id="7f0a8-122">Vedere [statico](../../../visual-basic/language-reference/modifiers/static.md).</span><span class="sxs-lookup"><span data-stu-id="7f0a8-122">See [Static](../../../visual-basic/language-reference/modifiers/static.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="7f0a8-123">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-123">Optional.</span></span> <span data-ttu-id="7f0a8-124">Vedere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="7f0a8-124">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WithEvents`  
  
     <span data-ttu-id="7f0a8-125">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-125">Optional.</span></span> <span data-ttu-id="7f0a8-126">Specifica che si tratta di variabili oggetto che fanno riferimento a istanze di una classe che può generare eventi.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-126">Specifies that these are object variables that refer to instances of a class that can raise events.</span></span> <span data-ttu-id="7f0a8-127">Vedere [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="7f0a8-127">See [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span></span>  
  
-   `variablelist`  
  
     <span data-ttu-id="7f0a8-128">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-128">Required.</span></span> <span data-ttu-id="7f0a8-129">Elenco di variabili dichiarate in questa istruzione.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-129">List of variables being declared in this statement.</span></span>  
  
     `variable [ , variable ... ]`  
  
     <span data-ttu-id="7f0a8-130">Ogni `variable` presenta la sintassi e le parti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f0a8-130">Each `variable` has the following syntax and parts:</span></span>  
  
     <span data-ttu-id="7f0a8-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="7f0a8-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="7f0a8-132">Parte</span><span class="sxs-lookup"><span data-stu-id="7f0a8-132">Part</span></span>|<span data-ttu-id="7f0a8-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f0a8-133">Description</span></span>|  
    |---|---|  
    |`variablename`|<span data-ttu-id="7f0a8-134">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-134">Required.</span></span> <span data-ttu-id="7f0a8-135">Nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-135">Name of the variable.</span></span> <span data-ttu-id="7f0a8-136">Vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="7f0a8-136">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
    |`boundslist`|<span data-ttu-id="7f0a8-137">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-137">Optional.</span></span> <span data-ttu-id="7f0a8-138">Elenco dei limiti di ciascuna dimensione della variabile di matrice.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-138">List of bounds of each dimension of an array variable.</span></span>|  
    |`New`|<span data-ttu-id="7f0a8-139">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-139">Optional.</span></span> <span data-ttu-id="7f0a8-140">Crea una nuova istanza della classe quando il `Dim` istruzione viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-140">Creates a new instance of the class when the `Dim` statement runs.</span></span>|  
    |`datatype`|<span data-ttu-id="7f0a8-141">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-141">Optional.</span></span> <span data-ttu-id="7f0a8-142">Tipo di dati della variabile.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-142">Data type of the variable.</span></span>|  
    |`With`|<span data-ttu-id="7f0a8-143">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-143">Optional.</span></span> <span data-ttu-id="7f0a8-144">Introduce l'elenco di inizializzatori di oggetto.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-144">Introduces the object initializer list.</span></span>|  
    |`propertyname`|<span data-ttu-id="7f0a8-145">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-145">Optional.</span></span> <span data-ttu-id="7f0a8-146">Il nome di una proprietà nella classe crei un'istanza di.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-146">The name of a property in the class you are making an instance of.</span></span>|  
    |`propinitializer`|<span data-ttu-id="7f0a8-147">Necessario dopo avere `propertyname` =.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-147">Required after `propertyname` =.</span></span> <span data-ttu-id="7f0a8-148">L'espressione viene valutata e assegnata al nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-148">The expression that is evaluated and assigned to the property name.</span></span>|  
    |`initializer`|<span data-ttu-id="7f0a8-149">Facoltativo se `New` non è specificato.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-149">Optional if `New` is not specified.</span></span> <span data-ttu-id="7f0a8-150">Espressione che viene valutata e assegnata alla variabile quando viene creato.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-150">Expression that is evaluated and assigned to the variable when it is created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f0a8-151">Note</span><span class="sxs-lookup"><span data-stu-id="7f0a8-151">Remarks</span></span>  
 <span data-ttu-id="7f0a8-152">Il compilatore Visual Basic utilizza il `Dim` istruzione per determinare il tipo di dati della variabile e altre informazioni, ad esempio il codice che può accedere alla variabile.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-152">The Visual Basic compiler uses the `Dim` statement to determine the variable's data type and other information, such as what code can access the variable.</span></span> <span data-ttu-id="7f0a8-153">Nell'esempio seguente viene dichiarata una variabile per contenere un `Integer` valore.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-153">The following example declares a variable to hold an `Integer` value.</span></span>  
  
```vb  
Dim numberOfStudents As Integer  
```  
  
 <span data-ttu-id="7f0a8-154">È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, struttura, classe o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-154">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
```vb  
Dim finished As Boolean  
Dim monitorBox As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="7f0a8-155">Per un tipo riferimento, utilizzare il `New` (parola chiave) per creare una nuova istanza della classe o una struttura che viene specificato dal tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-155">For a reference type, you use the `New` keyword to create a new instance of the class or structure that is specified by the data type.</span></span> <span data-ttu-id="7f0a8-156">Se si utilizza `New`, non si utilizza un'espressione dell'inizializzatore.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-156">If you use `New`, you do not use an initializer expression.</span></span> <span data-ttu-id="7f0a8-157">Al contrario, specificare argomenti, se sono necessarie, per il costruttore della classe da cui si sta creando la variabile.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-157">Instead, you supply arguments, if they are required, to the constructor of the class from which you are creating the variable.</span></span>  
  
```vb  
Dim bottomLabel As New System.Windows.Forms.Label  
```  
  
 <span data-ttu-id="7f0a8-158">È possibile dichiarare una variabile in una stored procedure, blocco, classe, struttura o modulo.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-158">You can declare a variable in a procedure, block, class, structure, or module.</span></span> <span data-ttu-id="7f0a8-159">È possibile dichiarare una variabile in un file di origine, lo spazio dei nomi o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-159">You cannot declare a variable in a source file, namespace, or interface.</span></span> <span data-ttu-id="7f0a8-160">Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="7f0a8-160">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="7f0a8-161">È una variabile dichiarata a livello di modulo, all'esterno di qualsiasi routine, un *variabile membro* o *campo*.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-161">A variable that is declared at module level, outside any procedure, is a *member variable* or *field*.</span></span> <span data-ttu-id="7f0a8-162">Le variabili membro sono nell'ambito in tutta la classe, struttura o modulo.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-162">Member variables are in scope throughout their class, structure, or module.</span></span> <span data-ttu-id="7f0a8-163">Una variabile dichiarata a livello di routine è un *variabile locale*.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-163">A variable that is declared at procedure level is a *local variable*.</span></span> <span data-ttu-id="7f0a8-164">Le variabili locali sono nell'ambito solo all'interno della routine o un blocco.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-164">Local variables are in scope only within their procedure or block.</span></span>  
  
 <span data-ttu-id="7f0a8-165">I seguenti modificatori di accesso vengono utilizzati per dichiarare le variabili all'esterno di una stored procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, e `Private`.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-165">The following access modifiers are used to declare variables outside a procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private`.</span></span> <span data-ttu-id="7f0a8-166">Per ulteriori informazioni, vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="7f0a8-166">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="7f0a8-167">Il `Dim` parola chiave è facoltativa e in genere omesso se si specifica uno dei seguenti modificatori: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, o `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-167">The `Dim` keyword is optional and usually omitted if you specify any of the following modifiers: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, or `WithEvents`.</span></span>  
  
```vb  
Public maximumAllowed As Double  
Protected Friend currentUserName As String  
Private salary As Decimal  
Static runningTotal As Integer  
```  
  
 <span data-ttu-id="7f0a8-168">Se `Option Explicit` è (impostazione predefinita), il compilatore richiede una dichiarazione per ciascuna variabile utilizzata.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-168">If `Option Explicit` is on (the default), the compiler requires a declaration for every variable you use.</span></span> <span data-ttu-id="7f0a8-169">Per ulteriori informazioni, vedere [istruzione Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7f0a8-169">For more information, see [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span></span>  
  
## <a name="specifying-an-initial-value"></a><span data-ttu-id="7f0a8-170">Specificare un valore iniziale</span><span class="sxs-lookup"><span data-stu-id="7f0a8-170">Specifying an Initial Value</span></span>  
 <span data-ttu-id="7f0a8-171">Quando viene creato, è possibile assegnare un valore a una variabile.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-171">You can assign a value to a variable when it is created.</span></span> <span data-ttu-id="7f0a8-172">Per un tipo valore, utilizzare un *inizializzatore* per fornire un'espressione da assegnare alla variabile.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-172">For a value type, you use an *initializer* to supply an expression to be assigned to the variable.</span></span> <span data-ttu-id="7f0a8-173">L'espressione deve restituire una costante che può essere calcolata in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-173">The expression must evaluate to a constant that can be calculated at compile time.</span></span>  
  
```vb  
Dim quantity As Integer = 10  
Dim message As String = "Just started"  
```  
  
 <span data-ttu-id="7f0a8-174">Se viene specificato un inizializzatore e non viene specificato un tipo di dati un `As` clausola *l'inferenza del tipo* viene utilizzato per dedurre il tipo di dati dall'inizializzatore.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-174">If an initializer is specified and a data type is not specified in an `As` clause, *type inference* is used to infer the data type from the initializer.</span></span> <span data-ttu-id="7f0a8-175">Nell'esempio seguente, entrambi `num1` e `num2` sono fortemente tipizzati come integer.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-175">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span> <span data-ttu-id="7f0a8-176">Nella seconda dichiarazione, l'inferenza del tipo deduce il tipo dal valore 3.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-176">In the second declaration, type inference infers the type from the value 3.</span></span>  
  
```vb  
' Use explicit typing.  
Dim num1 As Integer = 3  
  
' Use local type inference.  
Dim num2 = 3  
```  
  
 <span data-ttu-id="7f0a8-177">L'inferenza del tipo si applica a livello di routine.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-177">Type inference applies at the procedure level.</span></span> <span data-ttu-id="7f0a8-178">Non è applicabile all'esterno di una routine in una classe, struttura, modulo o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-178">It does not apply outside a procedure in a class, structure, module, or interface.</span></span> <span data-ttu-id="7f0a8-179">Per ulteriori informazioni sull'inferenza del tipo, vedere [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) e [locale l'inferenza del tipo](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="7f0a8-179">For more information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
 <span data-ttu-id="7f0a8-180">Per informazioni su ciò che accade quando un tipo di dati o l'inizializzatore non è specificato, vedere [valori e tipi di dati predefiniti](../../../visual-basic/language-reference/statements/dim-statement.md#default) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-180">For information about what happens when a data type or initializer is not specified, see [Default Data Types and Values](../../../visual-basic/language-reference/statements/dim-statement.md#default) later in this topic.</span></span>  
  
 <span data-ttu-id="7f0a8-181">È possibile utilizzare un *inizializzatore di oggetto* per dichiarare le istanze di tipi denominati e anonimi.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-181">You can use an *object initializer* to declare instances of named and anonymous types.</span></span> <span data-ttu-id="7f0a8-182">Il codice seguente crea un'istanza di un `Student` classe e utilizza un inizializzatore di oggetto per inizializzare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-182">The following code creates an instance of a `Student` class and uses an object initializer to initialize properties.</span></span>  
  
```vb  
Dim student1 As New Student With {.First = "Michael",   
                                  .Last = "Tucker"}  
```  
  
 <span data-ttu-id="7f0a8-183">Per ulteriori informazioni sugli inizializzatori di oggetti, vedere [procedura: dichiarare un oggetto utilizzando un inizializzatore di oggetto](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [gli inizializzatori di oggetto: tipi denominati e anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), e [tipi anonimi ](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="7f0a8-183">For more information about object initializers, see [How to: Declare an Object by Using an Object Initializer](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), and [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="declaring-multiple-variables"></a><span data-ttu-id="7f0a8-184">Dichiarazione di variabili di più</span><span class="sxs-lookup"><span data-stu-id="7f0a8-184">Declaring Multiple Variables</span></span>  
 <span data-ttu-id="7f0a8-185">È possibile dichiarare più variabili in un'istruzione di dichiarazione, specificando il nome della variabile per ognuno di essi e dopo ogni nome di matrice con parentesi.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-185">You can declare several variables in one declaration statement, specifying the variable name for each one, and following each array name with parentheses.</span></span> <span data-ttu-id="7f0a8-186">Nel caso di più variabili, è possibile separarle mediante virgole.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-186">Multiple variables are separated by commas.</span></span>  
  
```vb  
Dim lastTime, nextTime, allTimes() As Date  
```  
  
 <span data-ttu-id="7f0a8-187">Se si dichiarano più variabili con uno `As` clausola, non è possibile specificare un inizializzatore per tale gruppo di variabili.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-187">If you declare more than one variable with one `As` clause, you cannot supply an initializer for that group of variables.</span></span>  
  
 <span data-ttu-id="7f0a8-188">È possibile specificare i tipi di dati diversi per variabili differenti utilizzando un oggetto separato `As` clausola per ogni variabile è dichiarata.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-188">You can specify different data types for different variables by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="7f0a8-189">Ogni variabile accetta il tipo di dati specificato nel primo `As` clausola rilevata dopo il relativo `variablename` parte.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-189">Each variable takes the data type specified in the first `As` clause encountered after its `variablename` part.</span></span>  
  
```vb  
Dim a, b, c As Single, x, y As Double, i As Integer  
' a, b, and c are all Single; x and y are both Double  
```  
  
## <a name="arrays"></a><span data-ttu-id="7f0a8-190">Matrici</span><span class="sxs-lookup"><span data-stu-id="7f0a8-190">Arrays</span></span>  
 <span data-ttu-id="7f0a8-191">È possibile dichiarare una variabile per contenere un *matrice*, che può contenere più valori.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-191">You can declare a variable to hold an *array*, which can hold multiple values.</span></span> <span data-ttu-id="7f0a8-192">Per specificare che una variabile contiene una matrice, seguire la `variablename` immediatamente con parentesi.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-192">To specify that a variable holds an array, follow its `variablename` immediately with parentheses.</span></span> <span data-ttu-id="7f0a8-193">Per ulteriori informazioni sulle matrici, vedere [matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="7f0a8-193">For more information about arrays, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="7f0a8-194">È possibile specificare il limite inferiore e superiore di ciascuna dimensione della matrice.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-194">You can specify the lower and upper bound of each dimension of an array.</span></span> <span data-ttu-id="7f0a8-195">A tale scopo, includere un `boundslist` all'interno delle parentesi.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-195">To do this, include a `boundslist` inside the parentheses.</span></span> <span data-ttu-id="7f0a8-196">Per ogni dimensione, il `boundslist` specifica il limite superiore e facoltativamente il limite inferiore.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-196">For each dimension, the `boundslist` specifies the upper bound and optionally the lower bound.</span></span> <span data-ttu-id="7f0a8-197">Il limite inferiore è sempre uguale a zero, se specifichi o meno.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-197">The lower bound is always zero, whether you specify it or not.</span></span> <span data-ttu-id="7f0a8-198">Ogni indice possono variare da zero tramite il relativo valore limite superiore.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-198">Each index can vary from zero through its upper bound value.</span></span>  
  
 <span data-ttu-id="7f0a8-199">Le due istruzioni seguenti sono equivalenti.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-199">The following two statements are equivalent.</span></span> <span data-ttu-id="7f0a8-200">Ogni istruzione dichiara una matrice di 21 `Integer` elementi.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-200">Each statement declares an array of 21 `Integer` elements.</span></span> <span data-ttu-id="7f0a8-201">Quando si accede di matrice, l'indice può variare da 0 a 20.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-201">When you access the array, the index can vary from 0 through 20.</span></span>  
  
```vb  
Dim totals(20) As Integer  
Dim totals(0 To 20) As Integer  
```  
  
 <span data-ttu-id="7f0a8-202">L'istruzione seguente dichiara una matrice bidimensionale di tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-202">The following statement declares a two-dimensional array of type `Double`.</span></span> <span data-ttu-id="7f0a8-203">La matrice è 4 righe (3 + 1) di 6 colonne (5 + 1) ogni.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-203">The array has 4 rows (3 + 1) of 6 columns (5 + 1) each.</span></span> <span data-ttu-id="7f0a8-204">Si noti che il limite superiore rappresenta il valore più alto possibile per l'indice, non la lunghezza della dimensione.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-204">Note that an upper bound represents the highest possible value for the index, not the length of the dimension.</span></span> <span data-ttu-id="7f0a8-205">La lunghezza della dimensione è il limite superiore più uno.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-205">The length of the dimension is the upper bound plus one.</span></span>  
  
```vb  
Dim matrix2(3, 5) As Double  
```  
  
 <span data-ttu-id="7f0a8-206">Una matrice può avere da 1 a 32 dimensioni.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-206">An array can have from 1 to 32 dimensions.</span></span>  
  
 <span data-ttu-id="7f0a8-207">È possibile lasciare vuoto in una dichiarazione di matrice tutti i limiti.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-207">You can leave all the bounds blank in an array declaration.</span></span> <span data-ttu-id="7f0a8-208">In questo caso, la matrice disponga del numero di dimensioni specificato, ma non viene inizializzata.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-208">If you do this, the array has the number of dimensions you specify, but it is uninitialized.</span></span> <span data-ttu-id="7f0a8-209">Ha un valore `Nothing` fino a quando non si inizializzano alcuni dei relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-209">It has a value of `Nothing` until you initialize at least some of its elements.</span></span> <span data-ttu-id="7f0a8-210">Il `Dim` istruzione deve specificare limiti per tutte le dimensioni o Nessuna dimensione.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-210">The `Dim` statement must specify bounds either for all dimensions or for no dimensions.</span></span>  
  
```vb  
' Declare an array with blank array bounds.  
Dim messages() As String  
' Initialize the array.  
ReDim messages(4)  
```  
  
 <span data-ttu-id="7f0a8-211">Se la matrice contiene più di una dimensione, è necessario includere una virgola tra le parentesi per indicare il numero di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-211">If the array has more than one dimension, you must include commas between the parentheses to indicate the number of dimensions.</span></span>  
  
```vb  
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte  
```  
  
 <span data-ttu-id="7f0a8-212">È possibile dichiarare un *matrice di lunghezza zero* dichiarando una delle dimensioni della matrice-1.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-212">You can declare a *zero-length array* by declaring one of the array's dimensions to be -1.</span></span> <span data-ttu-id="7f0a8-213">Il valore di una variabile che contiene una matrice di lunghezza zero è `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-213">A variable that holds a zero-length array does not have the value `Nothing`.</span></span> <span data-ttu-id="7f0a8-214">Matrici di lunghezza zero sono richiesti da alcune funzioni di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-214">Zero-length arrays are required by certain common language runtime functions.</span></span> <span data-ttu-id="7f0a8-215">Se si tenta di accedere a una matrice di questo tipo, si verifica un'eccezione di runtime.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-215">If you try to access such an array, a runtime exception occurs.</span></span> <span data-ttu-id="7f0a8-216">Per ulteriori informazioni, vedere [matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="7f0a8-216">For more information, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="7f0a8-217">È possibile inizializzare i valori di una matrice con un valore letterale della matrice.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-217">You can initialize the values of an array by using an array literal.</span></span> <span data-ttu-id="7f0a8-218">A tale scopo, racchiudere i valori di inizializzazione con parentesi graffe (`{}`).</span><span class="sxs-lookup"><span data-stu-id="7f0a8-218">To do this, surround the initialization values with braces (`{}`).</span></span>  
  
```vb  
Dim longArray() As Long = {0, 1, 2, 3}  
```  
  
 <span data-ttu-id="7f0a8-219">Per le matrici multidimensionali, l'inizializzazione di ciascuna dimensione separata è racchiuso tra parentesi graffe all'interno della dimensione esterna.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-219">For multidimensional arrays, the initialization for each separate dimension is enclosed in braces in the outer dimension.</span></span> <span data-ttu-id="7f0a8-220">Gli elementi vengono specificati in ordine crescente di riga.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-220">The elements are specified in row-major order.</span></span>  
  
```vb  
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}  
```  
  
 <span data-ttu-id="7f0a8-221">Per ulteriori informazioni sui valori letterali di matrice, vedere [matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="7f0a8-221">For more information about array literals, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
##  <a name="default"></a> <span data-ttu-id="7f0a8-222">Tipi di dati predefiniti e valori</span><span class="sxs-lookup"><span data-stu-id="7f0a8-222">Default Data Types and Values</span></span>  
 <span data-ttu-id="7f0a8-223">Nella tabella seguente vengono descritti i risultati di varie combinazioni della specifica del tipo di dati e dell'inizializzatore in un'istruzione `Dim`.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-223">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>  
  
|<span data-ttu-id="7f0a8-224">Tipo di dati specificato?</span><span class="sxs-lookup"><span data-stu-id="7f0a8-224">Data type specified?</span></span>|<span data-ttu-id="7f0a8-225">Inizializzatore specificato?</span><span class="sxs-lookup"><span data-stu-id="7f0a8-225">Initializer specified?</span></span>|<span data-ttu-id="7f0a8-226">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f0a8-226">Example</span></span>|<span data-ttu-id="7f0a8-227">Risultato</span><span class="sxs-lookup"><span data-stu-id="7f0a8-227">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="7f0a8-228">No</span><span class="sxs-lookup"><span data-stu-id="7f0a8-228">No</span></span>|<span data-ttu-id="7f0a8-229">No</span><span class="sxs-lookup"><span data-stu-id="7f0a8-229">No</span></span>|`Dim qty`|<span data-ttu-id="7f0a8-230">Se [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) è off (impostazione predefinita), la variabile è impostata su `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-230">If [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="7f0a8-231">Se `Option Strict` è abilitato, si verifica un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-231">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="7f0a8-232">No</span><span class="sxs-lookup"><span data-stu-id="7f0a8-232">No</span></span>|<span data-ttu-id="7f0a8-233">Yes</span><span class="sxs-lookup"><span data-stu-id="7f0a8-233">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="7f0a8-234">Se [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) è (impostazione predefinita), digitare la variabile accetta i dati dell'inizializzatore.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-234">If [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="7f0a8-235">Vedere [inferenza](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="7f0a8-235">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="7f0a8-236">Se le istruzioni `Option Infer` e `Option Strict` sono disabilitate, il tipo di dati accettato dalla variabile è `Object`.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-236">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="7f0a8-237">Se `Option Infer` è disabilitato e `Option Strict` è abilitato, si verifica un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-237">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="7f0a8-238">Sì</span><span class="sxs-lookup"><span data-stu-id="7f0a8-238">Yes</span></span>|<span data-ttu-id="7f0a8-239">No</span><span class="sxs-lookup"><span data-stu-id="7f0a8-239">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="7f0a8-240">La variabile viene inizializzata sul valore predefinito per il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-240">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="7f0a8-241">Vedere la tabella più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-241">See the table later in this section.</span></span>|  
|<span data-ttu-id="7f0a8-242">Yes</span><span class="sxs-lookup"><span data-stu-id="7f0a8-242">Yes</span></span>|<span data-ttu-id="7f0a8-243">Sì</span><span class="sxs-lookup"><span data-stu-id="7f0a8-243">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="7f0a8-244">Se il tipo di dati dell'inizializzatore non è convertibile nel tipo di dati specificato, si verifica un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-244">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
 <span data-ttu-id="7f0a8-245">Se si specifica un tipo di dati ma non si specifica un inizializzatore, Visual Basic Inizializza la variabile sul valore predefinito per il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-245">If you specify a data type but do not specify an initializer, Visual Basic initializes the variable to the default value for its data type.</span></span> <span data-ttu-id="7f0a8-246">Nella tabella seguente mostra il valore predefinito di valori di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-246">The following table shows the default initialization values.</span></span>  
  
|<span data-ttu-id="7f0a8-247">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7f0a8-247">Data type</span></span>|<span data-ttu-id="7f0a8-248">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="7f0a8-248">Default value</span></span>|  
|---|---|  
|<span data-ttu-id="7f0a8-249">Tutti i tipi numerici (inclusi `Byte` e `SByte`)</span><span class="sxs-lookup"><span data-stu-id="7f0a8-249">All numeric types (including `Byte` and `SByte`)</span></span>|<span data-ttu-id="7f0a8-250">0</span><span class="sxs-lookup"><span data-stu-id="7f0a8-250">0</span></span>|  
|`Char`|<span data-ttu-id="7f0a8-251">Binario 0</span><span class="sxs-lookup"><span data-stu-id="7f0a8-251">Binary 0</span></span>|  
|<span data-ttu-id="7f0a8-252">I tipi di riferimento (inclusi `Object`, `String`e tutte le matrici)</span><span class="sxs-lookup"><span data-stu-id="7f0a8-252">All reference types (including `Object`, `String`, and all arrays)</span></span>|`Nothing`|  
|`Boolean`|`False`|  
|`Date`|<span data-ttu-id="7f0a8-253">Mezzanotte del 1 ° gennaio dell'anno 1 (01/01/0001 12:00:00 AM)</span><span class="sxs-lookup"><span data-stu-id="7f0a8-253">12:00 AM of January 1 of the year 1 (01/01/0001 12:00:00 AM)</span></span>|  
  
 <span data-ttu-id="7f0a8-254">Ogni elemento di una struttura viene inizializzato come se fosse una variabile separata.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-254">Each element of a structure is initialized as if it were a separate variable.</span></span> <span data-ttu-id="7f0a8-255">Se si dichiara la lunghezza di una matrice, ma non si inizializza gli elementi, ogni elemento viene inizializzato come se fosse una variabile separata.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-255">If you declare the length of an array but do not initialize its elements, each element is initialized as if it were a separate variable.</span></span>  
  
## <a name="static-local-variable-lifetime"></a><span data-ttu-id="7f0a8-256">Durata della variabile locale statica</span><span class="sxs-lookup"><span data-stu-id="7f0a8-256">Static Local Variable Lifetime</span></span>  
 <span data-ttu-id="7f0a8-257">Oggetto `Static` variabile locale ha una durata maggiore rispetto a quello della routine in cui viene dichiarato.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-257">A `Static` local variable has a longer lifetime than that of the procedure in which it is declared.</span></span> <span data-ttu-id="7f0a8-258">I limiti di durata della variabile dipendono in cui la routine viene dichiarata e se è `Shared`.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-258">The boundaries of the variable's lifetime depend on where the procedure is declared and whether it is `Shared`.</span></span>  
  
|<span data-ttu-id="7f0a8-259">Dichiarazione di routine</span><span class="sxs-lookup"><span data-stu-id="7f0a8-259">Procedure declaration</span></span>|<span data-ttu-id="7f0a8-260">Variabile inizializzata</span><span class="sxs-lookup"><span data-stu-id="7f0a8-260">Variable initialized</span></span>|<span data-ttu-id="7f0a8-261">Variabile arresta esistente</span><span class="sxs-lookup"><span data-stu-id="7f0a8-261">Variable stops existing</span></span>|  
|---|---|---|  
|<span data-ttu-id="7f0a8-262">In un modulo</span><span class="sxs-lookup"><span data-stu-id="7f0a8-262">In a module</span></span>|<span data-ttu-id="7f0a8-263">La prima volta che viene chiamata la procedura</span><span class="sxs-lookup"><span data-stu-id="7f0a8-263">The first time the procedure is called</span></span>|<span data-ttu-id="7f0a8-264">Arresto dell'esecuzione del programma</span><span class="sxs-lookup"><span data-stu-id="7f0a8-264">When your program stops execution</span></span>|  
|<span data-ttu-id="7f0a8-265">In una classe o struttura, procedura è `Shared`</span><span class="sxs-lookup"><span data-stu-id="7f0a8-265">In a class or structure, procedure is `Shared`</span></span>|<span data-ttu-id="7f0a8-266">La prima volta la procedura viene chiamata su un'istanza specifica o nella classe o struttura stessa</span><span class="sxs-lookup"><span data-stu-id="7f0a8-266">The first time the procedure is called either on a specific instance or on the class or structure itself</span></span>|<span data-ttu-id="7f0a8-267">Arresto dell'esecuzione del programma</span><span class="sxs-lookup"><span data-stu-id="7f0a8-267">When your program stops execution</span></span>|  
|<span data-ttu-id="7f0a8-268">In una classe o struttura, non è stored procedure `Shared`</span><span class="sxs-lookup"><span data-stu-id="7f0a8-268">In a class or structure, procedure isn't `Shared`</span></span>|<span data-ttu-id="7f0a8-269">La prima volta che la routine viene chiamata su una specifica istanza</span><span class="sxs-lookup"><span data-stu-id="7f0a8-269">The first time the procedure is called on a specific instance</span></span>|<span data-ttu-id="7f0a8-270">Quando l'istanza viene rilasciata per l'operazione di garbage collection (GC)</span><span class="sxs-lookup"><span data-stu-id="7f0a8-270">When the instance is released for garbage collection (GC)</span></span>|  
  
## <a name="attributes-and-modifiers"></a><span data-ttu-id="7f0a8-271">Gli attributi e modificatori</span><span class="sxs-lookup"><span data-stu-id="7f0a8-271">Attributes and Modifiers</span></span>  
 <span data-ttu-id="7f0a8-272">È possibile applicare gli attributi solo per le variabili membro, non per le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-272">You can apply attributes only to member variables, not to local variables.</span></span> <span data-ttu-id="7f0a8-273">Un attributo fornisce informazioni per i metadati dell'assembly, che non è significativo per l'archiviazione temporanea, ad esempio le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-273">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local variables.</span></span>  
  
 <span data-ttu-id="7f0a8-274">A livello di modulo, è possibile utilizzare il `Static` modificatore per dichiarare le variabili membro.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-274">At module level, you cannot use the `Static` modifier to declare member variables.</span></span> <span data-ttu-id="7f0a8-275">A livello di routine, non è possibile utilizzare `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, o i modificatori di accesso per dichiarare le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-275">At procedure level, you cannot use `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, or any access modifiers to declare local variables.</span></span>  
  
 <span data-ttu-id="7f0a8-276">È possibile specificare il codice può accedere a una variabile fornendo un `accessmodifier`.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-276">You can specify what code can access a variable by supplying an `accessmodifier`.</span></span> <span data-ttu-id="7f0a8-277">Classe e modulo predefinito di variabili (all'esterno di qualsiasi routine) membro accesso privato e predefinito di variabili membro di struttura per l'accesso pubblico.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-277">Class and module member variables (outside any procedure) default to private access, and structure member variables default to public access.</span></span> <span data-ttu-id="7f0a8-278">È possibile regolare i livelli di accesso con i modificatori di accesso.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-278">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="7f0a8-279">È possibile utilizzare i modificatori di accesso con le variabili locali (all'interno di una routine).</span><span class="sxs-lookup"><span data-stu-id="7f0a8-279">You cannot use access modifiers on local variables (inside a procedure).</span></span>  
  
 <span data-ttu-id="7f0a8-280">È possibile specificare `WithEvents` solo a variabili membro, non le variabili locali all'interno di una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-280">You can specify `WithEvents` only on member variables, not on local variables inside a procedure.</span></span> <span data-ttu-id="7f0a8-281">Se si specifica `WithEvents`, il tipo di dati della variabile deve essere un tipo di classe specifico non `Object`.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-281">If you specify `WithEvents`, the data type of the variable must be a specific class type, not `Object`.</span></span> <span data-ttu-id="7f0a8-282">Non è possibile dichiarare una matrice con `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-282">You cannot declare an array with `WithEvents`.</span></span> <span data-ttu-id="7f0a8-283">Per ulteriori informazioni sugli eventi, vedere [eventi](../../../visual-basic/programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="7f0a8-283">For more information about events, see [Events](../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f0a8-284">Codice esterno di una classe, struttura o un modulo necessario qualificare il nome di una variabile membro con il nome di tale classe, struttura o modulo.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-284">Code outside a class, structure, or module must qualify a member variable's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="7f0a8-285">All'esterno di che una stored procedure o un blocco non può fare riferimento a variabili locali all'interno della routine o un blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-285">Code outside a procedure or block cannot refer to any local variables within that procedure or block.</span></span>  
  
## <a name="releasing-managed-resources"></a><span data-ttu-id="7f0a8-286">Rilasciare le risorse gestite</span><span class="sxs-lookup"><span data-stu-id="7f0a8-286">Releasing Managed Resources</span></span>  
 <span data-ttu-id="7f0a8-287">Il garbage collector di .NET Framework elimina le risorse gestite senza alcuna codifica aggiuntiva da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-287">The .NET Framework garbage collector disposes of managed resources without any extra coding on your part.</span></span> <span data-ttu-id="7f0a8-288">Tuttavia, è possibile forzare l'eliminazione di una risorsa gestita anziché attendere che il garbage collector.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-288">However, you can force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="7f0a8-289">Se una classe contiene una risorsa particolarmente preziosa e rara (ad esempio, un handle di connessione o file di database), è possibile evitare di attendere la successiva operazione di garbage collection per pulire un'istanza di classe che non è più in uso.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-289">If a class holds onto a particularly valuable and scarce resource (such as a database connection or file handle), you might not want to wait until the next garbage collection to clean up a class instance that's no longer in use.</span></span> <span data-ttu-id="7f0a8-290">Una classe può implementare il <xref:System.IDisposable> interfaccia per fornire un modo per rilasciare le risorse prima di un'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-290">A class may implement the <xref:System.IDisposable> interface to provide a way to release resources before a garbage collection.</span></span> <span data-ttu-id="7f0a8-291">Una classe che implementa l'interfaccia espone un `Dispose` metodo che può essere chiamato per forzare il rilascio immediato delle risorse importanti.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-291">A class that implements that interface exposes a `Dispose` method that can be called to force valuable resources to be released immediately.</span></span>  
  
 <span data-ttu-id="7f0a8-292">Il `Using` istruzione automatizza il processo di acquisizione di una risorsa, l'esecuzione di un set di istruzioni e quindi l'eliminazione della risorsa.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-292">The `Using` statement automates the process of acquiring a resource, executing a set of statements, and then disposing of the resource.</span></span> <span data-ttu-id="7f0a8-293">Tuttavia, è necessario implementare la risorsa di <xref:System.IDisposable> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-293">However, the resource must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="7f0a8-294">Per altre informazioni, vedere [Istruzione using](../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7f0a8-294">For more information, see [Using Statement](../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f0a8-295">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f0a8-295">Example</span></span>  
 <span data-ttu-id="7f0a8-296">Nell'esempio seguente dichiara variabili utilizzando la `Dim` istruzione con varie opzioni.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-296">The following example declares variables by using the `Dim` statement with various options.</span></span>  
  
 [!code-vb[VbVbalrStatements#141](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="7f0a8-297">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f0a8-297">Example</span></span>  
 <span data-ttu-id="7f0a8-298">Nell'esempio seguente vengono elencati i numeri primi compreso tra 1 e 30.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-298">The following example lists the prime numbers between 1 and 30.</span></span> <span data-ttu-id="7f0a8-299">L'ambito delle variabili locali è descritto nei commenti di codice.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-299">The scope of local variables is described in code comments.</span></span>  
  
 [!code-vb[VbVbalrStatements#142](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="7f0a8-300">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f0a8-300">Example</span></span>  
 <span data-ttu-id="7f0a8-301">Nell'esempio seguente, il `speedValue` variabile viene dichiarata a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-301">In the following example, the `speedValue` variable is declared at the class level.</span></span> <span data-ttu-id="7f0a8-302">Il `Private` parola chiave viene utilizzata per dichiarare la variabile.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-302">The `Private` keyword is used to declare the variable.</span></span> <span data-ttu-id="7f0a8-303">La variabile è accessibile da qualsiasi routine di `Car` classe.</span><span class="sxs-lookup"><span data-stu-id="7f0a8-303">The variable can be accessed by any procedure in the `Car` class.</span></span>  
  
 [!code-vb[VbVbalrStatements#144](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#145](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7f0a8-304">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f0a8-304">See Also</span></span>  
 [<span data-ttu-id="7f0a8-305">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="7f0a8-305">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="7f0a8-306">Istruzione ReDim</span><span class="sxs-lookup"><span data-stu-id="7f0a8-306">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="7f0a8-307">Istruzione Option Explicit</span><span class="sxs-lookup"><span data-stu-id="7f0a8-307">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="7f0a8-308">Istruzione Option Infer</span><span class="sxs-lookup"><span data-stu-id="7f0a8-308">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [<span data-ttu-id="7f0a8-309">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="7f0a8-309">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="7f0a8-310">Pagina Compilazione, Creazione progetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f0a8-310">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)  
 [<span data-ttu-id="7f0a8-311">Dichiarazione di variabile</span><span class="sxs-lookup"><span data-stu-id="7f0a8-311">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="7f0a8-312">Array</span><span class="sxs-lookup"><span data-stu-id="7f0a8-312">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="7f0a8-313">Inizializzatori di oggetto: tipi denominati e tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="7f0a8-313">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [<span data-ttu-id="7f0a8-314">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="7f0a8-314">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="7f0a8-315">Inizializzatori di oggetto: tipi denominati e tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="7f0a8-315">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [<span data-ttu-id="7f0a8-316">Procedura: Dichiarare un oggetto usando un inizializzatore di oggetto</span><span class="sxs-lookup"><span data-stu-id="7f0a8-316">How to: Declare an Object by Using an Object Initializer</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)  
 [<span data-ttu-id="7f0a8-317">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="7f0a8-317">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)

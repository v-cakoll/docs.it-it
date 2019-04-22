---
title: Elenco dei tipi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
ms.openlocfilehash: d071e59d94e51ca55167983d0ee3098bd5c7dd8f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58843630"
---
# <a name="type-list-visual-basic"></a><span data-ttu-id="ebed7-102">Elenco dei tipi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebed7-102">Type List (Visual Basic)</span></span>
<span data-ttu-id="ebed7-103">Specifica la *parametri di tipo* per una *generico* elemento di programmazione.</span><span class="sxs-lookup"><span data-stu-id="ebed7-103">Specifies the *type parameters* for a *generic* programming element.</span></span> <span data-ttu-id="ebed7-104">Più parametri sono separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="ebed7-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="ebed7-105">Di seguito è la sintassi per un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="ebed7-105">Following is the syntax for one type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebed7-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ebed7-106">Syntax</span></span>  
  
```  
[genericmodifier] typename [ As constraintlist ]  
```  
  
## <a name="parts"></a><span data-ttu-id="ebed7-107">Parti</span><span class="sxs-lookup"><span data-stu-id="ebed7-107">Parts</span></span>  
  
|<span data-ttu-id="ebed7-108">Termine</span><span class="sxs-lookup"><span data-stu-id="ebed7-108">Term</span></span>|<span data-ttu-id="ebed7-109">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebed7-109">Definition</span></span>|  
|---|---|  
|`genericmodifier`|<span data-ttu-id="ebed7-110">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ebed7-110">Optional.</span></span> <span data-ttu-id="ebed7-111">Può essere utilizzato solo in interfacce e delegati generici.</span><span class="sxs-lookup"><span data-stu-id="ebed7-111">Can be used only in generic interfaces and delegates.</span></span> <span data-ttu-id="ebed7-112">È possibile dichiarare un tipo covariante usando la [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) parola chiave o controvariante usando la [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="ebed7-112">You can declare a type covariant by using the [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) keyword or contravariant by using the [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) keyword.</span></span> <span data-ttu-id="ebed7-113">Vedere [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="ebed7-113">See [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>|  
|`typename`|<span data-ttu-id="ebed7-114">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ebed7-114">Required.</span></span> <span data-ttu-id="ebed7-115">Nome del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="ebed7-115">Name of the type parameter.</span></span> <span data-ttu-id="ebed7-116">Questo è un segnaposto, da sostituire con un tipo definito dall'argomento di tipo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ebed7-116">This is a placeholder, to be replaced by a defined type supplied by the corresponding type argument.</span></span>|  
|`constraintlist`|<span data-ttu-id="ebed7-117">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ebed7-117">Optional.</span></span> <span data-ttu-id="ebed7-118">Elenco di requisiti che vincolano il tipo di dati che può essere fornito per `typename`.</span><span class="sxs-lookup"><span data-stu-id="ebed7-118">List of requirements that constrain the data type that can be supplied for `typename`.</span></span> <span data-ttu-id="ebed7-119">Se si dispone di più vincoli, racchiuderli tra parentesi graffe (`{ }`) e separarle con virgole.</span><span class="sxs-lookup"><span data-stu-id="ebed7-119">If you have multiple constraints, enclose them in curly braces (`{ }`) and separate them with commas.</span></span> <span data-ttu-id="ebed7-120">È necessario introdurre l'elenco di vincoli con la [come](../../../visual-basic/language-reference/statements/as-clause.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="ebed7-120">You must introduce the constraint list with the [As](../../../visual-basic/language-reference/statements/as-clause.md) keyword.</span></span> <span data-ttu-id="ebed7-121">Si utilizza `As` una sola volta, all'inizio dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ebed7-121">You use `As` only once, at the beginning of the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebed7-122">Note</span><span class="sxs-lookup"><span data-stu-id="ebed7-122">Remarks</span></span>  
 <span data-ttu-id="ebed7-123">Ogni elemento di programmazione generica deve accettare almeno un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="ebed7-123">Every generic programming element must take at least one type parameter.</span></span> <span data-ttu-id="ebed7-124">Un parametro di tipo è un segnaposto per un tipo specifico (un *elemento costruito*) che il codice client specifica quando crea un'istanza del tipo generico.</span><span class="sxs-lookup"><span data-stu-id="ebed7-124">A type parameter is a placeholder for a specific type (a *constructed element*) that client code specifies when it creates an instance of the generic type.</span></span> <span data-ttu-id="ebed7-125">È possibile definire una classe generica, struttura, interfaccia, routine o delegato.</span><span class="sxs-lookup"><span data-stu-id="ebed7-125">You can define a generic class, structure, interface, procedure, or delegate.</span></span>  
  
 <span data-ttu-id="ebed7-126">Per altre informazioni sui casi in cui definire un tipo generico, vedere [tipi generici in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="ebed7-126">For more information on when to define a generic type, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span> <span data-ttu-id="ebed7-127">Per altre informazioni sui nomi dei parametri di tipo, vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="ebed7-127">For more information on type parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="ebed7-128">Regole</span><span class="sxs-lookup"><span data-stu-id="ebed7-128">Rules</span></span>  
  
-   <span data-ttu-id="ebed7-129">**Parentesi.**</span><span class="sxs-lookup"><span data-stu-id="ebed7-129">**Parentheses.**</span></span> <span data-ttu-id="ebed7-130">Se si fornisce un elenco di parametri di tipo, è necessario racchiuderlo tra parentesi ed è necessario introdurre l'elenco con il [di](../../../visual-basic/language-reference/statements/of-clause.md) (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="ebed7-130">If you supply a type parameter list, you must enclose it in parentheses, and you must introduce the list with the [Of](../../../visual-basic/language-reference/statements/of-clause.md) keyword.</span></span> <span data-ttu-id="ebed7-131">Si utilizza `Of` una sola volta, all'inizio dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ebed7-131">You use `Of` only once, at the beginning of the list.</span></span>  
  
-   <span data-ttu-id="ebed7-132">**Vincoli.**</span><span class="sxs-lookup"><span data-stu-id="ebed7-132">**Constraints.**</span></span> <span data-ttu-id="ebed7-133">Un elenco delle *vincoli* su un tipo di parametro può includere gli elementi seguenti in qualsiasi combinazione:</span><span class="sxs-lookup"><span data-stu-id="ebed7-133">A list of *constraints* on a type parameter can include the following items in any combination:</span></span>  
  
    -   <span data-ttu-id="ebed7-134">Numero qualsiasi di interfacce.</span><span class="sxs-lookup"><span data-stu-id="ebed7-134">Any number of interfaces.</span></span> <span data-ttu-id="ebed7-135">Il tipo specificato deve implementare tutte le interfacce in questo elenco.</span><span class="sxs-lookup"><span data-stu-id="ebed7-135">The supplied type must implement every interface in this list.</span></span>  
  
    -   <span data-ttu-id="ebed7-136">Al massimo una classe.</span><span class="sxs-lookup"><span data-stu-id="ebed7-136">At most one class.</span></span> <span data-ttu-id="ebed7-137">Il tipo specificato deve ereditare da quella classe.</span><span class="sxs-lookup"><span data-stu-id="ebed7-137">The supplied type must inherit from that class.</span></span>  
  
    -   <span data-ttu-id="ebed7-138">Parola chiave `New`.</span><span class="sxs-lookup"><span data-stu-id="ebed7-138">The `New` keyword.</span></span> <span data-ttu-id="ebed7-139">Il tipo fornito deve esporre un costruttore senza parametri accessibile il tipo generico.</span><span class="sxs-lookup"><span data-stu-id="ebed7-139">The supplied type must expose a parameterless constructor that your generic type can access.</span></span> <span data-ttu-id="ebed7-140">Ciò è utile se si vincola un parametro di tipo da una o più interfacce.</span><span class="sxs-lookup"><span data-stu-id="ebed7-140">This is useful if you constrain a type parameter by one or more interfaces.</span></span> <span data-ttu-id="ebed7-141">Un tipo che implementa le interfacce non necessariamente espone un costruttore e a seconda del livello di accesso di un costruttore, il codice all'interno del tipo generico potrebbe non essere in grado di accedervi.</span><span class="sxs-lookup"><span data-stu-id="ebed7-141">A type that implements interfaces does not necessarily expose a constructor, and depending on the access level of a constructor, the code within the generic type might not be able to access it.</span></span>  
  
    -   <span data-ttu-id="ebed7-142">Entrambi i `Class` parola chiave o il `Structure` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="ebed7-142">Either the `Class` keyword or the `Structure` keyword.</span></span> <span data-ttu-id="ebed7-143">Il `Class` parola chiave vincola un parametro di tipo generico per richiedere che qualsiasi argomento tipo passato da un tipo riferimento, ad esempio una stringa, matrice o delegato, o un oggetto creato da una classe.</span><span class="sxs-lookup"><span data-stu-id="ebed7-143">The `Class` keyword constrains a generic type parameter to require that any type argument passed to it be a reference type, for example a string, array, or delegate, or an object created from a class.</span></span> <span data-ttu-id="ebed7-144">Il `Structure` parola chiave vincola un parametro di tipo generico per richiedere che qualsiasi argomento tipo passato sia un tipo valore, ad esempio una struttura, enumerazione o tipo di dati di tipo.</span><span class="sxs-lookup"><span data-stu-id="ebed7-144">The `Structure` keyword constrains a generic type parameter to require that any type argument passed to it be a value type, for example a structure, enumeration, or elementary data type.</span></span> <span data-ttu-id="ebed7-145">Non è possibile includere `Class` e `Structure` nello stesso `constraintlist`.</span><span class="sxs-lookup"><span data-stu-id="ebed7-145">You cannot include both `Class` and `Structure` in the same `constraintlist`.</span></span>  
  
     <span data-ttu-id="ebed7-146">Il tipo specificato deve soddisfare tutti i requisiti inclusi in `constraintlist`.</span><span class="sxs-lookup"><span data-stu-id="ebed7-146">The supplied type must satisfy every requirement you include in `constraintlist`.</span></span>  
  
     <span data-ttu-id="ebed7-147">Vincoli su ogni parametro di tipo sono indipendenti dai vincoli su altri parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="ebed7-147">Constraints on each type parameter are independent of constraints on other type parameters.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="ebed7-148">Comportamento</span><span class="sxs-lookup"><span data-stu-id="ebed7-148">Behavior</span></span>  
  
-   <span data-ttu-id="ebed7-149">**Sostituzione in fase di compilazione.**</span><span class="sxs-lookup"><span data-stu-id="ebed7-149">**Compile-Time Substitution.**</span></span> <span data-ttu-id="ebed7-150">Quando si crea un tipo costruito da un elemento di programmazione generico, si fornisce un tipo definito per ogni parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="ebed7-150">When you create a constructed type from a generic programming element, you supply a defined type for each type parameter.</span></span> <span data-ttu-id="ebed7-151">Il compilatore Visual Basic sostituisce il tipo specificato per tutte le occorrenze di `typename` all'interno dell'elemento generico.</span><span class="sxs-lookup"><span data-stu-id="ebed7-151">The Visual Basic compiler substitutes that supplied type for every occurrence of `typename` within the generic element.</span></span>  
  
-   <span data-ttu-id="ebed7-152">**Assenza di vincoli.**</span><span class="sxs-lookup"><span data-stu-id="ebed7-152">**Absence of Constraints.**</span></span> <span data-ttu-id="ebed7-153">Se non si specifica alcun vincolo su un parametro di tipo, quest'ultima è limitato a operazioni e ai membri supportati dal [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) per tale parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="ebed7-153">If you do not specify any constraints on a type parameter, your code is limited to the operations and members supported by the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) for that type parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebed7-154">Esempio</span><span class="sxs-lookup"><span data-stu-id="ebed7-154">Example</span></span>  
 <span data-ttu-id="ebed7-155">Nell'esempio seguente illustra una struttura di definizione di una classe di dizionari generici, tra cui una funzione di base per aggiungere una nuova voce al dizionario.</span><span class="sxs-lookup"><span data-stu-id="ebed7-155">The following example shows a skeleton definition of a generic dictionary class, including a skeleton function to add a new entry to the dictionary.</span></span>  
  
 [!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="ebed7-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="ebed7-156">Example</span></span>  
 <span data-ttu-id="ebed7-157">Poiché `dictionary` è generico, il codice che lo utilizza può creare un'ampia gamma di oggetti da quest'ultimo, ciascuno con le stesse funzionalità ma che agiscono su un tipo di dati diversi.</span><span class="sxs-lookup"><span data-stu-id="ebed7-157">Because `dictionary` is generic, the code that uses it can create a variety of objects from it, each having the same functionality but acting on a different data type.</span></span> <span data-ttu-id="ebed7-158">L'esempio seguente mostra una riga di codice che crea una `dictionary` dell'oggetto con `String` voci e `Integer` chiavi.</span><span class="sxs-lookup"><span data-stu-id="ebed7-158">The following example shows a line of code that creates a `dictionary` object with `String` entries and `Integer` keys.</span></span>  
  
 [!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="ebed7-159">Esempio</span><span class="sxs-lookup"><span data-stu-id="ebed7-159">Example</span></span>  
 <span data-ttu-id="ebed7-160">Nell'esempio seguente illustra la definizione di struttura equivalente generata dall'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="ebed7-160">The following example shows the equivalent skeleton definition generated by the preceding example.</span></span>  
  
 [!code-vb[VbVbalrStatements#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="ebed7-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ebed7-161">See also</span></span>

- [<span data-ttu-id="ebed7-162">Of</span><span class="sxs-lookup"><span data-stu-id="ebed7-162">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)
- [<span data-ttu-id="ebed7-163">Operatore New</span><span class="sxs-lookup"><span data-stu-id="ebed7-163">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="ebed7-164">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ebed7-164">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="ebed7-165">Tipo di dati Object</span><span class="sxs-lookup"><span data-stu-id="ebed7-165">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="ebed7-166">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="ebed7-166">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="ebed7-167">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="ebed7-167">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="ebed7-168">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="ebed7-168">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="ebed7-169">Procedura: Usare una classe generica</span><span class="sxs-lookup"><span data-stu-id="ebed7-169">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="ebed7-170">Covarianza e controvarianza</span><span class="sxs-lookup"><span data-stu-id="ebed7-170">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="ebed7-171">In</span><span class="sxs-lookup"><span data-stu-id="ebed7-171">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [<span data-ttu-id="ebed7-172">Out</span><span class="sxs-lookup"><span data-stu-id="ebed7-172">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)

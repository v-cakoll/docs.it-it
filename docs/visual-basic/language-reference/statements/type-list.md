---
title: Type List
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
ms.openlocfilehash: 7e22ad6e32ec13f081391e1d47a80df8b1e65063
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84412988"
---
# <a name="type-list-visual-basic"></a><span data-ttu-id="a8ed8-102">Elenco dei tipi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8ed8-102">Type List (Visual Basic)</span></span>

<span data-ttu-id="a8ed8-103">Specifica i *parametri di tipo* per un elemento di programmazione *generico* .</span><span class="sxs-lookup"><span data-stu-id="a8ed8-103">Specifies the *type parameters* for a *generic* programming element.</span></span> <span data-ttu-id="a8ed8-104">Più parametri sono separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="a8ed8-105">Di seguito è riportata la sintassi per un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-105">Following is the syntax for one type parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="a8ed8-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a8ed8-106">Syntax</span></span>

```vb
[genericmodifier] typename [ As constraintlist ]
```

## <a name="parts"></a><span data-ttu-id="a8ed8-107">Parti</span><span class="sxs-lookup"><span data-stu-id="a8ed8-107">Parts</span></span>

|<span data-ttu-id="a8ed8-108">Termine</span><span class="sxs-lookup"><span data-stu-id="a8ed8-108">Term</span></span>|<span data-ttu-id="a8ed8-109">Definizione</span><span class="sxs-lookup"><span data-stu-id="a8ed8-109">Definition</span></span>|
|---|---|
|`genericmodifier`|<span data-ttu-id="a8ed8-110">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-110">Optional.</span></span> <span data-ttu-id="a8ed8-111">Può essere usato solo in interfacce e delegati generici.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-111">Can be used only in generic interfaces and delegates.</span></span> <span data-ttu-id="a8ed8-112">È possibile dichiarare un tipo covariante usando la parola chiave [out](../modifiers/out-generic-modifier.md) o controvariante usando la parola chiave [in](../modifiers/in-generic-modifier.md) .</span><span class="sxs-lookup"><span data-stu-id="a8ed8-112">You can declare a type covariant by using the [Out](../modifiers/out-generic-modifier.md) keyword or contravariant by using the [In](../modifiers/in-generic-modifier.md) keyword.</span></span> <span data-ttu-id="a8ed8-113">Vedere [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="a8ed8-113">See [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>|
|`typename`|<span data-ttu-id="a8ed8-114">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-114">Required.</span></span> <span data-ttu-id="a8ed8-115">Nome del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-115">Name of the type parameter.</span></span> <span data-ttu-id="a8ed8-116">Si tratta di un segnaposto, che deve essere sostituito da un tipo definito fornito dall'argomento di tipo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-116">This is a placeholder, to be replaced by a defined type supplied by the corresponding type argument.</span></span>|
|`constraintlist`|<span data-ttu-id="a8ed8-117">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-117">Optional.</span></span> <span data-ttu-id="a8ed8-118">Elenco di requisiti che vincolano il tipo di dati che può essere fornito per `typename` .</span><span class="sxs-lookup"><span data-stu-id="a8ed8-118">List of requirements that constrain the data type that can be supplied for `typename`.</span></span> <span data-ttu-id="a8ed8-119">Se sono presenti più vincoli, racchiuderli tra parentesi graffe ( `{ }` ) e separarli con virgole.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-119">If you have multiple constraints, enclose them in curly braces (`{ }`) and separate them with commas.</span></span> <span data-ttu-id="a8ed8-120">È necessario introdurre l'elenco di vincoli con la parola chiave [As](as-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="a8ed8-120">You must introduce the constraint list with the [As](as-clause.md) keyword.</span></span> <span data-ttu-id="a8ed8-121">Si usa `As` una sola volta, all'inizio dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-121">You use `As` only once, at the beginning of the list.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a8ed8-122">Commenti</span><span class="sxs-lookup"><span data-stu-id="a8ed8-122">Remarks</span></span>

<span data-ttu-id="a8ed8-123">Ogni elemento di programmazione generico deve assumere almeno un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-123">Every generic programming element must take at least one type parameter.</span></span> <span data-ttu-id="a8ed8-124">Un parametro di tipo è un segnaposto per un tipo specifico (un *elemento costruito*) che il codice client specifica quando crea un'istanza del tipo generico.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-124">A type parameter is a placeholder for a specific type (a *constructed element*) that client code specifies when it creates an instance of the generic type.</span></span> <span data-ttu-id="a8ed8-125">È possibile definire una classe, una struttura, un'interfaccia, una routine o un delegato generico.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-125">You can define a generic class, structure, interface, procedure, or delegate.</span></span>

<span data-ttu-id="a8ed8-126">Per ulteriori informazioni sul momento in cui definire un tipo generico, vedere [tipi generici in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="a8ed8-126">For more information on when to define a generic type, see [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).</span></span> <span data-ttu-id="a8ed8-127">Per ulteriori informazioni sui nomi dei parametri di tipo, vedere [nomi di elementi dichiarati](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="a8ed8-127">For more information on type parameter names, see [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

## <a name="rules"></a><span data-ttu-id="a8ed8-128">Regole</span><span class="sxs-lookup"><span data-stu-id="a8ed8-128">Rules</span></span>

- <span data-ttu-id="a8ed8-129">**Parentesi.**</span><span class="sxs-lookup"><span data-stu-id="a8ed8-129">**Parentheses.**</span></span> <span data-ttu-id="a8ed8-130">Se si fornisce un elenco [di parametri di](of-clause.md) tipo, è necessario racchiuderlo tra parentesi ed è necessario introdurre l'elenco con la parola chiave of.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-130">If you supply a type parameter list, you must enclose it in parentheses, and you must introduce the list with the [Of](of-clause.md) keyword.</span></span> <span data-ttu-id="a8ed8-131">Si usa `Of` una sola volta, all'inizio dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-131">You use `Of` only once, at the beginning of the list.</span></span>

- <span data-ttu-id="a8ed8-132">**Vincoli.**</span><span class="sxs-lookup"><span data-stu-id="a8ed8-132">**Constraints.**</span></span> <span data-ttu-id="a8ed8-133">Un elenco di *vincoli* in un parametro di tipo può includere gli elementi seguenti in qualsiasi combinazione:</span><span class="sxs-lookup"><span data-stu-id="a8ed8-133">A list of *constraints* on a type parameter can include the following items in any combination:</span></span>

  - <span data-ttu-id="a8ed8-134">Un numero qualsiasi di interfacce.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-134">Any number of interfaces.</span></span> <span data-ttu-id="a8ed8-135">Il tipo fornito deve implementare ogni interfaccia in questo elenco.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-135">The supplied type must implement every interface in this list.</span></span>

  - <span data-ttu-id="a8ed8-136">Al massimo una classe.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-136">At most one class.</span></span> <span data-ttu-id="a8ed8-137">Il tipo specificato deve ereditare da quella classe.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-137">The supplied type must inherit from that class.</span></span>

  - <span data-ttu-id="a8ed8-138">Parola chiave `New`.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-138">The `New` keyword.</span></span> <span data-ttu-id="a8ed8-139">Il tipo fornito deve esporre un costruttore senza parametri a cui il tipo generico può accedere.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-139">The supplied type must expose a parameterless constructor that your generic type can access.</span></span> <span data-ttu-id="a8ed8-140">Questa operazione è utile se si vincola un parametro di tipo in base a una o più interfacce.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-140">This is useful if you constrain a type parameter by one or more interfaces.</span></span> <span data-ttu-id="a8ed8-141">Un tipo che implementa le interfacce non espone necessariamente un costruttore e, a seconda del livello di accesso di un costruttore, il codice all'interno del tipo generico potrebbe non essere in grado di accedervi.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-141">A type that implements interfaces does not necessarily expose a constructor, and depending on the access level of a constructor, the code within the generic type might not be able to access it.</span></span>

  - <span data-ttu-id="a8ed8-142">`Class`Parola chiave o `Structure` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-142">Either the `Class` keyword or the `Structure` keyword.</span></span> <span data-ttu-id="a8ed8-143">La `Class` parola chiave vincola un parametro di tipo generico per richiedere che qualsiasi argomento di tipo passato sia un tipo riferimento, ad esempio una stringa, una matrice o un delegato, oppure un oggetto creato da una classe.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-143">The `Class` keyword constrains a generic type parameter to require that any type argument passed to it be a reference type, for example a string, array, or delegate, or an object created from a class.</span></span> <span data-ttu-id="a8ed8-144">La `Structure` parola chiave vincola un parametro di tipo generico per richiedere che qualsiasi argomento di tipo passato sia un tipo valore, ad esempio una struttura, un'enumerazione o un tipo di dati elementare.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-144">The `Structure` keyword constrains a generic type parameter to require that any type argument passed to it be a value type, for example a structure, enumeration, or elementary data type.</span></span> <span data-ttu-id="a8ed8-145">Non è possibile includere sia `Class` che `Structure` nello stesso `constraintlist` .</span><span class="sxs-lookup"><span data-stu-id="a8ed8-145">You cannot include both `Class` and `Structure` in the same `constraintlist`.</span></span>

  <span data-ttu-id="a8ed8-146">Il tipo fornito deve soddisfare ogni requisito incluso in `constraintlist` .</span><span class="sxs-lookup"><span data-stu-id="a8ed8-146">The supplied type must satisfy every requirement you include in `constraintlist`.</span></span>

  <span data-ttu-id="a8ed8-147">I vincoli su ogni parametro di tipo sono indipendenti dai vincoli di altri parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-147">Constraints on each type parameter are independent of constraints on other type parameters.</span></span>

## <a name="behavior"></a><span data-ttu-id="a8ed8-148">Comportamento</span><span class="sxs-lookup"><span data-stu-id="a8ed8-148">Behavior</span></span>

- <span data-ttu-id="a8ed8-149">**Sostituzione in fase di compilazione.**</span><span class="sxs-lookup"><span data-stu-id="a8ed8-149">**Compile-Time Substitution.**</span></span> <span data-ttu-id="a8ed8-150">Quando si crea un tipo costruito da un elemento di programmazione generico, si fornisce un tipo definito per ogni parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-150">When you create a constructed type from a generic programming element, you supply a defined type for each type parameter.</span></span> <span data-ttu-id="a8ed8-151">Il compilatore Visual Basic sostituisce il tipo fornito per ogni occorrenza di `typename` all'interno dell'elemento generico.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-151">The Visual Basic compiler substitutes that supplied type for every occurrence of `typename` within the generic element.</span></span>

- <span data-ttu-id="a8ed8-152">**Assenza di vincoli.**</span><span class="sxs-lookup"><span data-stu-id="a8ed8-152">**Absence of Constraints.**</span></span> <span data-ttu-id="a8ed8-153">Se non si specifica alcun vincolo per un parametro di tipo, il codice è limitato alle operazioni e ai membri supportati dal [tipo di dati Object](../data-types/object-data-type.md) per quel parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-153">If you do not specify any constraints on a type parameter, your code is limited to the operations and members supported by the [Object Data Type](../data-types/object-data-type.md) for that type parameter.</span></span>

## <a name="example"></a><span data-ttu-id="a8ed8-154">Esempio</span><span class="sxs-lookup"><span data-stu-id="a8ed8-154">Example</span></span>

<span data-ttu-id="a8ed8-155">Nell'esempio seguente viene illustrata una definizione di scheletro di una classe di dizionario generica, inclusa una funzione Skeleton per aggiungere una nuova voce al dizionario.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-155">The following example shows a skeleton definition of a generic dictionary class, including a skeleton function to add a new entry to the dictionary.</span></span>

[!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]

## <a name="example"></a><span data-ttu-id="a8ed8-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="a8ed8-156">Example</span></span>

<span data-ttu-id="a8ed8-157">Poiché `dictionary` è generico, il codice che lo usa può creare un'ampia gamma di oggetti, ognuno dei quali ha la stessa funzionalità ma agisce su un tipo di dati diverso.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-157">Because `dictionary` is generic, the code that uses it can create a variety of objects from it, each having the same functionality but acting on a different data type.</span></span> <span data-ttu-id="a8ed8-158">Nell'esempio seguente viene illustrata una riga di codice che crea un `dictionary` oggetto con le `String` voci e le `Integer` chiavi.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-158">The following example shows a line of code that creates a `dictionary` object with `String` entries and `Integer` keys.</span></span>

[!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]

## <a name="example"></a><span data-ttu-id="a8ed8-159">Esempio</span><span class="sxs-lookup"><span data-stu-id="a8ed8-159">Example</span></span>

<span data-ttu-id="a8ed8-160">Nell'esempio seguente viene illustrata la definizione di scheletro equivalente generata dall'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="a8ed8-160">The following example shows the equivalent skeleton definition generated by the preceding example.</span></span>

[!code-vb[VbVbalrStatements#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="a8ed8-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8ed8-161">See also</span></span>

- [<span data-ttu-id="a8ed8-162">Di</span><span class="sxs-lookup"><span data-stu-id="a8ed8-162">Of</span></span>](of-clause.md)
- [<span data-ttu-id="a8ed8-163">Operatore New</span><span class="sxs-lookup"><span data-stu-id="a8ed8-163">New Operator</span></span>](../operators/new-operator.md)
- [<span data-ttu-id="a8ed8-164">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8ed8-164">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="a8ed8-165">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="a8ed8-165">Object Data Type</span></span>](../data-types/object-data-type.md)
- [<span data-ttu-id="a8ed8-166">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="a8ed8-166">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="a8ed8-167">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="a8ed8-167">Structure Statement</span></span>](structure-statement.md)
- [<span data-ttu-id="a8ed8-168">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="a8ed8-168">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="a8ed8-169">Procedura: Usare una classe generica</span><span class="sxs-lookup"><span data-stu-id="a8ed8-169">How to: Use a Generic Class</span></span>](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="a8ed8-170">Covarianza e controvarianza</span><span class="sxs-lookup"><span data-stu-id="a8ed8-170">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="a8ed8-171">In</span><span class="sxs-lookup"><span data-stu-id="a8ed8-171">In</span></span>](../modifiers/in-generic-modifier.md)
- [<span data-ttu-id="a8ed8-172">Out</span><span class="sxs-lookup"><span data-stu-id="a8ed8-172">Out</span></span>](../modifiers/out-generic-modifier.md)

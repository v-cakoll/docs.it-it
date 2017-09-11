---
title: Strutture e classi (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- classes [Visual Basic], vs. structures
- structures
- classes [Visual Basic]
- structures, compared to classes
- structures, structure variables
- structure variables
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c6874192a09db9ff5f247274247630d0bfa05ea3
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="structures-and-classes-visual-basic"></a><span data-ttu-id="c57d2-102">Strutture e classi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c57d2-102">Structures and Classes (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="c57d2-103">Unisce la sintassi per le strutture e classi, con il risultato che entrambe le entità supportano la maggior parte delle stesse funzionalità.</span><span class="sxs-lookup"><span data-stu-id="c57d2-103"> unifies the syntax for structures and classes, with the result that both entities support most of the same features.</span></span> <span data-ttu-id="c57d2-104">Tuttavia, esistono anche differenze importanti tra strutture e classi.</span><span class="sxs-lookup"><span data-stu-id="c57d2-104">However, there are also important differences between structures and classes.</span></span>  
  
 <span data-ttu-id="c57d2-105">Presentano il vantaggio di essere tipi di riferimento, passando un riferimento è più efficiente passare una variabile di struttura con tutti i relativi dati.</span><span class="sxs-lookup"><span data-stu-id="c57d2-105">Classes have the advantage of being reference types — passing a reference is more efficient than passing a structure variable with all its data.</span></span> <span data-ttu-id="c57d2-106">D'altra parte, le strutture non richiedono l'allocazione di memoria nell'heap globale.</span><span class="sxs-lookup"><span data-stu-id="c57d2-106">On the other hand, structures do not require allocation of memory on the global heap.</span></span>  
  
 <span data-ttu-id="c57d2-107">Poiché non è possibile ereditare da una struttura, utilizzare strutture solo per gli oggetti che non è necessario essere esteso.</span><span class="sxs-lookup"><span data-stu-id="c57d2-107">Because you cannot inherit from a structure, structures should be used only for objects that do not need to be extended.</span></span> <span data-ttu-id="c57d2-108">Utilizzare le strutture quando l'oggetto che si desidera creare ha una dimensione di un'istanza ridotta e prendere in considerazione le caratteristiche delle classi e strutture di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="c57d2-108">Use structures when the object you wish to create has a small instance size, and take into account the performance characteristics of classes versus structures.</span></span>  
  
## <a name="similarities"></a><span data-ttu-id="c57d2-109">Analogie</span><span class="sxs-lookup"><span data-stu-id="c57d2-109">Similarities</span></span>  
 <span data-ttu-id="c57d2-110">Classi e strutture sono simili per i seguenti aspetti:</span><span class="sxs-lookup"><span data-stu-id="c57d2-110">Structures and classes are similar in the following respects:</span></span>  
  
-   <span data-ttu-id="c57d2-111">Entrambi sono *contenitore* tipi, vale a dire che contengono altri tipi come membri.</span><span class="sxs-lookup"><span data-stu-id="c57d2-111">Both are *container* types, meaning that they contain other types as members.</span></span>  
  
-   <span data-ttu-id="c57d2-112">Entrambi sono membri, che possono includere costruttori, metodi, proprietà, campi, costanti, enumerazioni, eventi e gestori di eventi.</span><span class="sxs-lookup"><span data-stu-id="c57d2-112">Both have members, which can include constructors, methods, properties, fields, constants, enumerations, events, and event handlers.</span></span> <span data-ttu-id="c57d2-113">Tuttavia, non confondere questi membri con il dichiarato *elementi* di una struttura.</span><span class="sxs-lookup"><span data-stu-id="c57d2-113">However, do not confuse these members with the declared *elements* of a structure.</span></span>  
  
-   <span data-ttu-id="c57d2-114">I membri di entrambe possono avere livelli di accesso personalizzati.</span><span class="sxs-lookup"><span data-stu-id="c57d2-114">Members of both can have individualized access levels.</span></span> <span data-ttu-id="c57d2-115">Ad esempio, è possibile dichiarare un membro `Public` e un altro `Private`.</span><span class="sxs-lookup"><span data-stu-id="c57d2-115">For example, one member can be declared `Public` and another `Private`.</span></span>  
  
-   <span data-ttu-id="c57d2-116">Entrambi possono implementare interfacce.</span><span class="sxs-lookup"><span data-stu-id="c57d2-116">Both can implement interfaces.</span></span>  
  
-   <span data-ttu-id="c57d2-117">Entrambe possono avere condivisi costruttori, con o senza parametri.</span><span class="sxs-lookup"><span data-stu-id="c57d2-117">Both can have shared constructors, with or without parameters.</span></span>  
  
-   <span data-ttu-id="c57d2-118">Entrambe possono esporre un *predefiniti delle proprietà*, a condizione che accetti almeno un parametro.</span><span class="sxs-lookup"><span data-stu-id="c57d2-118">Both can expose a *default property*, provided that property takes at least one parameter.</span></span>  
  
-   <span data-ttu-id="c57d2-119">Entrambe possono dichiarare e generare eventi e sia possibile dichiarare i delegati.</span><span class="sxs-lookup"><span data-stu-id="c57d2-119">Both can declare and raise events, and both can declare delegates.</span></span>  
  
## <a name="differences"></a><span data-ttu-id="c57d2-120">Differenze</span><span class="sxs-lookup"><span data-stu-id="c57d2-120">Differences</span></span>  
 <span data-ttu-id="c57d2-121">Classi e strutture sono diversi per le seguenti indicazioni:</span><span class="sxs-lookup"><span data-stu-id="c57d2-121">Structures and classes differ in the following particulars:</span></span>  
  
-   <span data-ttu-id="c57d2-122">Le strutture sono *i tipi di valore*; le classi sono *tipi di riferimento*.</span><span class="sxs-lookup"><span data-stu-id="c57d2-122">Structures are *value types*; classes are *reference types*.</span></span> <span data-ttu-id="c57d2-123">Una variabile di un tipo di struttura contiene i dati della struttura, anziché contenente un riferimento a dati come un tipo di classe.</span><span class="sxs-lookup"><span data-stu-id="c57d2-123">A variable of a structure type contains the structure's data, rather than containing a reference to the data as a class type does.</span></span>  
  
-   <span data-ttu-id="c57d2-124">Strutture di utilizzano l'allocazione dello stack; le classi utilizzano l'allocazione di heap.</span><span class="sxs-lookup"><span data-stu-id="c57d2-124">Structures use stack allocation; classes use heap allocation.</span></span>  
  
-   <span data-ttu-id="c57d2-125">Tutti gli elementi di struttura sono `Public` per impostazione predefinita; classe variabili e costanti sono `Private` per impostazione predefinita, mentre altri membri della classe sono `Public` per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c57d2-125">All structure elements are `Public` by default; class variables and constants are `Private` by default, while other class members are `Public` by default.</span></span> <span data-ttu-id="c57d2-126">Questo comportamento per i membri di classe fornisce la compatibilità con il sistema di Visual Basic 6.0 di valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="c57d2-126">This behavior for class members provides compatibility with the Visual Basic 6.0 system of defaults.</span></span>  
  
-   <span data-ttu-id="c57d2-127">Una struttura deve contenere almeno uno non personalizzato non condiviso di variabile o condiviso, elemento di un evento; una classe può essere completamente vuota.</span><span class="sxs-lookup"><span data-stu-id="c57d2-127">A structure must have at least one nonshared variable or nonshared, noncustom event element; a class can be completely empty.</span></span>  
  
-   <span data-ttu-id="c57d2-128">Elementi di struttura non possono essere dichiarati come `Protected`; i membri di classe possono.</span><span class="sxs-lookup"><span data-stu-id="c57d2-128">Structure elements cannot be declared as `Protected`; class members can.</span></span>  
  
-   <span data-ttu-id="c57d2-129">Una routine di struttura può gestire eventi solo se è un [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` procedura e solo per mezzo di [AddHandler (istruzione)](../../../../visual-basic/language-reference/statements/addhandler-statement.md); qualsiasi routine di classe può gestire gli eventi utilizzando il [gestisce](../../../../visual-basic/language-reference/statements/handles-clause.md) (parola chiave) o `AddHandler` istruzione.</span><span class="sxs-lookup"><span data-stu-id="c57d2-129">A structure procedure can handle events only if it is a [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` procedure, and only by means of the [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md); any class procedure can handle events, using either the [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) keyword or the `AddHandler` statement.</span></span> <span data-ttu-id="c57d2-130">Per ulteriori informazioni, vedere [eventi](../../../../visual-basic/programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="c57d2-130">For more information, see [Events](../../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
-   <span data-ttu-id="c57d2-131">Dichiarazioni di variabili di struttura non possono specificare inizializzatori o dimensioni iniziali per le matrici. dichiarazioni di variabili di classe possono.</span><span class="sxs-lookup"><span data-stu-id="c57d2-131">Structure variable declarations cannot specify initializers or initial sizes for arrays; class variable declarations can.</span></span>  
  
-   <span data-ttu-id="c57d2-132">Le strutture ereditano in modo implicito dalla <xref:System.ValueType?displayProperty=fullName>classe e non può ereditare da qualsiasi altro tipo; le classi possono ereditare da qualsiasi classe o una classe diversa da <xref:System.ValueType?displayProperty=fullName>.</xref:System.ValueType?displayProperty=fullName> </xref:System.ValueType?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c57d2-132">Structures implicitly inherit from the <xref:System.ValueType?displayProperty=fullName> class and cannot inherit from any other type; classes can inherit from any class or classes other than <xref:System.ValueType?displayProperty=fullName>.</span></span>  
  
-   <span data-ttu-id="c57d2-133">Strutture non sono ereditabili; le classi sono.</span><span class="sxs-lookup"><span data-stu-id="c57d2-133">Structures are not inheritable; classes are.</span></span>  
  
-   <span data-ttu-id="c57d2-134">Le strutture non vengono mai terminate, common language runtime (CLR) non chiama mai il <xref:System.Object.Finalize%2A>metodo in una struttura; le classi vengono terminate dal garbage collector (GC), che chiama <xref:System.Object.Finalize%2A>su una classe quando rilevato che non sono presenti riferimenti attivi.</xref:System.Object.Finalize%2A> </xref:System.Object.Finalize%2A></span><span class="sxs-lookup"><span data-stu-id="c57d2-134">Structures are never terminated, so the common language runtime (CLR) never calls the <xref:System.Object.Finalize%2A> method on any structure; classes are terminated by the garbage collector (GC), which calls <xref:System.Object.Finalize%2A> on a class when it detects there are no active references remaining.</span></span>  
  
-   <span data-ttu-id="c57d2-135">Una struttura non richiede un costruttore. esegue una classe.</span><span class="sxs-lookup"><span data-stu-id="c57d2-135">A structure does not require a constructor; a class does.</span></span>  
  
-   <span data-ttu-id="c57d2-136">Strutture possono disporre di costruttori non condivisi solo se hanno parametri. le classi possono avere li con o senza parametri.</span><span class="sxs-lookup"><span data-stu-id="c57d2-136">Structures can have nonshared constructors only if they take parameters; classes can have them with or without parameters.</span></span>  
  
 <span data-ttu-id="c57d2-137">Ogni struttura dispone di un costruttore pubblico senza parametri.</span><span class="sxs-lookup"><span data-stu-id="c57d2-137">Every structure has an implicit public constructor without parameters.</span></span> <span data-ttu-id="c57d2-138">Questo costruttore inizializza gli elementi di dati della struttura sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="c57d2-138">This constructor initializes all the structure's data elements to their default values.</span></span> <span data-ttu-id="c57d2-139">È possibile ridefinire il problema.</span><span class="sxs-lookup"><span data-stu-id="c57d2-139">You cannot redefine this behavior.</span></span>  
  
## <a name="instances-and-variables"></a><span data-ttu-id="c57d2-140">Istanze e variabili</span><span class="sxs-lookup"><span data-stu-id="c57d2-140">Instances and Variables</span></span>  
 <span data-ttu-id="c57d2-141">Poiché le strutture sono tipi di valore, ogni variabile di struttura in modo permanente è associato a un'istanza di struttura individuale.</span><span class="sxs-lookup"><span data-stu-id="c57d2-141">Because structures are value types, each structure variable is permanently bound to an individual structure instance.</span></span> <span data-ttu-id="c57d2-142">Tuttavia, le classi sono tipi di riferimento e una variabile oggetto può fare riferimento a diverse istanze di classi in momenti diversi.</span><span class="sxs-lookup"><span data-stu-id="c57d2-142">But classes are reference types, and an object variable can refer to various class instances at different times.</span></span> <span data-ttu-id="c57d2-143">Questa differenza influisce sull'utilizzo di strutture e classi nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c57d2-143">This distinction affects your usage of structures and classes in the following ways:</span></span>  
  
-   <span data-ttu-id="c57d2-144">**Inizializzazione.**</span><span class="sxs-lookup"><span data-stu-id="c57d2-144">**Initialization.**</span></span> <span data-ttu-id="c57d2-145">Una variabile di struttura include implicitamente un'inizializzazione degli elementi utilizzando il costruttore della struttura senza parametri.</span><span class="sxs-lookup"><span data-stu-id="c57d2-145">A structure variable implicitly includes an initialization of the elements using the structure's parameterless constructor.</span></span> <span data-ttu-id="c57d2-146">Di conseguenza, `Dim s As struct1` equivale a `Dim s As struct1 = New struct1()`.</span><span class="sxs-lookup"><span data-stu-id="c57d2-146">Therefore, `Dim s As struct1` is equivalent to `Dim s As struct1 = New struct1()`.</span></span>  
  
-   <span data-ttu-id="c57d2-147">**Assegnazione di variabili.**</span><span class="sxs-lookup"><span data-stu-id="c57d2-147">**Assigning Variables.**</span></span> <span data-ttu-id="c57d2-148">Quando si assegna una variabile di struttura a un altro, o passa un'istanza della struttura a un argomento di routine, i valori correnti di tutti gli elementi variabile vengono copiati nella nuova struttura.</span><span class="sxs-lookup"><span data-stu-id="c57d2-148">When you assign one structure variable to another, or pass a structure instance to a procedure argument, the current values of all the variable elements are copied to the new structure.</span></span> <span data-ttu-id="c57d2-149">Quando si assegna una variabile oggetto a un altro o si passa una variabile oggetto a una routine, viene copiato solo il puntatore di riferimento.</span><span class="sxs-lookup"><span data-stu-id="c57d2-149">When you assign one object variable to another, or pass an object variable to a procedure, only the reference pointer is copied.</span></span>  
  
-   <span data-ttu-id="c57d2-150">**Assegnare il valore Nothing.**</span><span class="sxs-lookup"><span data-stu-id="c57d2-150">**Assigning Nothing.**</span></span> <span data-ttu-id="c57d2-151">È possibile assegnare il valore [nulla](../../../../visual-basic/language-reference/nothing.md) a una struttura variabile, ma l'istanza continua a essere associato alla variabile.</span><span class="sxs-lookup"><span data-stu-id="c57d2-151">You can assign the value [Nothing](../../../../visual-basic/language-reference/nothing.md) to a structure variable, but the instance continues to be associated with the variable.</span></span> <span data-ttu-id="c57d2-152">È comunque possibile chiamarne i metodi e accedere ai relativi elementi di dati, anche se gli elementi variabile vengano reinizializzati dall'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="c57d2-152">You can still call its methods and access its data elements, although variable elements are reinitialized by the assignment.</span></span>  
  
     <span data-ttu-id="c57d2-153">Al contrario, se si imposta una variabile oggetto su `Nothing`, si dissocia tale variabile da qualsiasi istanza della classe e non può accedere ad alcun membro tramite la variabile finché non verrà assegnato un'altra istanza.</span><span class="sxs-lookup"><span data-stu-id="c57d2-153">In contrast, if you set an object variable to `Nothing`, you dissociate it from any class instance, and you cannot access any members through the variable until you assign another instance to it.</span></span>  
  
-   <span data-ttu-id="c57d2-154">**Più istanze.**</span><span class="sxs-lookup"><span data-stu-id="c57d2-154">**Multiple Instances.**</span></span> <span data-ttu-id="c57d2-155">Una variabile oggetto può disporre di istanze di classe diversi in momenti diversi, e diverse variabili di oggetto possono fare riferimento alla stessa istanza di classe nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="c57d2-155">An object variable can have different class instances assigned to it at different times, and several object variables can refer to the same class instance at the same time.</span></span> <span data-ttu-id="c57d2-156">Le modifiche apportate ai valori dei membri della classe influiscono su tali membri quando si accede tramite un'altra variabile che punta alla stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="c57d2-156">Changes you make to the values of class members affect those members when accessed through another variable pointing to the same instance.</span></span>  
  
     <span data-ttu-id="c57d2-157">Elementi della struttura, tuttavia, sono isolati all'interno della relativa istanza.</span><span class="sxs-lookup"><span data-stu-id="c57d2-157">Structure elements, however, are isolated within their own instance.</span></span> <span data-ttu-id="c57d2-158">In base ai valori non vengono riflesse in altre variabili di struttura, anche in altre istanze dello stesso `Structure` dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="c57d2-158">Changes to their values are not reflected in any other structure variables, even in other instances of the same `Structure` declaration.</span></span>  
  
-   <span data-ttu-id="c57d2-159">**Uguaglianza.**</span><span class="sxs-lookup"><span data-stu-id="c57d2-159">**Equality.**</span></span> <span data-ttu-id="c57d2-160">Test di uguaglianza di due strutture deve essere eseguito con un elemento per elemento test.</span><span class="sxs-lookup"><span data-stu-id="c57d2-160">Equality testing of two structures must be performed with an element-by-element test.</span></span> <span data-ttu-id="c57d2-161">Due variabili di oggetto possono essere confrontate utilizzando il <xref:System.Object.Equals%2A>(metodo).</xref:System.Object.Equals%2A></span><span class="sxs-lookup"><span data-stu-id="c57d2-161">Two object variables can be compared using the <xref:System.Object.Equals%2A> method.</span></span> <span data-ttu-id="c57d2-162"><xref:System.Object.Equals%2A>indica se le due variabili puntano alla stessa istanza.</xref:System.Object.Equals%2A></span><span class="sxs-lookup"><span data-stu-id="c57d2-162"><xref:System.Object.Equals%2A> indicates whether the two variables point to the same instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c57d2-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c57d2-163">See Also</span></span>  
 <span data-ttu-id="c57d2-164">[Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="c57d2-164">[Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="c57d2-165"> [Tipi di dati compositi](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="c57d2-165"> [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span></span>  
<span data-ttu-id="c57d2-166"> [Tipi di valore e tipi di riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="c57d2-166"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="c57d2-167"> [Strutture](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span><span class="sxs-lookup"><span data-stu-id="c57d2-167"> [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span></span>  
<span data-ttu-id="c57d2-168"> [Risoluzione dei tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="c57d2-168"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="c57d2-169"> [Strutture e altri elementi di programmazione](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md) </span><span class="sxs-lookup"><span data-stu-id="c57d2-169"> [Structures and Other Programming Elements](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md) </span></span>  
<span data-ttu-id="c57d2-170"> [Oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)</span><span class="sxs-lookup"><span data-stu-id="c57d2-170"> [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)</span></span>

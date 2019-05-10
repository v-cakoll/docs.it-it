---
title: Nozioni fondamentali sull'ereditarietà (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- derived classes [Visual Basic], inheritance
- MyClass keyword [Visual Basic], using
- MyBase keyword [Visual Basic], using
- Inherits statement [Visual Basic], inheritance
- overriding, Overridable keyword
- MustInherit keyword [Visual Basic], using
- Overrides keyword [Visual Basic], using
- inheritance
- MustInherit classes [Visual Basic]
- MustOverride keyword [Visual Basic], using
- classes [Visual Basic], derived
- NotInheritable keyword [Visual Basic], using
- base classes [Visual Basic], extending properties and methods [Visual Basic]
- NotOverridable keyword [Visual Basic], using
- base classes [Visual Basic], inheritance
- abstract classes [Visual Basic], inheritance
- overriding, Overrides keyword
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
ms.openlocfilehash: a31f69459465368dc7519b5126c6c4eb72e25d29
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663001"
---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="1c3e2-102">Nozioni fondamentali sull'ereditarietà (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c3e2-102">Inheritance Basics (Visual Basic)</span></span>
<span data-ttu-id="1c3e2-103">Il `Inherits` istruzione viene usata per dichiarare una nuova classe, denominata un *classe derivata*, in base a una classe esistente, nota come un *classe di base*.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="1c3e2-104">Le classi derivate ereditano e possono estendere, proprietà, metodi, eventi, campi e le costanti definite nella classe di base.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="1c3e2-105">La sezione seguente descrive alcune delle regole per l'ereditarietà e i modificatori che è possibile usare per modificare le classi modo ereditano o vengono ereditati:</span><span class="sxs-lookup"><span data-stu-id="1c3e2-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>  
  
- <span data-ttu-id="1c3e2-106">Per impostazione predefinita, tutte le classi sono ereditabili a meno che non contrassegnato con il `NotInheritable` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="1c3e2-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="1c3e2-107">Le classi possono ereditare da altre classi nel progetto o dalle classi in altri assembly che fa riferimento il progetto.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>  
  
- <span data-ttu-id="1c3e2-108">Diversamente dai linguaggi che consentono l'ereditarietà multipla, Visual Basic consente solo l'ereditarietà singola nelle classi. ovvero le classi derivate possono avere una sola classe base.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-108">Unlike languages that allow multiple inheritance, Visual Basic allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="1c3e2-109">Anche se non è consentito nelle classi di ereditarietà multipla, le classi possono implementare più interfacce di cui è possono eseguire in modo efficace la stessa funzione.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>  
  
- <span data-ttu-id="1c3e2-110">Per evitare l'esposizione agli elementi in una classe base, il tipo di accesso di una classe derivata deve essere uguale o più restrittivo alla classe di base.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="1c3e2-111">Ad esempio, un `Public` classe non può ereditare un `Friend` o una `Private` (classe) e un `Friend` classe non può ereditare un `Private` classe.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>  
  
## <a name="inheritance-modifiers"></a><span data-ttu-id="1c3e2-112">Modificatori di ereditarietà</span><span class="sxs-lookup"><span data-stu-id="1c3e2-112">Inheritance Modifiers</span></span>  
 <span data-ttu-id="1c3e2-113">Visual Basic introduce le istruzioni a livello di classe e i modificatori per il supporto dell'ereditarietà:</span><span class="sxs-lookup"><span data-stu-id="1c3e2-113">Visual Basic introduces the following class-level statements and modifiers to support inheritance:</span></span>  
  
- <span data-ttu-id="1c3e2-114">`Inherits` istruzione: specifica la classe di base.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-114">`Inherits` statement — Specifies the base class.</span></span>  
  
- <span data-ttu-id="1c3e2-115">`NotInheritable` modificatore, ovvero per impedire ai programmatori di utilizzo della classe come classe di base.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>  
  
- <span data-ttu-id="1c3e2-116">`MustInherit` modificatore: Specifica che la classe deve essere utilizzato come classe di base.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="1c3e2-117">Le istanze di `MustInherit` classi non possono essere create direttamente; possono solo essere create istanze della classe di base di una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="1c3e2-118">(Altri linguaggi di programmazione, ad esempio C++ e C#, viene usato il termine *classe astratta* per descrivere una classe di questo tipo.)</span><span class="sxs-lookup"><span data-stu-id="1c3e2-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="1c3e2-119">Override di proprietà e metodi nelle classi derivate</span><span class="sxs-lookup"><span data-stu-id="1c3e2-119">Overriding Properties and Methods in Derived Classes</span></span>  
 <span data-ttu-id="1c3e2-120">Per impostazione predefinita, una classe derivata eredita le proprietà e metodi della classe base.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="1c3e2-121">Se un metodo o proprietà ereditata deve comportarsi in modo diverso nella classe derivata può risultare *sottoposto a override*.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="1c3e2-122">Vale a dire, è possibile definire una nuova implementazione del metodo nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="1c3e2-123">I seguenti modificatori consentono di controllare le modalità di override di proprietà e metodi:</span><span class="sxs-lookup"><span data-stu-id="1c3e2-123">The following modifiers are used to control how properties and methods are overridden:</span></span>  
  
- <span data-ttu-id="1c3e2-124">`Overridable` : Consente a una proprietà o metodo in una classe per eseguire l'override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>  
  
- <span data-ttu-id="1c3e2-125">`Overrides` : Esegue l'override di un `Overridable` proprietà o un metodo definito nella classe di base.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>  
  
- <span data-ttu-id="1c3e2-126">`NotOverridable` -Impedisce una proprietà o metodo da sottoporre a override in una classe che eredita.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="1c3e2-127">Per impostazione predefinita `Public` sono metodi `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-127">By default, `Public` methods are `NotOverridable`.</span></span>  
  
- <span data-ttu-id="1c3e2-128">`MustOverride` : Richiede che una classe derivata eseguono l'override di proprietà o metodo.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="1c3e2-129">Quando la `MustOverride` parola chiave viene usata, la definizione del metodo è costituito solo il `Sub`, `Function`, o `Property` istruzione.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="1c3e2-130">Le altre istruzioni non sono consentiti e in particolare è presente alcun `End Sub` o `End Function` istruzione.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="1c3e2-131">`MustOverride` i metodi devono essere dichiarati `MustInherit` classi.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>  
  
 <span data-ttu-id="1c3e2-132">Si supponga di che voler definire classi per la gestione delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="1c3e2-133">È possibile definire un oggetto generico `Payroll` classe che contiene un `RunPayroll` metodo che calcola retribuzioni per una settimana tipica.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="1c3e2-134">È quindi possibile usare `Payroll` come classe di base per una più specializzati `BonusPayroll` (classe), che potrebbe essere usati quando si distribuiscono bonus ai dipendenti.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>  
  
 <span data-ttu-id="1c3e2-135">Il `BonusPayroll` classe può ereditare ed eseguire l'override, il `PayEmployee` metodo definito nella base `Payroll` classe.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>  
  
 <span data-ttu-id="1c3e2-136">L'esempio seguente definisce una classe di base `Payroll,` e una classe derivata `BonusPayroll`, che esegue l'override di un metodo ereditato, `PayEmployee`.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="1c3e2-137">Una routine, `RunPayroll`, viene creato e quindi passa un `Payroll` oggetto e un `BonusPayroll` oggetto a una funzione `Pay`, che esegue il `PayEmployee` metodo di entrambi gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>  
  
 [!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]  
  
## <a name="the-mybase-keyword"></a><span data-ttu-id="1c3e2-138">La parola chiave MyBase</span><span class="sxs-lookup"><span data-stu-id="1c3e2-138">The MyBase Keyword</span></span>  
 <span data-ttu-id="1c3e2-139">Il `MyBase` (parola chiave) si comporta come una variabile oggetto che fa riferimento alla classe di base dell'istanza corrente di una classe.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-139">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="1c3e2-140">`MyBase` viene spesso utilizzato per accedere ai membri di classe base sottoposto a override o shadowing in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-140">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="1c3e2-141">In particolare, `MyBase.New` viene usato per chiamare in modo esplicito un costruttore di classe di base da un costruttore di classe derivata.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-141">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
 <span data-ttu-id="1c3e2-142">Si supponga, ad esempio, che si progetta una classe derivata che esegue l'override di un metodo ereditato dalla classe di base.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-142">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="1c3e2-143">Il metodo sottoposto a override è possibile chiamare il metodo nella classe di base e modificare il valore restituito, come illustrato nel frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="1c3e2-143">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]  
  
 <span data-ttu-id="1c3e2-144">L'elenco seguente descrive le restrizioni sull'uso di `MyBase`:</span><span class="sxs-lookup"><span data-stu-id="1c3e2-144">The following list describes restrictions on using `MyBase`:</span></span>  
  
- <span data-ttu-id="1c3e2-145">`MyBase` fa riferimento alla classe di base immediata e i relativi membri ereditati.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-145">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="1c3e2-146">Non può essere usato per accedere a `Private` membri della classe.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-146">It cannot be used to access `Private` members in the class.</span></span>  
  
- <span data-ttu-id="1c3e2-147">`MyBase` è una parola chiave, non un oggetto reale.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-147">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="1c3e2-148">`MyBase` non può essere assegnato a una variabile, passati alle procedure o usato in un `Is` confronto.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-148">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
- <span data-ttu-id="1c3e2-149">Il metodo che `MyBase` qualifica non deve essere definito nella classe di base immediata; può invece essere definito in una classe di base ereditata indirettamente.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-149">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="1c3e2-150">Affinché un riferimento qualificato da `MyBase` venga compilato correttamente, una classe di base deve contenere un metodo corrispondente al nome e i tipi di parametri che vengono visualizzati nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-150">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>  
  
- <span data-ttu-id="1c3e2-151">Non è possibile usare `MyBase` chiamare `MustOverride` metodi della classe di base.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-151">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>  
  
- <span data-ttu-id="1c3e2-152">`MyBase` non può essere utilizzato per qualificare stesso.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-152">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="1c3e2-153">Pertanto, il codice seguente non è valido:</span><span class="sxs-lookup"><span data-stu-id="1c3e2-153">Therefore, the following code is not valid:</span></span>  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
- <span data-ttu-id="1c3e2-154">`MyBase` non è utilizzabile nei moduli.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-154">`MyBase` cannot be used in modules.</span></span>  
  
- <span data-ttu-id="1c3e2-155">`MyBase` non può essere usato per accedere ai membri di classe di base che sono contrassegnati come `Friend` se la classe di base si trova in un assembly diverso.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-155">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>  
  
 <span data-ttu-id="1c3e2-156">Per altre informazioni e un altro esempio, vedere [come: Accedere a una variabile nascosta da una classe derivata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="1c3e2-156">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
## <a name="the-myclass-keyword"></a><span data-ttu-id="1c3e2-157">La parola chiave MyClass</span><span class="sxs-lookup"><span data-stu-id="1c3e2-157">The MyClass Keyword</span></span>  
 <span data-ttu-id="1c3e2-158">Il `MyClass` (parola chiave) si comporta come una variabile oggetto che fa riferimento all'istanza corrente di una classe come implementata originariamente.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-158">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="1c3e2-159">`MyClass` è simile a `Me`, ma tutti i metodi e proprietà in una chiamata `MyClass` viene trattato come se il metodo o proprietà fosse [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span><span class="sxs-lookup"><span data-stu-id="1c3e2-159">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="1c3e2-160">Pertanto, il metodo o proprietà non è influenzata viene sottoposto a override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-160">Therefore, the method or property is not affected by overriding in a derived class.</span></span>  
  
- <span data-ttu-id="1c3e2-161">`MyClass` è una parola chiave, non un oggetto reale.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-161">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="1c3e2-162">`MyClass` non può essere assegnato a una variabile, passati alle procedure o usato in un `Is` confronto.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-162">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
- <span data-ttu-id="1c3e2-163">`MyClass` fa riferimento alla classe che lo contiene e i relativi membri ereditati.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-163">`MyClass` refers to the containing class and its inherited members.</span></span>  
  
- <span data-ttu-id="1c3e2-164">`MyClass` può essere usato come qualificatore per `Shared` membri.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-164">`MyClass` can be used as a qualifier for `Shared` members.</span></span>  
  
- <span data-ttu-id="1c3e2-165">`MyClass` non può essere utilizzato all'interno di un `Shared` (metodo), ma può essere usato all'interno di un metodo di istanza per accedere a un membro condiviso di una classe.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-165">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>  
  
- <span data-ttu-id="1c3e2-166">`MyClass` non può essere utilizzata nei moduli standard.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-166">`MyClass` cannot be used in standard modules.</span></span>  
  
- <span data-ttu-id="1c3e2-167">`MyClass` può essere utilizzata per qualificare un metodo definito in una classe di base e che non ha un'implementazione del metodo specificato in tale classe.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-167">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="1c3e2-168">Tale riferimento ha lo stesso significato di `MyBase.` *metodo*.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-168">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>  
  
 <span data-ttu-id="1c3e2-169">Nell'esempio seguente vengono confrontate `Me` e `MyClass`.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-169">The following example compares `Me` and `MyClass`.</span></span>  
  
```vb
Class baseClass  
    Public Overridable Sub testMethod()  
        MsgBox("Base class string")  
    End Sub  
    Public Sub useMe()  
        ' The following call uses the calling class's method, even if   
        ' that method is an override.  
        Me.testMethod()  
    End Sub  
    Public Sub useMyClass()  
        ' The following call uses this instance's method and not any  
        ' override.  
        MyClass.testMethod()  
    End Sub  
End Class  
Class derivedClass : Inherits baseClass  
    Public Overrides Sub testMethod()  
        MsgBox("Derived class string")  
    End Sub  
End Class  
Class testClasses  
    Sub startHere()  
        Dim testObj As derivedClass = New derivedClass()  
        ' The following call displays "Derived class string".  
        testObj.useMe()  
        ' The following call displays "Base class string".  
        testObj.useMyClass()  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="1c3e2-170">Sebbene `derivedClass` esegue l'override `testMethod`, il `MyClass` parola chiave nel `useMyClass` Annulla gli effetti dell'esecuzione dell'override e i compilatore risolve la chiamata a quella classe di base di `testMethod`.</span><span class="sxs-lookup"><span data-stu-id="1c3e2-170">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c3e2-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c3e2-171">See also</span></span>

- [<span data-ttu-id="1c3e2-172">Istruzione Inherits</span><span class="sxs-lookup"><span data-stu-id="1c3e2-172">Inherits Statement</span></span>](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="1c3e2-173">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="1c3e2-173">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)

---
title: Nozioni fondamentali sull'ereditarietà (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e37dabefcbda48144af910298dd4d82c13b7042
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="82c04-102">Nozioni fondamentali sull'ereditarietà (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82c04-102">Inheritance Basics (Visual Basic)</span></span>
<span data-ttu-id="82c04-103">Il `Inherits` istruzione viene utilizzata per dichiarare una nuova classe, denominata un *derivata*, in base a una classe esistente, nota come un *classe di base*.</span><span class="sxs-lookup"><span data-stu-id="82c04-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="82c04-104">Le classi derivate ereditano e possono estendere, proprietà, metodi, eventi, campi e costanti definite nella classe base.</span><span class="sxs-lookup"><span data-stu-id="82c04-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="82c04-105">Nella sezione seguente vengono descritte alcune delle regole per l'ereditarietà e i modificatori che è possibile utilizzare per modificare le classi modo ereditano o sono ereditati:</span><span class="sxs-lookup"><span data-stu-id="82c04-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>  
  
-   <span data-ttu-id="82c04-106">Per impostazione predefinita, tutte le classi sono ereditabili a meno che non contrassegnato con il `NotInheritable` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="82c04-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="82c04-107">Le classi possono ereditare da altre classi nel progetto o dalle classi in altri assembly che fa riferimento il progetto.</span><span class="sxs-lookup"><span data-stu-id="82c04-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>  
  
-   <span data-ttu-id="82c04-108">A differenza dei linguaggi che consentono l'ereditarietà multipla, Visual Basic consente solo l'ereditarietà singola nelle classi. vale a dire, le classi derivate possono avere solo una classe base.</span><span class="sxs-lookup"><span data-stu-id="82c04-108">Unlike languages that allow multiple inheritance, Visual Basic allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="82c04-109">Sebbene l'ereditarietà multipla non è consentita nelle classi, le classi possono implementare più interfacce, che possono raggiungere la stessa funzione.</span><span class="sxs-lookup"><span data-stu-id="82c04-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>  
  
-   <span data-ttu-id="82c04-110">Per evitare l'esposizione agli elementi in una classe base, il tipo di accesso di una classe derivata deve essere uguale o più restrittivo di quello della classe base.</span><span class="sxs-lookup"><span data-stu-id="82c04-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="82c04-111">Ad esempio, un `Public` classe non può ereditare un `Friend` o `Private` (classe) e un `Friend` classe non può ereditare un `Private` classe.</span><span class="sxs-lookup"><span data-stu-id="82c04-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>  
  
## <a name="inheritance-modifiers"></a><span data-ttu-id="82c04-112">Modificatori di ereditarietà</span><span class="sxs-lookup"><span data-stu-id="82c04-112">Inheritance Modifiers</span></span>  
 <span data-ttu-id="82c04-113">Visual Basic vengono presentate le istruzioni seguenti a livello di classe e i modificatori di supportano l'ereditarietà:</span><span class="sxs-lookup"><span data-stu-id="82c04-113">Visual Basic introduces the following class-level statements and modifiers to support inheritance:</span></span>  
  
-   <span data-ttu-id="82c04-114">`Inherits` istruzione: specifica la classe base.</span><span class="sxs-lookup"><span data-stu-id="82c04-114">`Inherits` statement — Specifies the base class.</span></span>  
  
-   <span data-ttu-id="82c04-115">`NotInheritable` modificatore: impedisce ai programmatori di utilizzo della classe come classe base.</span><span class="sxs-lookup"><span data-stu-id="82c04-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>  
  
-   <span data-ttu-id="82c04-116">`MustInherit` modificatore: Specifica che la classe è può essere utilizzata come classe di base.</span><span class="sxs-lookup"><span data-stu-id="82c04-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="82c04-117">Le istanze di `MustInherit` le classi non possono essere create direttamente; essi possono essere creati solo istanze della classe di base di una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="82c04-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="82c04-118">(Altri linguaggi di programmazione, ad esempio C++ e c#, usano il termine *classe astratta* per descrivere una classe.)</span><span class="sxs-lookup"><span data-stu-id="82c04-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="82c04-119">Override di proprietà e metodi nelle classi derivate</span><span class="sxs-lookup"><span data-stu-id="82c04-119">Overriding Properties and Methods in Derived Classes</span></span>  
 <span data-ttu-id="82c04-120">Per impostazione predefinita, una classe derivata eredita le proprietà e metodi della classe base.</span><span class="sxs-lookup"><span data-stu-id="82c04-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="82c04-121">Se una proprietà o metodo ha un comportamento diverso nella classe derivata può essere *sottoposto a override*.</span><span class="sxs-lookup"><span data-stu-id="82c04-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="82c04-122">Ovvero, è possibile definire una nuova implementazione del metodo nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="82c04-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="82c04-123">I seguenti modificatori consentono di controllare le modalità di override di proprietà e metodi:</span><span class="sxs-lookup"><span data-stu-id="82c04-123">The following modifiers are used to control how properties and methods are overridden:</span></span>  
  
-   <span data-ttu-id="82c04-124">`Overridable` -Consente di una proprietà o metodo in una classe per eseguire l'override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="82c04-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>  
  
-   <span data-ttu-id="82c04-125">`Overrides` : Esegue l'override di un `Overridable` proprietà o un metodo definito nella classe base.</span><span class="sxs-lookup"><span data-stu-id="82c04-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>  
  
-   <span data-ttu-id="82c04-126">`NotOverridable` -Impedisce una proprietà o un metodo da sottoporre a override in una classe che eredita.</span><span class="sxs-lookup"><span data-stu-id="82c04-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="82c04-127">Per impostazione predefinita, `Public` metodi sono `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="82c04-127">By default, `Public` methods are `NotOverridable`.</span></span>  
  
-   <span data-ttu-id="82c04-128">`MustOverride` : Richiede che una classe derivata esegue l'override di proprietà o metodo.</span><span class="sxs-lookup"><span data-stu-id="82c04-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="82c04-129">Quando il `MustOverride` parola chiave viene utilizzata, la definizione del metodo è costituita solo il `Sub`, `Function`, o `Property` istruzione.</span><span class="sxs-lookup"><span data-stu-id="82c04-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="82c04-130">Le altre istruzioni non sono consentite in modo specifico, non `End Sub` o `End Function` istruzione.</span><span class="sxs-lookup"><span data-stu-id="82c04-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="82c04-131">`MustOverride` i metodi devono essere dichiarati `MustInherit` classi.</span><span class="sxs-lookup"><span data-stu-id="82c04-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>  
  
 <span data-ttu-id="82c04-132">Si supponga che si desidera definire le classi per la gestione delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="82c04-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="82c04-133">È possibile definire un oggetto generico `Payroll` classe che contiene un `RunPayroll` metodo che calcola retribuzioni di una settimana tipica.</span><span class="sxs-lookup"><span data-stu-id="82c04-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="82c04-134">È quindi possibile utilizzare `Payroll` come classe base per una più specializzato `BonusPayroll` (classe), che potrebbe essere usate quando si distribuiscono bonus ai dipendenti.</span><span class="sxs-lookup"><span data-stu-id="82c04-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>  
  
 <span data-ttu-id="82c04-135">Il `BonusPayroll` classe può ereditare ed eseguire l'override, il `PayEmployee` metodo definito nella base `Payroll` classe.</span><span class="sxs-lookup"><span data-stu-id="82c04-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>  
  
 <span data-ttu-id="82c04-136">L'esempio seguente definisce una classe base, `Payroll,` e una classe derivata, `BonusPayroll`, che esegue l'override di un metodo ereditato, `PayEmployee`.</span><span class="sxs-lookup"><span data-stu-id="82c04-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="82c04-137">Una routine, `RunPayroll`, crea e passa quindi un `Payroll` oggetto e un `BonusPayroll` oggetto a una funzione, `Pay`, che viene eseguita la `PayEmployee` metodo di entrambi gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="82c04-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>  
  
 [!code-vb[VbVbalrOOP#28](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]  
  
## <a name="the-mybase-keyword"></a><span data-ttu-id="82c04-138">La parola chiave MyBase</span><span class="sxs-lookup"><span data-stu-id="82c04-138">The MyBase Keyword</span></span>  
 <span data-ttu-id="82c04-139">Il `MyBase` (parola chiave) si comporta come una variabile oggetto che fa riferimento alla classe di base dell'istanza corrente di una classe.</span><span class="sxs-lookup"><span data-stu-id="82c04-139">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="82c04-140">`MyBase` viene spesso utilizzato per accedere ai membri di classe di base che vengono sottoposti a override o shadowing in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="82c04-140">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="82c04-141">In particolare, `MyBase.New` viene utilizzata per chiamare in modo esplicito un costruttore di classe di base da un costruttore di classe derivata.</span><span class="sxs-lookup"><span data-stu-id="82c04-141">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
 <span data-ttu-id="82c04-142">Si supponga, ad esempio, che si progetta una classe derivata che esegue l'override di un metodo ereditato dalla classe di base.</span><span class="sxs-lookup"><span data-stu-id="82c04-142">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="82c04-143">Il metodo sottoposto a override è possibile chiamare il metodo nella classe base e modificare il valore restituito, come illustrato nel frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="82c04-143">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#109](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]  
  
 <span data-ttu-id="82c04-144">Nell'elenco seguente descrive le restrizioni sull'utilizzo di `MyBase`:</span><span class="sxs-lookup"><span data-stu-id="82c04-144">The following list describes restrictions on using `MyBase`:</span></span>  
  
-   <span data-ttu-id="82c04-145">`MyBase` fa riferimento alla classe base immediata e i relativi membri ereditati.</span><span class="sxs-lookup"><span data-stu-id="82c04-145">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="82c04-146">Non può essere utilizzato per accedere a `Private` membri della classe.</span><span class="sxs-lookup"><span data-stu-id="82c04-146">It cannot be used to access `Private` members in the class.</span></span>  
  
-   <span data-ttu-id="82c04-147">`MyBase` è una parola chiave, non un oggetto reale.</span><span class="sxs-lookup"><span data-stu-id="82c04-147">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="82c04-148">`MyBase` non è possibile assegnare a una variabile, passare alle procedure o un `Is` confronto.</span><span class="sxs-lookup"><span data-stu-id="82c04-148">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
-   <span data-ttu-id="82c04-149">Il metodo che `MyBase` qualifica non deve essere definito nella classe base immediata; potrebbe invece essere definita in una classe di base ereditata indirettamente.</span><span class="sxs-lookup"><span data-stu-id="82c04-149">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="82c04-150">Affinché un riferimento qualificato da `MyBase` venga compilato correttamente, una classe di base deve contenere un metodo corrispondente al nome e i tipi di parametri presenti nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="82c04-150">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>  
  
-   <span data-ttu-id="82c04-151">Non è possibile utilizzare `MyBase` chiamare `MustOverride` metodi della classe di base.</span><span class="sxs-lookup"><span data-stu-id="82c04-151">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>  
  
-   <span data-ttu-id="82c04-152">`MyBase` non può essere utilizzato per qualificare se stesso.</span><span class="sxs-lookup"><span data-stu-id="82c04-152">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="82c04-153">Pertanto, il codice seguente non è valido:</span><span class="sxs-lookup"><span data-stu-id="82c04-153">Therefore, the following code is not valid:</span></span>  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   <span data-ttu-id="82c04-154">`MyBase` non può essere utilizzata nei moduli.</span><span class="sxs-lookup"><span data-stu-id="82c04-154">`MyBase` cannot be used in modules.</span></span>  
  
-   <span data-ttu-id="82c04-155">`MyBase` non può essere utilizzato per accedere ai membri di classe di base che sono contrassegnati come `Friend` se la classe di base si trova in un assembly diverso.</span><span class="sxs-lookup"><span data-stu-id="82c04-155">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>  
  
 <span data-ttu-id="82c04-156">Per ulteriori informazioni e un altro esempio, vedere [procedura: accedere a una variabile nascosta da una classe derivata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="82c04-156">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
## <a name="the-myclass-keyword"></a><span data-ttu-id="82c04-157">La parola chiave MyClass</span><span class="sxs-lookup"><span data-stu-id="82c04-157">The MyClass Keyword</span></span>  
 <span data-ttu-id="82c04-158">Il `MyClass` (parola chiave) si comporta come una variabile oggetto che fa riferimento all'istanza corrente di una classe come implementata originariamente.</span><span class="sxs-lookup"><span data-stu-id="82c04-158">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="82c04-159">`MyClass` è simile `Me`, ma ogni metodo e proprietà chiamare sul `MyClass` viene trattato come se il metodo o proprietà fosse [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span><span class="sxs-lookup"><span data-stu-id="82c04-159">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="82c04-160">Pertanto, il metodo o proprietà non è interessata eseguendo l'override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="82c04-160">Therefore, the method or property is not affected by overriding in a derived class.</span></span>  
  
-   <span data-ttu-id="82c04-161">`MyClass` è una parola chiave, non un oggetto reale.</span><span class="sxs-lookup"><span data-stu-id="82c04-161">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="82c04-162">`MyClass` non è possibile assegnare a una variabile, passare alle procedure o un `Is` confronto.</span><span class="sxs-lookup"><span data-stu-id="82c04-162">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
-   <span data-ttu-id="82c04-163">`MyClass` fa riferimento a tale classe e i relativi membri ereditati.</span><span class="sxs-lookup"><span data-stu-id="82c04-163">`MyClass` refers to the containing class and its inherited members.</span></span>  
  
-   <span data-ttu-id="82c04-164">`MyClass` può essere utilizzato come qualificatore per `Shared` membri.</span><span class="sxs-lookup"><span data-stu-id="82c04-164">`MyClass` can be used as a qualifier for `Shared` members.</span></span>  
  
-   <span data-ttu-id="82c04-165">`MyClass` non può essere utilizzato all'interno di un `Shared` (metodo), ma può essere utilizzato all'interno di un metodo di istanza per accedere a un membro di una classe condiviso.</span><span class="sxs-lookup"><span data-stu-id="82c04-165">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>  
  
-   <span data-ttu-id="82c04-166">`MyClass` non può essere utilizzata nei moduli standard.</span><span class="sxs-lookup"><span data-stu-id="82c04-166">`MyClass` cannot be used in standard modules.</span></span>  
  
-   <span data-ttu-id="82c04-167">`MyClass` può essere utilizzato per qualificare un metodo che è definito in una classe base e che non contiene alcuna implementazione del metodo fornito in quella classe.</span><span class="sxs-lookup"><span data-stu-id="82c04-167">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="82c04-168">Questo riferimento ha lo stesso significato di `MyBase.` *metodo*.</span><span class="sxs-lookup"><span data-stu-id="82c04-168">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>  
  
 <span data-ttu-id="82c04-169">Nell'esempio seguente vengono confrontate `Me` e `MyClass`.</span><span class="sxs-lookup"><span data-stu-id="82c04-169">The following example compares `Me` and `MyClass`.</span></span>  
  
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
  
 <span data-ttu-id="82c04-170">Anche se `derivedClass` esegue l'override `testMethod`, `MyClass` parola chiave in `useMyClass` Annulla gli effetti dell'override e i compilatore consente di risolvere la chiamata per la versione della classe base `testMethod`.</span><span class="sxs-lookup"><span data-stu-id="82c04-170">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82c04-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82c04-171">See Also</span></span>  
 [<span data-ttu-id="82c04-172">Istruzione Inherits</span><span class="sxs-lookup"><span data-stu-id="82c04-172">Inherits Statement</span></span>](../../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [<span data-ttu-id="82c04-173">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="82c04-173">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)

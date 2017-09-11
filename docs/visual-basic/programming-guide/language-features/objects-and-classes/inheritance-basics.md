---
title: "Nozioni fondamentali sull&quot;ereditarietà (Visual Basic) | Documenti di Microsoft"
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
- derived classes, inheritance
- MyClass keyword, using
- MyBase keyword, using
- Inherits statement, inheritance
- overriding, Overridable keyword
- MustInherit keyword, using
- Overrides keyword, using
- inheritance
- MustInherit classes
- MustOverride keyword, using
- classes [Visual Basic], derived
- NotInheritable keyword, using
- base classes, extending properties and methods
- NotOverridable keyword, using
- base classes, inheritance
- abstract classes, inheritance
- overriding, Overrides keyword
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
caps.latest.revision: 23
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
ms.sourcegitcommit: 4892ed6dcfb3843bd6cb2de2d3e032bfeb1efdf9
ms.openlocfilehash: 43b6505634b12f7f8353866e938151f1e00fb073
ms.contentlocale: it-it
ms.lasthandoff: 05/16/2017

---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="a0098-102">Nozioni fondamentali sull'ereditarietà (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a0098-102">Inheritance Basics (Visual Basic)</span></span>
<span data-ttu-id="a0098-103">Il `Inherits` istruzione viene utilizzata per dichiarare una nuova classe, denominata un *derivata*, in base a una classe esistente, nota come un *classe di base*.</span><span class="sxs-lookup"><span data-stu-id="a0098-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="a0098-104">Le classi derivate ereditano e possono estendere, proprietà, metodi, eventi, campi e le costanti definite nella classe di base.</span><span class="sxs-lookup"><span data-stu-id="a0098-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="a0098-105">Nella sezione seguente vengono descritte alcune delle regole per l'ereditarietà e i modificatori che è possibile utilizzare per modificare le classi modo ereditano o vengono ereditati:</span><span class="sxs-lookup"><span data-stu-id="a0098-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>  
  
-   <span data-ttu-id="a0098-106">Per impostazione predefinita, tutte le classi sono ereditabili a meno che non contrassegnato con il `NotInheritable` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="a0098-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="a0098-107">Le classi possono ereditare da altre classi nel progetto o dalle classi in altri assembly che fa riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="a0098-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>  
  
-   <span data-ttu-id="a0098-108">A differenza dei linguaggi che consentono l'ereditarietà multipla, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] consente l'ereditarietà singola solo nelle classi; ovvero le classi derivate possono avere una sola classe base.</span><span class="sxs-lookup"><span data-stu-id="a0098-108">Unlike languages that allow multiple inheritance, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="a0098-109">Sebbene l'ereditarietà multipla non è consentita nelle classi, le classi possono implementare più interfacce, che possono raggiungere la stessa funzione.</span><span class="sxs-lookup"><span data-stu-id="a0098-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>  
  
-   <span data-ttu-id="a0098-110">Per impedire l'esposizione agli elementi in una classe base, il tipo di accesso di una classe derivata deve essere uguale o più restrittivo rispetto alla classe di base.</span><span class="sxs-lookup"><span data-stu-id="a0098-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="a0098-111">Ad esempio, un `Public` classe non può ereditare un `Friend` o `Private` (classe) e un `Friend` classe non può ereditare un `Private` (classe).</span><span class="sxs-lookup"><span data-stu-id="a0098-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>  
  
## <a name="inheritance-modifiers"></a><span data-ttu-id="a0098-112">Modificatori di ereditarietà</span><span class="sxs-lookup"><span data-stu-id="a0098-112">Inheritance Modifiers</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="a0098-113">vengono presentate le istruzioni seguenti a livello di classe e modificatori per supportare l'ereditarietà:</span><span class="sxs-lookup"><span data-stu-id="a0098-113"> introduces the following class-level statements and modifiers to support inheritance:</span></span>  
  
-   <span data-ttu-id="a0098-114">`Inherits`istruzione: specifica la classe base.</span><span class="sxs-lookup"><span data-stu-id="a0098-114">`Inherits` statement — Specifies the base class.</span></span>  
  
-   <span data-ttu-id="a0098-115">`NotInheritable`modificatore-impedisce ai programmatori di utilizzo della classe come classe base.</span><span class="sxs-lookup"><span data-stu-id="a0098-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>  
  
-   <span data-ttu-id="a0098-116">`MustInherit`modificatore: Specifica che la classe è può essere utilizzata come classe di base.</span><span class="sxs-lookup"><span data-stu-id="a0098-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="a0098-117">Le istanze di `MustInherit` le classi non possono essere create direttamente; essi possono essere create solo istanze della classe di base di una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="a0098-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="a0098-118">(Altri linguaggi di programmazione, ad esempio C++ e c#, utilizzano il termine *classe astratta* per descrivere tale classe.)</span><span class="sxs-lookup"><span data-stu-id="a0098-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="a0098-119">Override di proprietà e metodi nelle classi derivate</span><span class="sxs-lookup"><span data-stu-id="a0098-119">Overriding Properties and Methods in Derived Classes</span></span>  
 <span data-ttu-id="a0098-120">Per impostazione predefinita, una classe derivata eredita le proprietà e metodi della classe base.</span><span class="sxs-lookup"><span data-stu-id="a0098-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="a0098-121">Se una proprietà o metodo ha un comportamento diverso nella classe derivata può essere *sottoposto a override*.</span><span class="sxs-lookup"><span data-stu-id="a0098-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="a0098-122">Vale a dire, è possibile definire una nuova implementazione del metodo nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="a0098-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="a0098-123">I seguenti modificatori consentono di controllare le modalità di override di proprietà e metodi:</span><span class="sxs-lookup"><span data-stu-id="a0098-123">The following modifiers are used to control how properties and methods are overridden:</span></span>  
  
-   <span data-ttu-id="a0098-124">`Overridable`-Consente di una proprietà o metodo in una classe può essere sottoposto a override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="a0098-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>  
  
-   <span data-ttu-id="a0098-125">`Overrides`: Esegue l'override di un `Overridable` proprietà o metodo definito nella classe di base.</span><span class="sxs-lookup"><span data-stu-id="a0098-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>  
  
-   <span data-ttu-id="a0098-126">`NotOverridable`-Impedisce una proprietà o metodo viene sottoposto a override in una classe che eredita.</span><span class="sxs-lookup"><span data-stu-id="a0098-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="a0098-127">Per impostazione predefinita, `Public` metodi sono `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="a0098-127">By default, `Public` methods are `NotOverridable`.</span></span>  
  
-   <span data-ttu-id="a0098-128">`MustOverride`È necessario che una classe derivata eseguono l'override di proprietà o metodo.</span><span class="sxs-lookup"><span data-stu-id="a0098-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="a0098-129">Quando il `MustOverride` parola chiave viene utilizzata, la definizione del metodo è costituita solo il `Sub`, `Function`, o `Property` istruzione.</span><span class="sxs-lookup"><span data-stu-id="a0098-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="a0098-130">Le altre istruzioni non sono consentite in modo specifico, non `End Sub` o `End Function` istruzione.</span><span class="sxs-lookup"><span data-stu-id="a0098-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="a0098-131">`MustOverride`i metodi devono essere dichiarati `MustInherit` classi.</span><span class="sxs-lookup"><span data-stu-id="a0098-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>  
  
 <span data-ttu-id="a0098-132">Si supponga che si desidera definire classi per la gestione delle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="a0098-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="a0098-133">È possibile definire un oggetto generico `Payroll` classe che contiene un `RunPayroll` metodo che calcola retribuzioni per una settimana tipica.</span><span class="sxs-lookup"><span data-stu-id="a0098-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="a0098-134">È quindi possibile utilizzare `Payroll` come classe base per una più specializzato `BonusPayroll` (classe), che può essere utilizzata durante la distribuzione di bonus ai dipendenti.</span><span class="sxs-lookup"><span data-stu-id="a0098-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>  
  
 <span data-ttu-id="a0098-135">Il `BonusPayroll` classe può ereditare ed eseguire l'override, il `PayEmployee` metodo definito nella base `Payroll` (classe).</span><span class="sxs-lookup"><span data-stu-id="a0098-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>  
  
 <span data-ttu-id="a0098-136">Nell'esempio seguente definisce una classe base, `Payroll,` e una classe derivata, `BonusPayroll`, che esegue l'override di un metodo ereditato, `PayEmployee`.</span><span class="sxs-lookup"><span data-stu-id="a0098-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="a0098-137">Una routine, `RunPayroll`, crea e passa quindi un `Payroll` oggetto e un `BonusPayroll` oggetto a una funzione, `Pay`, che esegue il `PayEmployee` metodo di entrambi gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="a0098-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>  
  
 <span data-ttu-id="a0098-138">[!code-vb[28 VbVbalrOOP](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a0098-138">[!code-vb[VbVbalrOOP#28](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]</span></span>  
  
## <a name="the-mybase-keyword"></a><span data-ttu-id="a0098-139">La parola chiave MyBase</span><span class="sxs-lookup"><span data-stu-id="a0098-139">The MyBase Keyword</span></span>  
 <span data-ttu-id="a0098-140">Il `MyBase` (parola chiave) si comporta come una variabile oggetto che fa riferimento alla classe di base dell'istanza corrente di una classe.</span><span class="sxs-lookup"><span data-stu-id="a0098-140">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="a0098-141">`MyBase`viene spesso utilizzato per accedere ai membri di classe di base sottoposti a override o nascosti in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="a0098-141">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="a0098-142">In particolare, `MyBase.New` viene utilizzato per chiamare in modo esplicito un costruttore di classe di base da un costruttore di classe derivata.</span><span class="sxs-lookup"><span data-stu-id="a0098-142">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
 <span data-ttu-id="a0098-143">Si supponga, ad esempio, che si progetta una classe derivata che esegue l'override di un metodo ereditato dalla classe di base.</span><span class="sxs-lookup"><span data-stu-id="a0098-143">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="a0098-144">Il metodo sottoposto a override può chiamare il metodo nella classe di base e modificare il valore restituito, come illustrato nel frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a0098-144">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>  
  
 <span data-ttu-id="a0098-145">[!code-vb[VbVbalrOOP&#109;](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="a0098-145">[!code-vb[VbVbalrOOP#109](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]</span></span>  
  
 <span data-ttu-id="a0098-146">Nell'elenco seguente descrive le restrizioni sull'utilizzo di `MyBase`:</span><span class="sxs-lookup"><span data-stu-id="a0098-146">The following list describes restrictions on using `MyBase`:</span></span>  
  
-   <span data-ttu-id="a0098-147">`MyBase`fa riferimento alla classe base immediata e i relativi membri ereditati.</span><span class="sxs-lookup"><span data-stu-id="a0098-147">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="a0098-148">Non può essere utilizzato per accedere a `Private` membri della classe.</span><span class="sxs-lookup"><span data-stu-id="a0098-148">It cannot be used to access `Private` members in the class.</span></span>  
  
-   <span data-ttu-id="a0098-149">`MyBase`è una parola chiave, non un oggetto reale.</span><span class="sxs-lookup"><span data-stu-id="a0098-149">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="a0098-150">`MyBase`non può essere assegnato a una variabile, passare alle procedure o utilizzato in un `Is` confronto.</span><span class="sxs-lookup"><span data-stu-id="a0098-150">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
-   <span data-ttu-id="a0098-151">Il metodo che `MyBase` qualifica non deve essere definito nella classe base immediata; potrebbe invece essere definita in una classe base ereditata indirettamente.</span><span class="sxs-lookup"><span data-stu-id="a0098-151">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="a0098-152">Affinché un riferimento qualificato da `MyBase` per compilare correttamente, una classe di base deve contenere un metodo corrispondente al nome e i tipi di parametri presenti nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="a0098-152">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>  
  
-   <span data-ttu-id="a0098-153">Non è possibile utilizzare `MyBase` chiamare `MustOverride` metodi della classe di base.</span><span class="sxs-lookup"><span data-stu-id="a0098-153">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>  
  
-   <span data-ttu-id="a0098-154">`MyBase`non può essere utilizzato per qualificare se stesso.</span><span class="sxs-lookup"><span data-stu-id="a0098-154">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="a0098-155">Pertanto, il codice seguente non è valido:</span><span class="sxs-lookup"><span data-stu-id="a0098-155">Therefore, the following code is not valid:</span></span>  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   <span data-ttu-id="a0098-156">`MyBase`non può essere utilizzata nei moduli.</span><span class="sxs-lookup"><span data-stu-id="a0098-156">`MyBase` cannot be used in modules.</span></span>  
  
-   <span data-ttu-id="a0098-157">`MyBase`non può essere utilizzato per accedere ai membri di classe di base che sono contrassegnati come `Friend` se la classe di base si trova in un assembly diverso.</span><span class="sxs-lookup"><span data-stu-id="a0098-157">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>  
  
 <span data-ttu-id="a0098-158">Per ulteriori informazioni e un altro esempio, vedere [procedura: accedere a una variabile nascosta da una classe derivata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="a0098-158">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
## <a name="the-myclass-keyword"></a><span data-ttu-id="a0098-159">La parola chiave MyClass</span><span class="sxs-lookup"><span data-stu-id="a0098-159">The MyClass Keyword</span></span>  
 <span data-ttu-id="a0098-160">Il `MyClass` (parola chiave) si comporta come una variabile oggetto che fa riferimento all'istanza corrente di una classe sua implementata originale.</span><span class="sxs-lookup"><span data-stu-id="a0098-160">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="a0098-161">`MyClass`è simile a `Me`, ma tutti i metodi e proprietà chiamare su `MyClass` viene trattato come se fosse il metodo o proprietà [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span><span class="sxs-lookup"><span data-stu-id="a0098-161">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="a0098-162">Pertanto, il metodo o proprietà non è interessata eseguendo l'override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="a0098-162">Therefore, the method or property is not affected by overriding in a derived class.</span></span>  
  
-   <span data-ttu-id="a0098-163">`MyClass`è una parola chiave, non un oggetto reale.</span><span class="sxs-lookup"><span data-stu-id="a0098-163">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="a0098-164">`MyClass`non può essere assegnato a una variabile, passare alle procedure o utilizzato in un `Is` confronto.</span><span class="sxs-lookup"><span data-stu-id="a0098-164">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
-   <span data-ttu-id="a0098-165">`MyClass`fa riferimento a tale classe e i relativi membri ereditati.</span><span class="sxs-lookup"><span data-stu-id="a0098-165">`MyClass` refers to the containing class and its inherited members.</span></span>  
  
-   <span data-ttu-id="a0098-166">`MyClass`può essere utilizzato come qualificatore per `Shared` i membri.</span><span class="sxs-lookup"><span data-stu-id="a0098-166">`MyClass` can be used as a qualifier for `Shared` members.</span></span>  
  
-   <span data-ttu-id="a0098-167">`MyClass`non può essere utilizzato all'interno di un `Shared` (metodo), ma può essere utilizzato all'interno di un metodo di istanza per accedere a un membro di una classe condiviso.</span><span class="sxs-lookup"><span data-stu-id="a0098-167">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>  
  
-   <span data-ttu-id="a0098-168">`MyClass`non può essere utilizzata nei moduli standard.</span><span class="sxs-lookup"><span data-stu-id="a0098-168">`MyClass` cannot be used in standard modules.</span></span>  
  
-   <span data-ttu-id="a0098-169">`MyClass`può essere utilizzato per qualificare un metodo definito in una classe base e che non ha un'implementazione del metodo fornito in tale classe.</span><span class="sxs-lookup"><span data-stu-id="a0098-169">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="a0098-170">Questo riferimento ha lo stesso significato di `MyBase.` *metodo*.</span><span class="sxs-lookup"><span data-stu-id="a0098-170">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>  
  
 <span data-ttu-id="a0098-171">Nell'esempio seguente vengono confrontate `Me` e `MyClass`.</span><span class="sxs-lookup"><span data-stu-id="a0098-171">The following example compares `Me` and `MyClass`.</span></span>  
  
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
  
 <span data-ttu-id="a0098-172">Anche se `derivedClass` sostituzioni `testMethod`, `MyClass` (parola chiave) in `useMyClass` Annulla gli effetti dell'esecuzione dell'override e i compilatore risolve la chiamata alla versione della classe base di `testMethod`.</span><span class="sxs-lookup"><span data-stu-id="a0098-172">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0098-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0098-173">See Also</span></span>  
 <span data-ttu-id="a0098-174">[Inherits (istruzione)](../../../../visual-basic/language-reference/statements/inherits-statement.md) </span><span class="sxs-lookup"><span data-stu-id="a0098-174">[Inherits Statement](../../../../visual-basic/language-reference/statements/inherits-statement.md) </span></span>  
<span data-ttu-id="a0098-175"> [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span><span class="sxs-lookup"><span data-stu-id="a0098-175"> [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span></span>


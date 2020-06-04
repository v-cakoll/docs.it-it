---
title: Nozioni fondamentali sull'ereditarietà
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
ms.openlocfilehash: 3bf1847f618a642d26df4aa1c5247a4ba2bd3b23
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411779"
---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="d4f40-102">Nozioni fondamentali sull'ereditarietà (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4f40-102">Inheritance Basics (Visual Basic)</span></span>

<span data-ttu-id="d4f40-103">L' `Inherits` istruzione viene usata per dichiarare una nuova classe, denominata *classe derivata*, basata su una classe esistente, nota come classe di *base*.</span><span class="sxs-lookup"><span data-stu-id="d4f40-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="d4f40-104">Le classi derivate ereditano e possono estendere, le proprietà, i metodi, gli eventi, i campi e le costanti definiti nella classe di base.</span><span class="sxs-lookup"><span data-stu-id="d4f40-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="d4f40-105">Nella sezione seguente vengono descritte alcune delle regole per l'ereditarietà e i modificatori che è possibile utilizzare per modificare il modo in cui le classi ereditano o vengono ereditate:</span><span class="sxs-lookup"><span data-stu-id="d4f40-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>

- <span data-ttu-id="d4f40-106">Per impostazione predefinita, tutte le classi sono ereditabili, a meno che non siano contrassegnate con la `NotInheritable` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="d4f40-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="d4f40-107">Le classi possono ereditare da altre classi nel progetto o da classi di altri assembly a cui fa riferimento il progetto.</span><span class="sxs-lookup"><span data-stu-id="d4f40-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>

- <span data-ttu-id="d4f40-108">Diversamente dalle lingue che consentono l'ereditarietà multipla, Visual Basic consente solo l'ereditarietà singola nelle classi; ovvero, le classi derivate possono avere una sola classe di base.</span><span class="sxs-lookup"><span data-stu-id="d4f40-108">Unlike languages that allow multiple inheritance, Visual Basic allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="d4f40-109">Sebbene l'ereditarietà multipla non sia consentita nelle classi, le classi possono implementare più interfacce, che possono raggiungere le stesse entità finali.</span><span class="sxs-lookup"><span data-stu-id="d4f40-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>

- <span data-ttu-id="d4f40-110">Per impedire l'esposizione di elementi con restrizioni in una classe base, il tipo di accesso di una classe derivata deve essere uguale o più restrittivo rispetto alla relativa classe di base.</span><span class="sxs-lookup"><span data-stu-id="d4f40-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="d4f40-111">Ad esempio, una `Public` classe non può ereditare una classe `Friend` o `Private` e una classe `Friend` non può ereditare una `Private` classe.</span><span class="sxs-lookup"><span data-stu-id="d4f40-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>

## <a name="inheritance-modifiers"></a><span data-ttu-id="d4f40-112">Modificatori di ereditarietà</span><span class="sxs-lookup"><span data-stu-id="d4f40-112">Inheritance Modifiers</span></span>

<span data-ttu-id="d4f40-113">Visual Basic introduce le istruzioni e i modificatori a livello di classe seguenti per supportare l'ereditarietà:</span><span class="sxs-lookup"><span data-stu-id="d4f40-113">Visual Basic introduces the following class-level statements and modifiers to support inheritance:</span></span>

- <span data-ttu-id="d4f40-114">`Inherits`Statement-specifica la classe base.</span><span class="sxs-lookup"><span data-stu-id="d4f40-114">`Inherits` statement — Specifies the base class.</span></span>

- <span data-ttu-id="d4f40-115">`NotInheritable`modificatore: impedisce ai programmatori di usare la classe come classe di base.</span><span class="sxs-lookup"><span data-stu-id="d4f40-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>

- <span data-ttu-id="d4f40-116">`MustInherit`modificatore — specifica che la classe deve essere usata solo come classe base.</span><span class="sxs-lookup"><span data-stu-id="d4f40-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="d4f40-117">`MustInherit`Non è possibile creare direttamente istanze delle classi. possono essere create solo come istanze della classe di base di una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="d4f40-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="d4f40-118">(Altri linguaggi di programmazione, ad esempio C++ e C#, usano il termine *classe astratta* per descrivere tale classe).</span><span class="sxs-lookup"><span data-stu-id="d4f40-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>

## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="d4f40-119">Override di proprietà e metodi nelle classi derivate</span><span class="sxs-lookup"><span data-stu-id="d4f40-119">Overriding Properties and Methods in Derived Classes</span></span>

<span data-ttu-id="d4f40-120">Per impostazione predefinita, una classe derivata eredita proprietà e metodi dalla relativa classe di base.</span><span class="sxs-lookup"><span data-stu-id="d4f40-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="d4f40-121">Se una proprietà o un metodo ereditato deve comportarsi in modo diverso nella classe derivata, è possibile eseguirne l' *override*.</span><span class="sxs-lookup"><span data-stu-id="d4f40-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="d4f40-122">Ovvero, è possibile definire una nuova implementazione del metodo nella classe derivata.</span><span class="sxs-lookup"><span data-stu-id="d4f40-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="d4f40-123">I seguenti modificatori consentono di controllare le modalità di override di proprietà e metodi:</span><span class="sxs-lookup"><span data-stu-id="d4f40-123">The following modifiers are used to control how properties and methods are overridden:</span></span>

- <span data-ttu-id="d4f40-124">`Overridable`: Consente di eseguire l'override di una proprietà o di un metodo in una classe in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="d4f40-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>

- <span data-ttu-id="d4f40-125">`Overrides`: Esegue l'override di una `Overridable` proprietà o di un metodo definito nella classe base.</span><span class="sxs-lookup"><span data-stu-id="d4f40-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>

- <span data-ttu-id="d4f40-126">`NotOverridable`: Impedisce l'override di una proprietà o di un metodo in una classe che eredita.</span><span class="sxs-lookup"><span data-stu-id="d4f40-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="d4f40-127">Per impostazione predefinita, `Public` i metodi sono `NotOverridable` .</span><span class="sxs-lookup"><span data-stu-id="d4f40-127">By default, `Public` methods are `NotOverridable`.</span></span>

- <span data-ttu-id="d4f40-128">`MustOverride`: Richiede che una classe derivata esegua l'override della proprietà o del metodo.</span><span class="sxs-lookup"><span data-stu-id="d4f40-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="d4f40-129">Quando `MustOverride` si utilizza la parola chiave, la definizione del metodo è costituita solo dall' `Sub` `Function` istruzione, o `Property` .</span><span class="sxs-lookup"><span data-stu-id="d4f40-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="d4f40-130">Non sono consentite altre istruzioni e in particolare non esiste alcuna `End Sub` `End Function` istruzione o.</span><span class="sxs-lookup"><span data-stu-id="d4f40-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="d4f40-131">`MustOverride`i metodi devono essere dichiarati nelle `MustInherit` classi.</span><span class="sxs-lookup"><span data-stu-id="d4f40-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>

<span data-ttu-id="d4f40-132">Si supponga di voler definire le classi per gestire le retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="d4f40-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="d4f40-133">È possibile definire una classe generica `Payroll` che contiene un `RunPayroll` metodo che calcola lo stipendio per una settimana tipica.</span><span class="sxs-lookup"><span data-stu-id="d4f40-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="d4f40-134">È quindi possibile usare `Payroll` come classe base per una classe più specializzata `BonusPayroll` , che può essere usata quando si distribuiscono i bonus dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="d4f40-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>

<span data-ttu-id="d4f40-135">La `BonusPayroll` classe può ereditare ed eseguire l'override del `PayEmployee` metodo definito nella `Payroll` classe base.</span><span class="sxs-lookup"><span data-stu-id="d4f40-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>

<span data-ttu-id="d4f40-136">L'esempio seguente definisce una classe di base `Payroll,` e una classe derivata, `BonusPayroll` , che esegue l'override di un metodo ereditato, `PayEmployee` .</span><span class="sxs-lookup"><span data-stu-id="d4f40-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="d4f40-137">Una routine, `RunPayroll` , crea e quindi passa un `Payroll` oggetto e un `BonusPayroll` oggetto a una funzione, `Pay` , che esegue il `PayEmployee` metodo di entrambi gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="d4f40-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a><span data-ttu-id="d4f40-138">Parola chiave MyBase</span><span class="sxs-lookup"><span data-stu-id="d4f40-138">The MyBase Keyword</span></span>

<span data-ttu-id="d4f40-139">La `MyBase` parola chiave si comporta come una variabile oggetto che fa riferimento alla classe di base dell'istanza corrente di una classe.</span><span class="sxs-lookup"><span data-stu-id="d4f40-139">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="d4f40-140">`MyBase`viene spesso usato per accedere ai membri della classe base sottoposti a override o nascosti in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="d4f40-140">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="d4f40-141">In particolare, `MyBase.New` viene usato per chiamare in modo esplicito un costruttore della classe base da un costruttore di classe derivata.</span><span class="sxs-lookup"><span data-stu-id="d4f40-141">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>

<span data-ttu-id="d4f40-142">Si supponga, ad esempio, di progettare una classe derivata che esegue l'override di un metodo ereditato dalla classe base.</span><span class="sxs-lookup"><span data-stu-id="d4f40-142">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="d4f40-143">Il metodo sottoposto a override può chiamare il metodo nella classe base e modificare il valore restituito come illustrato nel frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d4f40-143">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

<span data-ttu-id="d4f40-144">Nell'elenco seguente vengono descritte le restrizioni relative all'utilizzo di `MyBase` :</span><span class="sxs-lookup"><span data-stu-id="d4f40-144">The following list describes restrictions on using `MyBase`:</span></span>

- <span data-ttu-id="d4f40-145">`MyBase`si riferisce alla classe di base immediata e ai relativi membri ereditati.</span><span class="sxs-lookup"><span data-stu-id="d4f40-145">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="d4f40-146">Non può essere usato per accedere ai `Private` membri della classe.</span><span class="sxs-lookup"><span data-stu-id="d4f40-146">It cannot be used to access `Private` members in the class.</span></span>

- <span data-ttu-id="d4f40-147">`MyBase`è una parola chiave, non un oggetto reale.</span><span class="sxs-lookup"><span data-stu-id="d4f40-147">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="d4f40-148">`MyBase`non può essere assegnato a una variabile, passato a procedure o utilizzato in un `Is` confronto.</span><span class="sxs-lookup"><span data-stu-id="d4f40-148">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>

- <span data-ttu-id="d4f40-149">Il metodo che `MyBase` qualifica non deve essere definito nella classe di base immediata; può invece essere definito in una classe di base ereditata indirettamente.</span><span class="sxs-lookup"><span data-stu-id="d4f40-149">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="d4f40-150">Affinché un riferimento qualificato da `MyBase` venga compilato correttamente, alcune classi di base devono contenere un metodo corrispondente al nome e ai tipi di parametri visualizzati nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="d4f40-150">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>

- <span data-ttu-id="d4f40-151">Non è possibile usare `MyBase` per chiamare i `MustOverride` metodi della classe di base.</span><span class="sxs-lookup"><span data-stu-id="d4f40-151">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>

- <span data-ttu-id="d4f40-152">`MyBase`non può essere usato per qualificarsi.</span><span class="sxs-lookup"><span data-stu-id="d4f40-152">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="d4f40-153">Pertanto, il codice seguente non è valido:</span><span class="sxs-lookup"><span data-stu-id="d4f40-153">Therefore, the following code is not valid:</span></span>

  `MyBase.MyBase.BtnOK_Click()`

- <span data-ttu-id="d4f40-154">`MyBase`non può essere usato nei moduli.</span><span class="sxs-lookup"><span data-stu-id="d4f40-154">`MyBase` cannot be used in modules.</span></span>

- <span data-ttu-id="d4f40-155">`MyBase`non può essere usato per accedere ai membri della classe base contrassegnati come `Friend` se la classe di base si trova in un assembly diverso.</span><span class="sxs-lookup"><span data-stu-id="d4f40-155">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>

<span data-ttu-id="d4f40-156">Per altre informazioni e un altro esempio, vedere [procedura: accedere a una variabile nascosta da una classe derivata](../declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="d4f40-156">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>

## <a name="the-myclass-keyword"></a><span data-ttu-id="d4f40-157">Parola chiave MyClass</span><span class="sxs-lookup"><span data-stu-id="d4f40-157">The MyClass Keyword</span></span>

<span data-ttu-id="d4f40-158">La `MyClass` parola chiave si comporta come una variabile oggetto che fa riferimento all'istanza corrente di una classe come implementata originariamente.</span><span class="sxs-lookup"><span data-stu-id="d4f40-158">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="d4f40-159">`MyClass`è simile a `Me` , ma ogni metodo e chiamata di proprietà su `MyClass` viene considerato come se il metodo o la proprietà fosse [NotOverridable](../../../language-reference/modifiers/notoverridable.md).</span><span class="sxs-lookup"><span data-stu-id="d4f40-159">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="d4f40-160">Pertanto, il metodo o la proprietà non sono interessati dall'override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="d4f40-160">Therefore, the method or property is not affected by overriding in a derived class.</span></span>

- <span data-ttu-id="d4f40-161">`MyClass`è una parola chiave, non un oggetto reale.</span><span class="sxs-lookup"><span data-stu-id="d4f40-161">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="d4f40-162">`MyClass`non può essere assegnato a una variabile, passato a procedure o utilizzato in un `Is` confronto.</span><span class="sxs-lookup"><span data-stu-id="d4f40-162">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>

- <span data-ttu-id="d4f40-163">`MyClass`si riferisce alla classe che lo contiene e ai relativi membri ereditati.</span><span class="sxs-lookup"><span data-stu-id="d4f40-163">`MyClass` refers to the containing class and its inherited members.</span></span>

- <span data-ttu-id="d4f40-164">`MyClass`può essere usato come qualificatore per `Shared` i membri.</span><span class="sxs-lookup"><span data-stu-id="d4f40-164">`MyClass` can be used as a qualifier for `Shared` members.</span></span>

- <span data-ttu-id="d4f40-165">`MyClass`non può essere usato all'interno di un `Shared` metodo, ma può essere usato all'interno di un metodo di istanza per accedere a un membro condiviso di una classe.</span><span class="sxs-lookup"><span data-stu-id="d4f40-165">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>

- <span data-ttu-id="d4f40-166">`MyClass`non può essere usato nei moduli standard.</span><span class="sxs-lookup"><span data-stu-id="d4f40-166">`MyClass` cannot be used in standard modules.</span></span>

- <span data-ttu-id="d4f40-167">`MyClass`può essere usato per qualificare un metodo definito in una classe di base e che non dispone di un'implementazione del metodo fornito in tale classe.</span><span class="sxs-lookup"><span data-stu-id="d4f40-167">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="d4f40-168">Un riferimento di questo tipo ha lo stesso significato di `MyBase.` *Method*.</span><span class="sxs-lookup"><span data-stu-id="d4f40-168">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>

<span data-ttu-id="d4f40-169">Nell'esempio seguente vengono confrontati `Me` e `MyClass` .</span><span class="sxs-lookup"><span data-stu-id="d4f40-169">The following example compares `Me` and `MyClass`.</span></span>

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

<span data-ttu-id="d4f40-170">Anche se `derivedClass` esegue l'override `testMethod` , la `MyClass` parola chiave in `useMyClass` Annulla gli effetti dell'override di e il compilatore risolve la chiamata alla versione della classe di base di `testMethod` .</span><span class="sxs-lookup"><span data-stu-id="d4f40-170">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4f40-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4f40-171">See also</span></span>

- [<span data-ttu-id="d4f40-172">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="d4f40-172">Inherits Statement</span></span>](../../../language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="d4f40-173">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="d4f40-173">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)

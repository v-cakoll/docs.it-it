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
ms.openlocfilehash: 89fcf2a14d8938d536aa72628218242811baa1a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400883"
---
# <a name="inheritance-basics-visual-basic"></a>Nozioni fondamentali sull'ereditarietà (Visual Basic)

L'istruzione `Inherits` viene utilizzata per dichiarare una nuova classe, denominata *classe derivata*, basata su una classe esistente, nota come *classe base*. Le classi derivate ereditano e possono estendere le proprietà, i metodi, gli eventi, i campi e le costanti definiti nella classe base. Nella sezione seguente vengono descritte alcune regole per l'ereditarietà e i modificatori che è possibile utilizzare per modificare il modo in cui le classi ereditano o vengono ereditate:

- Per impostazione predefinita, tutte le `NotInheritable` classi sono ereditabili a meno che non siano contrassegnate con la parola chiave . Le classi possono ereditare da altre classi nel progetto o da classi in altri assembly a cui fa riferimento il progetto.

- A differenza dei linguaggi che consentono l'ereditarietà multipla, Visual Basic consente solo l'ereditarietà singola nelle classi; vale a dire, le classi derivate possono avere una sola classe base. Sebbene l'ereditarietà multipla non sia consentita nelle classi, le classi possono implementare più interfacce, che possono effettivamente raggiungere gli stessi scopi.

- Per evitare l'esposizione di elementi con restrizioni in una classe base, il tipo di accesso di una classe derivata deve essere uguale o più restrittivo rispetto alla relativa classe base. Ad esempio, `Public` una classe `Friend` non `Private` può ereditare una o una classe e una `Friend` classe non può ereditare una `Private` classe.

## <a name="inheritance-modifiers"></a>Modificatori di ereditarietà

Visual Basic introduce le seguenti istruzioni a livello di classe e modificatori per supportare l'ereditarietà:

- `Inherits`statement - Specifica la classe base.

- `NotInheritable`modifier : impedisce ai programmatori di utilizzare la classe come classe base.

- `MustInherit`modificatore - Specifica che la classe deve essere utilizzata solo come classe base. Le `MustInherit` istanze delle classi non possono essere create direttamente; possono essere creati solo come istanze della classe base di una classe derivata. (Altri linguaggi di programmazione, ad esempio C , e C , utilizzare il termine *classe astratta* per descrivere una classe di questo tipo.)

## <a name="overriding-properties-and-methods-in-derived-classes"></a>Override di proprietà e metodi nelle classi derivate

Per impostazione predefinita, una classe derivata eredita proprietà e metodi dalla relativa classe base. Se una proprietà o un metodo ereditato deve comportarsi in modo diverso nella classe derivata, è possibile *eseguire l'override*di . Ovvero, è possibile definire una nuova implementazione del metodo nella classe derivata. I seguenti modificatori consentono di controllare le modalità di override di proprietà e metodi:

- `Overridable`: consente di eseguire l'override di una proprietà o di un metodo in una classe in una classe derivata.

- `Overrides`: esegue `Overridable` l'override di una proprietà o di un metodo definito nella classe base.

- `NotOverridable`: impedisce l'override di una proprietà o di un metodo in una classe che eredita. Per impostazione `Public` `NotOverridable`predefinita, i metodi sono .

- `MustOverride`È necessario che una classe derivata eseda la proprietà o il metodo. Quando `MustOverride` viene utilizzata la parola chiave, `Sub`la `Function`definizione del metodo è costituita solo dall'istruzione , , `Property` o . Non sono ammesse altre dichiarazioni, `End Sub` `End Function` e in particolare non esiste né istruzione. `MustOverride`i metodi devono `MustInherit` essere dichiarati nelle classi.

Si supponga di voler definire le classi per la gestione delle retribuzioni. È possibile definire `Payroll` una classe `RunPayroll` generica che contiene un metodo che calcola le retribuzioni per una settimana tipica. È quindi `Payroll` possibile utilizzare come classe `BonusPayroll` di base per una classe più specializzata, che potrebbe essere utilizzata quando si distribuisce bonus per i dipendenti.

La `BonusPayroll` classe può ereditare `PayEmployee` ed eseguire l'override del metodo definito nella classe base. `Payroll`

Nell'esempio riportato di `Payroll,` seguito vengono definite `BonusPayroll`una classe base e `PayEmployee`una classe derivata, , che esegue l'override di un metodo ereditato, . Una `RunPayroll`routine, , crea `Payroll` e quindi `BonusPayroll` passa un `Pay`oggetto e un `PayEmployee` oggetto a una funzione che esegue il metodo di entrambi gli oggetti.

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a>La parola chiave MyBase

La `MyBase` parola chiave si comporta come una variabile oggetto che fa riferimento alla classe base dell'istanza corrente di una classe. `MyBase`viene spesso utilizzato per accedere ai membri della classe base sottoposti a override o sottoposti a shadowing in una classe derivata. In particolare, `MyBase.New` viene utilizzato per chiamare in modo esplicito un costruttore di classe base da un costruttore di classi derivate.

Si supponga, ad esempio, di progettare una classe derivata che esegue l'override di un metodo ereditato dalla classe base. Il metodo sottoposto a override può chiamare il metodo nella classe base e modificare il valore restituito come illustrato nel frammento di codice seguente:The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

Nell'elenco seguente vengono descritte le restrizioni relative all'utilizzo: `MyBase`

- `MyBase`fa riferimento alla classe base immediata e ai relativi membri ereditati. Non può essere `Private` utilizzato per accedere ai membri della classe.

- `MyBase`è una parola chiave, non un oggetto reale. `MyBase`non può essere assegnato a una variabile, `Is` passato alle procedure o utilizzato in un confronto.

- Il metodo `MyBase` che si qualifica non deve essere definito nella classe base immediata; può invece essere definito in una classe base ereditata indirettamente. Affinché un riferimento `MyBase` qualificato da compilare correttamente, una classe di base deve contenere un metodo corrispondente al nome e tipi di parametri visualizzati nella chiamata.

- Non è `MyBase` possibile `MustOverride` utilizzare per chiamare i metodi della classe base.

- `MyBase`non può essere utilizzato per qualificarsi. Pertanto, il codice seguente non è valido:Therefore, the following code is not valid:

  `MyBase.MyBase.BtnOK_Click()`

- `MyBase`non può essere utilizzato nei moduli.

- `MyBase`non può essere utilizzato per accedere `Friend` ai membri della classe base contrassegnati come se la classe base si trovasse in un assembly diverso.

Per ulteriori informazioni e un altro esempio, vedere [Procedura: accedere a una variabile nascosta da una classe derivata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).

## <a name="the-myclass-keyword"></a>La parola chiave MyClass

La `MyClass` parola chiave si comporta come una variabile oggetto che fa riferimento all'istanza corrente di una classe come originariamente implementato. `MyClass`è `Me`simile a , ma `MyClass` ogni chiamata al metodo e alla proprietà su viene considerata come se il metodo o la proprietà fosse [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md). Pertanto, il metodo o la proprietà non è interessato dall'override in una classe derivata.

- `MyClass`è una parola chiave, non un oggetto reale. `MyClass`non può essere assegnato a una variabile, `Is` passato alle procedure o utilizzato in un confronto.

- `MyClass`fa riferimento alla classe contenitore e ai relativi membri ereditati.

- `MyClass`può essere utilizzato come `Shared` qualificatore per i membri.

- `MyClass`non può essere `Shared` utilizzato all'interno di un metodo, ma può essere utilizzato all'interno di un metodo di istanza per accedere a un membro condiviso di una classe.

- `MyClass`non può essere utilizzato nei moduli standard.

- `MyClass`può essere utilizzato per qualificare un metodo definito in una classe base e che non dispone di alcuna implementazione del metodo fornito in tale classe. Tale riferimento ha lo `MyBase.`stesso significato di *Method*.

Nell'esempio riportato di seguito vengono confrontati `Me` e `MyClass`.

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

Anche `derivedClass` se `testMethod`esegue `MyClass` l'override di , la parola chiave in `useMyClass` annulla gli effetti dell'override e il compilatore risolve la chiamata alla versione della classe base di `testMethod`.

## <a name="see-also"></a>Vedere anche

- [Istruzione Inherits](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)

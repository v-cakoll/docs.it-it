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
ms.openlocfilehash: 8a75b75ef9acb4c89f4c7d05f1410d4ca70e680b
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582752"
---
# <a name="inheritance-basics-visual-basic"></a>Nozioni fondamentali sull'ereditarietà (Visual Basic)

L'istruzione `Inherits` viene utilizzata per dichiarare una nuova classe, denominata *classe derivata*, basata su una classe esistente, nota come classe di *base*. Le classi derivate ereditano e possono estendere, le proprietà, i metodi, gli eventi, i campi e le costanti definiti nella classe di base. Nella sezione seguente vengono descritte alcune delle regole per l'ereditarietà e i modificatori che è possibile utilizzare per modificare il modo in cui le classi ereditano o vengono ereditate:

- Per impostazione predefinita, tutte le classi sono ereditabili, a meno che non siano contrassegnate con la parola chiave `NotInheritable`. Le classi possono ereditare da altre classi nel progetto o da classi di altri assembly a cui fa riferimento il progetto.

- Diversamente dalle lingue che consentono l'ereditarietà multipla, Visual Basic consente solo l'ereditarietà singola nelle classi; ovvero, le classi derivate possono avere una sola classe di base. Sebbene l'ereditarietà multipla non sia consentita nelle classi, le classi possono implementare più interfacce, che possono raggiungere le stesse entità finali.

- Per impedire l'esposizione di elementi con restrizioni in una classe base, il tipo di accesso di una classe derivata deve essere uguale o più restrittivo rispetto alla relativa classe di base. Una classe `Public`, ad esempio, non può ereditare una classe `Friend` o `Private` e una classe `Friend` non può ereditare una classe `Private`.

## <a name="inheritance-modifiers"></a>Modificatori di ereditarietà

Visual Basic introduce le istruzioni e i modificatori a livello di classe seguenti per supportare l'ereditarietà:

- `Inherits` Statement-specifica la classe base.

- modificatore `NotInheritable`: impedisce ai programmatori di usare la classe come classe di base.

- `MustInherit` modificatore — specifica che la classe deve essere usata solo come classe base. Non è possibile creare direttamente istanze delle classi `MustInherit`. possono essere creati solo come istanze della classe di base di una classe derivata. (Altri linguaggi di programmazione, ad C++ esempio C#e, usano il termine *classe astratta* per descrivere tale classe).

## <a name="overriding-properties-and-methods-in-derived-classes"></a>Override di proprietà e metodi nelle classi derivate

Per impostazione predefinita, una classe derivata eredita proprietà e metodi dalla relativa classe di base. Se una proprietà o un metodo ereditato deve comportarsi in modo diverso nella classe derivata, è possibile eseguirne l' *override*. Ovvero, è possibile definire una nuova implementazione del metodo nella classe derivata. I seguenti modificatori consentono di controllare le modalità di override di proprietà e metodi:

- `Overridable` — consente di eseguire l'override di una proprietà o di un metodo in una classe in una classe derivata.

- `Overrides`: esegue l'override di una proprietà o di un metodo `Overridable` definito nella classe di base.

- `NotOverridable`: impedisce l'override di una proprietà o di un metodo in una classe che eredita. Per impostazione predefinita, `Public` metodi vengono `NotOverridable`.

- `MustOverride`: richiede che una classe derivata esegua l'override della proprietà o del metodo. Quando si usa la parola chiave `MustOverride`, la definizione del metodo è costituita solo dall'istruzione `Sub`, `Function` o `Property`. Non sono consentite altre istruzioni e, in particolare, non esiste alcuna istruzione `End Sub` o `End Function`. `MustOverride` metodi devono essere dichiarati nelle classi `MustInherit`.

Si supponga di voler definire le classi per gestire le retribuzioni. È possibile definire una classe `Payroll` generica che contiene un metodo `RunPayroll` che calcola il libro paga per una settimana tipica. È quindi possibile usare `Payroll` come classe di base per una classe `BonusPayroll` più specializzata, che può essere usata quando si distribuiscono i bonus dei dipendenti.

La classe `BonusPayroll` può ereditare ed eseguire l'override del metodo `PayEmployee` definito nella classe `Payroll` di base.

Nell'esempio seguente viene definita una classe base, `Payroll,` e una classe derivata, `BonusPayroll`, che esegue l'override di un metodo ereditato, `PayEmployee`. Una procedura, `RunPayroll`, crea e quindi passa un oggetto `Payroll` e un oggetto `BonusPayroll` a una funzione, `Pay`, che esegue il metodo `PayEmployee` di entrambi gli oggetti.

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a>Parola chiave MyBase

La parola chiave `MyBase` si comporta come una variabile oggetto che fa riferimento alla classe di base dell'istanza corrente di una classe. `MyBase` viene spesso usata per accedere ai membri della classe di base sottoposti a override o nascosti in una classe derivata. In particolare, `MyBase.New` viene usato per chiamare in modo esplicito un costruttore della classe base da un costruttore di classe derivata.

Si supponga, ad esempio, di progettare una classe derivata che esegue l'override di un metodo ereditato dalla classe base. Il metodo sottoposto a override può chiamare il metodo nella classe base e modificare il valore restituito come illustrato nel frammento di codice seguente:

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

Nell'elenco seguente vengono descritte le restrizioni relative all'utilizzo di `MyBase`:

- `MyBase` si riferisce alla classe di base immediata e ai relativi membri ereditati. Non può essere usato per accedere ai membri `Private` nella classe.

- `MyBase` è una parola chiave, non un oggetto reale. non è possibile assegnare `MyBase` a una variabile, passata a procedure o utilizzata in un confronto di `Is`.

- Il metodo che `MyBase` qualifica non deve essere definito nella classe di base immediata; può invece essere definito in una classe di base ereditata indirettamente. Affinché un riferimento qualificato da `MyBase` venga compilato correttamente, alcune classi di base devono contenere un metodo che corrisponda al nome e ai tipi di parametri visualizzati nella chiamata.

- Non è possibile usare `MyBase` per chiamare `MustOverride` metodi della classe di base.

- non è possibile usare `MyBase` per qualificarsi. Pertanto, il codice seguente non è valido:

  `MyBase.MyBase.BtnOK_Click()`

- non è possibile usare `MyBase` nei moduli.

- non è possibile usare `MyBase` per accedere ai membri della classe base contrassegnati come `Friend` se la classe base si trova in un assembly diverso.

Per altre informazioni e un altro esempio, vedere [procedura: accedere a una variabile nascosta da una classe derivata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).

## <a name="the-myclass-keyword"></a>Parola chiave MyClass

La parola chiave `MyClass` si comporta come una variabile oggetto che fa riferimento all'istanza corrente di una classe come implementata originariamente. `MyClass` è simile a `Me`, ma tutte le chiamate al metodo e alla proprietà su `MyClass` vengono considerate come se il metodo o la proprietà fosse [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md). Pertanto, il metodo o la proprietà non sono interessati dall'override in una classe derivata.

- `MyClass` è una parola chiave, non un oggetto reale. non è possibile assegnare `MyClass` a una variabile, passata a procedure o utilizzata in un confronto di `Is`.

- `MyClass` si riferisce alla classe che lo contiene e ai relativi membri ereditati.

- `MyClass` può essere usato come qualificatore per `Shared` membri.

- non è possibile usare `MyClass` all'interno di un metodo di `Shared`, ma è possibile usarlo all'interno di un metodo di istanza per accedere a un membro condiviso di una classe.

- non è possibile usare `MyClass` nei moduli standard.

- `MyClass` può essere utilizzato per qualificare un metodo definito in una classe di base e che non dispone di un'implementazione del metodo fornito in tale classe. Un riferimento di questo tipo ha lo stesso significato di `MyBase.`*Metodo*.

Nell'esempio seguente vengono confrontati `Me` e `MyClass`.

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

Anche se `derivedClass` esegue l'override di `testMethod`, la parola chiave `MyClass` in `useMyClass` Annulla gli effetti dell'override di e il compilatore risolve la chiamata alla versione della classe di base di `testMethod`.

## <a name="see-also"></a>Vedere anche

- [Istruzione Inherits](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)

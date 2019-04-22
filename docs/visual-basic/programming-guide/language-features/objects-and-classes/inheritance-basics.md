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
ms.openlocfilehash: 5e4b8511145e758bf3d6328141be0e526965dccf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58826574"
---
# <a name="inheritance-basics-visual-basic"></a>Nozioni fondamentali sull'ereditarietà (Visual Basic)
Il `Inherits` istruzione viene usata per dichiarare una nuova classe, denominata un *classe derivata*, in base a una classe esistente, nota come un *classe di base*. Le classi derivate ereditano e possono estendere, proprietà, metodi, eventi, campi e le costanti definite nella classe di base. La sezione seguente descrive alcune delle regole per l'ereditarietà e i modificatori che è possibile usare per modificare le classi modo ereditano o vengono ereditati:  
  
-   Per impostazione predefinita, tutte le classi sono ereditabili a meno che non contrassegnato con il `NotInheritable` (parola chiave). Le classi possono ereditare da altre classi nel progetto o dalle classi in altri assembly che fa riferimento il progetto.  
  
-   Diversamente dai linguaggi che consentono l'ereditarietà multipla, Visual Basic consente solo l'ereditarietà singola nelle classi. ovvero le classi derivate possono avere una sola classe base. Anche se non è consentito nelle classi di ereditarietà multipla, le classi possono implementare più interfacce di cui è possono eseguire in modo efficace la stessa funzione.  
  
-   Per evitare l'esposizione agli elementi in una classe base, il tipo di accesso di una classe derivata deve essere uguale o più restrittivo alla classe di base. Ad esempio, un `Public` classe non può ereditare un `Friend` o una `Private` (classe) e un `Friend` classe non può ereditare un `Private` classe.  
  
## <a name="inheritance-modifiers"></a>Modificatori di ereditarietà  
 Visual Basic introduce le istruzioni a livello di classe e i modificatori per il supporto dell'ereditarietà:  
  
-   `Inherits` istruzione: specifica la classe di base.  
  
-   `NotInheritable` modificatore, ovvero per impedire ai programmatori di utilizzo della classe come classe di base.  
  
-   `MustInherit` modificatore: Specifica che la classe deve essere utilizzato come classe di base. Le istanze di `MustInherit` classi non possono essere create direttamente; possono solo essere create istanze della classe di base di una classe derivata. (Altri linguaggi di programmazione, ad esempio C++ e C#, viene usato il termine *classe astratta* per descrivere una classe di questo tipo.)  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a>Override di proprietà e metodi nelle classi derivate  
 Per impostazione predefinita, una classe derivata eredita le proprietà e metodi della classe base. Se un metodo o proprietà ereditata deve comportarsi in modo diverso nella classe derivata può risultare *sottoposto a override*. Vale a dire, è possibile definire una nuova implementazione del metodo nella classe derivata. I seguenti modificatori consentono di controllare le modalità di override di proprietà e metodi:  
  
-   `Overridable` : Consente a una proprietà o metodo in una classe per eseguire l'override in una classe derivata.  
  
-   `Overrides` : Esegue l'override di un `Overridable` proprietà o un metodo definito nella classe di base.  
  
-   `NotOverridable` -Impedisce una proprietà o metodo da sottoporre a override in una classe che eredita. Per impostazione predefinita `Public` sono metodi `NotOverridable`.  
  
-   `MustOverride` : Richiede che una classe derivata eseguono l'override di proprietà o metodo. Quando la `MustOverride` parola chiave viene usata, la definizione del metodo è costituito solo il `Sub`, `Function`, o `Property` istruzione. Le altre istruzioni non sono consentiti e in particolare è presente alcun `End Sub` o `End Function` istruzione. `MustOverride` i metodi devono essere dichiarati `MustInherit` classi.  
  
 Si supponga di che voler definire classi per la gestione delle retribuzioni. È possibile definire un oggetto generico `Payroll` classe che contiene un `RunPayroll` metodo che calcola retribuzioni per una settimana tipica. È quindi possibile usare `Payroll` come classe di base per una più specializzati `BonusPayroll` (classe), che potrebbe essere usati quando si distribuiscono bonus ai dipendenti.  
  
 Il `BonusPayroll` classe può ereditare ed eseguire l'override, il `PayEmployee` metodo definito nella base `Payroll` classe.  
  
 L'esempio seguente definisce una classe di base `Payroll,` e una classe derivata `BonusPayroll`, che esegue l'override di un metodo ereditato, `PayEmployee`. Una routine, `RunPayroll`, viene creato e quindi passa un `Payroll` oggetto e un `BonusPayroll` oggetto a una funzione `Pay`, che esegue il `PayEmployee` metodo di entrambi gli oggetti.  
  
 [!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]  
  
## <a name="the-mybase-keyword"></a>La parola chiave MyBase  
 Il `MyBase` (parola chiave) si comporta come una variabile oggetto che fa riferimento alla classe di base dell'istanza corrente di una classe. `MyBase` viene spesso utilizzato per accedere ai membri di classe base sottoposto a override o shadowing in una classe derivata. In particolare, `MyBase.New` viene usato per chiamare in modo esplicito un costruttore di classe di base da un costruttore di classe derivata.  
  
 Si supponga, ad esempio, che si progetta una classe derivata che esegue l'override di un metodo ereditato dalla classe di base. Il metodo sottoposto a override è possibile chiamare il metodo nella classe di base e modificare il valore restituito, come illustrato nel frammento di codice seguente:  
  
 [!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]  
  
 L'elenco seguente descrive le restrizioni sull'uso di `MyBase`:  
  
-   `MyBase` fa riferimento alla classe di base immediata e i relativi membri ereditati. Non può essere usato per accedere a `Private` membri della classe.  
  
-   `MyBase` è una parola chiave, non un oggetto reale. `MyBase` non può essere assegnato a una variabile, passati alle procedure o usato in un `Is` confronto.  
  
-   Il metodo che `MyBase` qualifica non deve essere definito nella classe di base immediata; può invece essere definito in una classe di base ereditata indirettamente. Affinché un riferimento qualificato da `MyBase` venga compilato correttamente, una classe di base deve contenere un metodo corrispondente al nome e i tipi di parametri che vengono visualizzati nella chiamata.  
  
-   Non è possibile usare `MyBase` chiamare `MustOverride` metodi della classe di base.  
  
-   `MyBase` non può essere utilizzato per qualificare stesso. Pertanto, il codice seguente non è valido:  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   `MyBase` non è utilizzabile nei moduli.  
  
-   `MyBase` non può essere usato per accedere ai membri di classe di base che sono contrassegnati come `Friend` se la classe di base si trova in un assembly diverso.  
  
 Per altre informazioni e un altro esempio, vedere [come: Accedere a una variabile nascosta da una classe derivata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
## <a name="the-myclass-keyword"></a>La parola chiave MyClass  
 Il `MyClass` (parola chiave) si comporta come una variabile oggetto che fa riferimento all'istanza corrente di una classe come implementata originariamente. `MyClass` è simile a `Me`, ma tutti i metodi e proprietà in una chiamata `MyClass` viene trattato come se il metodo o proprietà fosse [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md). Pertanto, il metodo o proprietà non è influenzata viene sottoposto a override in una classe derivata.  
  
-   `MyClass` è una parola chiave, non un oggetto reale. `MyClass` non può essere assegnato a una variabile, passati alle procedure o usato in un `Is` confronto.  
  
-   `MyClass` fa riferimento alla classe che lo contiene e i relativi membri ereditati.  
  
-   `MyClass` può essere usato come qualificatore per `Shared` membri.  
  
-   `MyClass` non può essere utilizzato all'interno di un `Shared` (metodo), ma può essere usato all'interno di un metodo di istanza per accedere a un membro condiviso di una classe.  
  
-   `MyClass` non può essere utilizzata nei moduli standard.  
  
-   `MyClass` può essere utilizzata per qualificare un metodo definito in una classe di base e che non ha un'implementazione del metodo specificato in tale classe. Tale riferimento ha lo stesso significato di `MyBase.` *metodo*.  
  
 Nell'esempio seguente vengono confrontate `Me` e `MyClass`.  
  
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
  
 Sebbene `derivedClass` esegue l'override `testMethod`, il `MyClass` parola chiave nel `useMyClass` Annulla gli effetti dell'esecuzione dell'override e i compilatore risolve la chiamata a quella classe di base di `testMethod`.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Inherits](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)

---
title: "Nozioni fondamentali sull'ereditarietà (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
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
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76813bb36c0bcf75791932a0fec081f0fc1958e3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="inheritance-basics-visual-basic"></a>Nozioni fondamentali sull'ereditarietà (Visual Basic)
Il `Inherits` istruzione viene utilizzata per dichiarare una nuova classe, denominata un *derivata*, in base a una classe esistente, nota come un *classe di base*. Le classi derivate ereditano e possono estendere, proprietà, metodi, eventi, campi e costanti definite nella classe base. Nella sezione seguente vengono descritte alcune delle regole per l'ereditarietà e i modificatori che è possibile utilizzare per modificare le classi modo ereditano o sono ereditati:  
  
-   Per impostazione predefinita, tutte le classi sono ereditabili a meno che non contrassegnato con il `NotInheritable` (parola chiave). Le classi possono ereditare da altre classi nel progetto o dalle classi in altri assembly che fa riferimento il progetto.  
  
-   A differenza dei linguaggi che consentono l'ereditarietà multipla, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] consente solo singole ereditarietà nelle classi; ovvero le classi derivate possono avere solo una classe base. Sebbene l'ereditarietà multipla non è consentita nelle classi, le classi possono implementare più interfacce, che possono raggiungere la stessa funzione.  
  
-   Per evitare l'esposizione agli elementi in una classe base, il tipo di accesso di una classe derivata deve essere uguale o più restrittivo di quello della classe base. Ad esempio, un `Public` classe non può ereditare un `Friend` o `Private` (classe) e un `Friend` classe non può ereditare un `Private` classe.  
  
## <a name="inheritance-modifiers"></a>Modificatori di ereditarietà  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]introduce le istruzioni a livello di classe e i modificatori per supportare l'ereditarietà:  
  
-   `Inherits`istruzione: specifica la classe base.  
  
-   `NotInheritable`modificatore-impedisce ai programmatori di utilizzo della classe come classe base.  
  
-   `MustInherit`modificatore: Specifica che la classe deve essere utilizzato come classe di base. Le istanze di `MustInherit` le classi non possono essere create direttamente; essi possono essere creati solo istanze della classe di base di una classe derivata. (Altri linguaggi di programmazione, ad esempio C++ e c#, usano il termine *classe astratta* per descrivere una classe.)  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a>Override di proprietà e metodi nelle classi derivate  
 Per impostazione predefinita, una classe derivata eredita le proprietà e metodi della classe base. Se una proprietà o metodo ha un comportamento diverso nella classe derivata può essere *sottoposto a override*. Ovvero, è possibile definire una nuova implementazione del metodo nella classe derivata. I seguenti modificatori consentono di controllare le modalità di override di proprietà e metodi:  
  
-   `Overridable`-Consente di una proprietà o metodo in una classe per eseguire l'override in una classe derivata.  
  
-   `Overrides`: Esegue l'override di un `Overridable` proprietà o un metodo definito nella classe di base.  
  
-   `NotOverridable`-Impedisce una proprietà o un metodo viene sottoposto a override in una classe che eredita. Per impostazione predefinita, `Public` metodi sono `NotOverridable`.  
  
-   `MustOverride`: Richiede che una classe derivata esegue l'override di proprietà o metodo. Quando il `MustOverride` parola chiave viene utilizzata, la definizione del metodo è costituita solo il `Sub`, `Function`, o `Property` istruzione. Le altre istruzioni non sono consentite in modo specifico, non `End Sub` o `End Function` istruzione. `MustOverride`i metodi devono essere dichiarati in `MustInherit` classi.  
  
 Si supponga che si desidera definire le classi per la gestione delle retribuzioni. È possibile definire un oggetto generico `Payroll` classe che contiene un `RunPayroll` metodo che calcola retribuzioni di una settimana tipica. È quindi possibile utilizzare `Payroll` come classe base per una più specializzato `BonusPayroll` (classe), che potrebbe essere usate quando si distribuiscono bonus ai dipendenti.  
  
 Il `BonusPayroll` classe può ereditare ed eseguire l'override, il `PayEmployee` metodo definito nella base `Payroll` classe.  
  
 L'esempio seguente definisce una classe base, `Payroll,` e una classe derivata, `BonusPayroll`, che esegue l'override di un metodo ereditato, `PayEmployee`. Una routine, `RunPayroll`, crea e passa quindi un `Payroll` oggetto e un `BonusPayroll` oggetto a una funzione, `Pay`, che viene eseguita la `PayEmployee` metodo di entrambi gli oggetti.  
  
 [!code-vb[VbVbalrOOP#28](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]  
  
## <a name="the-mybase-keyword"></a>La parola chiave MyBase  
 Il `MyBase` (parola chiave) si comporta come una variabile oggetto che fa riferimento alla classe di base dell'istanza corrente di una classe. `MyBase`viene spesso utilizzato per accedere ai membri di classe di base che vengono sottoposti a override o shadowing in una classe derivata. In particolare, `MyBase.New` viene utilizzata per chiamare in modo esplicito un costruttore di classe di base da un costruttore di classe derivata.  
  
 Si supponga, ad esempio, che si progetta una classe derivata che esegue l'override di un metodo ereditato dalla classe di base. Il metodo sottoposto a override è possibile chiamare il metodo nella classe base e modificare il valore restituito, come illustrato nel frammento di codice seguente:  
  
 [!code-vb[VbVbalrOOP#109](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]  
  
 Nell'elenco seguente descrive le restrizioni sull'utilizzo di `MyBase`:  
  
-   `MyBase`fa riferimento alla classe base immediata e i relativi membri ereditati. Non può essere utilizzato per accedere a `Private` membri della classe.  
  
-   `MyBase`è una parola chiave, non un oggetto reale. `MyBase`non è assegnato a una variabile, passare alle procedure o utilizzato un `Is` confronto.  
  
-   Il metodo che `MyBase` qualifica non deve essere definito nella classe base immediata; potrebbe invece essere definita in una classe di base ereditata indirettamente. Affinché un riferimento qualificato da `MyBase` venga compilato correttamente, una classe di base deve contenere un metodo corrispondente al nome e i tipi di parametri presenti nella chiamata.  
  
-   Non è possibile utilizzare `MyBase` chiamare `MustOverride` metodi della classe di base.  
  
-   `MyBase`non può essere utilizzato per qualificare se stesso. Pertanto, il codice seguente non è valido:  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   `MyBase`non può essere utilizzata nei moduli.  
  
-   `MyBase`non può essere utilizzato per accedere ai membri di classe di base che sono contrassegnati come `Friend` se la classe di base si trova in un assembly diverso.  
  
 Per ulteriori informazioni e un altro esempio, vedere [procedura: accedere a una variabile nascosta da una classe derivata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
## <a name="the-myclass-keyword"></a>La parola chiave MyClass  
 Il `MyClass` (parola chiave) si comporta come una variabile oggetto che fa riferimento all'istanza corrente di una classe come implementata originariamente. `MyClass`è simile a `Me`, ma ogni metodo e proprietà chiamare su `MyClass` viene trattato come se fosse il metodo o proprietà [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md). Pertanto, il metodo o proprietà non è interessata eseguendo l'override in una classe derivata.  
  
-   `MyClass`è una parola chiave, non un oggetto reale. `MyClass`non è assegnato a una variabile, passare alle procedure o utilizzato un `Is` confronto.  
  
-   `MyClass`fa riferimento alla classe contenitore e i relativi membri ereditati.  
  
-   `MyClass`può essere utilizzato come qualificatore per `Shared` membri.  
  
-   `MyClass`non può essere utilizzato all'interno di un `Shared` (metodo), ma può essere utilizzato all'interno di un metodo di istanza per accedere a un membro di una classe condiviso.  
  
-   `MyClass`non può essere utilizzata nei moduli standard.  
  
-   `MyClass`può essere utilizzato per qualificare un metodo definito in una classe base e che non ha un'implementazione del metodo specificato in tale classe. Questo riferimento ha lo stesso significato di `MyBase.` *metodo*.  
  
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
  
 Anche se `derivedClass` esegue l'override `testMethod`, `MyClass` parola chiave in `useMyClass` Annulla gli effetti dell'override e i compilatore consente di risolvere la chiamata per la versione della classe base `testMethod`.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Inherits](../../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [Me, My, MyBase e MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)

---
title: Riferimenti a elementi dichiarati (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: 16f4fb28ab030ccebed2a8d1b93a3a6c29d075c6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501256"
---
# <a name="references-to-declared-elements-visual-basic"></a>Riferimenti a elementi dichiarati (Visual Basic)
Quando il codice fa riferimento a un elemento dichiarato, il compilatore Visual Basic corrisponde al nome nel riferimento alla dichiarazione appropriata di tale nome. Se più di un elemento viene dichiarato con lo stesso nome, è possibile controllare quale di questi elementi è a cui fa riferimento *qualificazione* il relativo nome.  
  
 Il compilatore tenta di ottenere un riferimento a una dichiarazione del nome e il *ambito più ristretto*. Ciò significa inizia con il creazione del riferimento del codice e procede verso l'esterno attraverso livelli successivi di contenente gli elementi.  
  
 Nell'esempio seguente mostra i riferimenti a due variabili con lo stesso nome. Nell'esempio vengono dichiarate due variabili, ogni colonna nome `totalCount`, a diversi livelli di ambito nel modulo `container`. Quando la procedura `showCount` consente di visualizzare `totalCount` senza qualifica, il compilatore Visual Basic si risolve il riferimento alla dichiarazione con ambito più ristretto, vale a dire la dichiarazione locale all'interno `showCount`. Quando qualifica `totalCount` con il modulo contenente `container`, il compilatore risolve il riferimento alla dichiarazione con ambito più ampio.  
  
```vb  
' Assume these two modules are both in the same assembly.  
Module container  
    Public totalCount As Integer = 1  
    Public Sub showCount()  
        Dim totalCount As Integer = 6000  
        ' The following statement displays the local totalCount (6000).  
        MsgBox("Unqualified totalCount is " & CStr(totalCount))  
        ' The following statement displays the module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
Module callingModule  
    Public Sub displayCount()  
        container.showCount()  
        ' The following statement displays the containing module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
```  
  
## <a name="qualifying-an-element-name"></a>Un nome di elemento di qualificazione  
 Se si desidera eseguire l'override di questo processo di ricerca e specificare un nome dichiarato in un ambito più ampio, è necessario *qualificare* al nome dell'elemento contenitore dell'ambito più ampio. In alcuni casi, potrebbe anche dover qualificare l'elemento che lo contiene.  
  
 Qualificare un nome significa che lo precede nell'istruzione del codice sorgente con le informazioni che identificano in cui è definito l'elemento di destinazione. Queste informazioni viene chiamate un *stringa di qualificazione*. Può includere uno o più spazi dei nomi e un modulo, classe o una struttura.  
  
 La stringa di qualificazione necessario specificare in modo non ambiguo il modulo, classe o struttura che contiene l'elemento di destinazione. Il contenitore a loro volta potrebbe trovarsi in un altro elemento che lo contiene, in genere uno spazio dei nomi. Potrebbe essere necessario includere gli elementi che lo contiene diversi nella stringa di qualificazione.  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a>Per accedere a un elemento dichiarato dal relativo nome completo della classe  
  
1.  Determinare il percorso in cui è stato definito l'elemento. Potrebbe trattarsi di uno spazio dei nomi o anche una gerarchia di spazi dei nomi. Nello spazio dei nomi di livello più basso, l'elemento deve essere incluso in un modulo, classe o struttura.  
  
    ```vb  
    ' Assume the following hierarchy exists outside your code.  
    Namespace outerSpace  
        Namespace innerSpace  
            Module holdsTotals  
                Public Structure totals  
                    Public thisTotal As Integer  
                    Public Shared grandTotal As Long  
                End Structure  
            End Module  
        End Namespace  
    End Namespace  
    ```  
  
2.  Determinare il percorso di qualificazione in base alla posizione dell'elemento di destinazione. Iniziare con lo spazio dei nomi di livello più alto, procedere con lo spazio dei nomi di livello più basso e terminare con il modulo, classe o struttura che contiene l'elemento di destinazione. Ogni elemento nel percorso deve contenere l'elemento che lo segue.  
  
     `outerSpace` → `innerSpace` → `holdsTotals` → `totals`  
  
3.  Preparare la stringa di qualificazione per l'elemento di destinazione. Inserire un punto (`.`) dopo ogni elemento nel percorso. L'applicazione deve avere accesso a ogni elemento nella stringa di qualificazione.  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4.  Scrivere l'espressione o istruzione di assegnazione che fa riferimento all'elemento di destinazione in modo normale.  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5.  Anteporre al nome di elemento di destinazione con la stringa di qualificazione. Il nome deve seguire immediatamente il punto (`.`) che segue il modulo, classe o struttura che contiene l'elemento.  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6.  Il compilatore Usa la stringa di qualificazione per individuare una dichiarazione di non crittografata e non ambigua a cui può trovare il riferimento all'elemento di destinazione.  
  
 Potrebbe anche essere necessario qualificare un riferimento al nome, se l'applicazione può accedere a più di un elemento di programmazione che ha lo stesso nome. Ad esempio, il <xref:System.Windows.Forms> e <xref:System.Web.UI.WebControls> spazi dei nomi di entrambi contengono una `Label` classe (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> e <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>). Se l'applicazione Usa entrambi o se definisce il proprio `Label` (classe), è necessario distinguere i diversi `Label` oggetti. Includere l'alias di importazione o dello spazio dei nomi nella dichiarazione di variabile. Nell'esempio seguente usa l'alias di importazione.  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a>Membri di altri elementi contenitore  
 Quando si usa un membro non condiviso di un'altra classe o struttura, è innanzitutto necessario qualificare il nome del membro con una variabile o espressione che punti a un'istanza della classe o struttura. Nell'esempio riportato di seguito `demoClass` è un'istanza di una classe denominata `class1`.  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 È possibile usare il nome della classe per qualificare un membro che non è [condiviso](../../../../visual-basic/language-reference/modifiers/shared.md). È innanzitutto necessario creare un'istanza in una variabile oggetto (in questo caso `demoClass`) e quindi farvi riferimento tramite il nome della variabile.  
  
 Se una classe o struttura ha un `Shared` membro, è possibile qualificare il membro con il nome di classe o struttura o con una variabile o espressione che punti a un'istanza.  
  
 Un modulo non dispone di tutte le istanze separate e tutti i relativi membri sono `Shared` per impostazione predefinita. Pertanto, qualificare un membro del modulo con il nome del modulo.  
  
 Nell'esempio seguente mostra riferimenti qualificati a procedure di membri di modulo. Nell'esempio viene dichiarata due `Sub` procedure, entrambi denominati `perform`, in moduli diversi in un progetto. Ciascuna di esse può essere specificato senza qualifica all'interno di un proprio modulo ma deve essere completo se viene fatto riferimento da qualsiasi altra posizione. Perché fa riferimento l'elemento finale nel `module3` non soddisfa i requisiti `perform`, il compilatore non è possibile risolvere il riferimento.  
  
```vb  
' Assume these three modules are all in the same assembly.  
Module module1  
    Public Sub perform()  
        MsgBox("module1.perform() now returning")  
    End Sub  
End Module  
Module module2  
    Public Sub perform()  
        MsgBox("module2.perform() now returning")  
    End Sub  
    Public Sub doSomething()  
        ' The following statement calls perform in module2, the active module.  
        perform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
    End Sub  
End Module  
Module module3  
    Public Sub callPerform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
        ' The following statement makes an unresolvable name reference  
        ' and therefore generates a COMPILER ERROR.  
        perform() ' INVALID statement  
    End Sub  
End Module  
```  
  
## <a name="references-to-projects"></a>Riferimenti a progetti  
 Per usare [pubblici](../../../../visual-basic/language-reference/modifiers/public.md) gli elementi definiti in un altro progetto, è innanzitutto necessario impostare un *riferimento* per quel progetto assembly o libreria dei tipi. Per impostare un riferimento, fare clic su **Aggiungi riferimento** nel **progetto** menu o utilizzare il [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) opzione del compilatore da riga di comando.  
  
 Ad esempio, è possibile usare il modello a oggetti XML del [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Se si imposta un riferimento la <xref:System.Xml> dello spazio dei nomi, è possibile dichiarare e usare una delle relative classi, ad esempio <xref:System.Xml.XmlDocument>. L'esempio seguente usa <xref:System.Xml.XmlDocument>.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a>Importazione di elementi contenitore  
 È possibile usare la [istruzione Imports (tipo e Namespace .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) al *importare* gli spazi dei nomi che contengono i moduli o classi che si desiderano utilizzare. In questo modo è possibile fare riferimento agli elementi definiti in uno spazio dei nomi importato senza qualificare completamente i relativi nomi. Nell'esempio seguente riscritto l'esempio precedente per importare il <xref:System.Xml> dello spazio dei nomi.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 Inoltre, il `Imports` istruzione è possibile definire un *alias di importazione* per ogni spazio dei nomi importato. Ciò può rendere il codice sorgente più breve e facile da leggere. Nell'esempio seguente riscrive l'esempio precedente per usare `xD` come alias per il <xref:System.Xml> dello spazio dei nomi.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 Il `Imports` istruzione non rende disponibili elementi di altri progetti all'applicazione. Vale a dire, non viene preso il posto di un riferimento all'impostazione. L'importazione di uno spazio dei nomi appena rimuove il requisito per qualificare i nomi definiti nello spazio dei nomi.  
  
 È anche possibile usare il `Imports` per importare i moduli, classi, strutture ed enumerazioni. È quindi possibile usare i membri degli elementi importati senza qualifica. Tuttavia, è sempre necessario qualificare i membri non condivisi di classi e strutture con una variabile o espressione che restituisce un'istanza della classe o struttura.  
  
## <a name="naming-guidelines"></a>Convenzioni di denominazione  
 Quando si definiscono due o più elementi di programmazione che hanno lo stesso nome, una *ambiguità dei nomi* può verificarsi quando il compilatore prova a risolvere un riferimento a tale nome. Se più di una definizione nell'ambito, o se non è una definizione nell'ambito, il riferimento è non risolvibile. Per un esempio, vedere "Esempio di riferimento qualificato" in questa pagina della Guida.  
  
 È possibile evitare ambiguità dei nomi mediante l'assegnazione di tutti gli elementi di nomi univoci. Quindi è possibile creare riferimento a tutti gli elementi senza dover qualificare il nome con un spazio dei nomi, modulo o classe. È anche possibile ridurre le probabilità di errore che fa riferimento a un elemento non corretto.  
  
## <a name="shadowing"></a>Shadowing  
 Quando due elementi di programmazione condividono lo stesso nome, è possibile nascondere uno di essi, oppure *shadow*, un altro. Un elemento nascosto non è disponibile per riferimento; al contrario, quando il codice usi il nome dell'elemento nascosto, il compilatore Visual Basic si risolve nell'elemento di shadowing. Per una spiegazione più dettagliata con esempi, vedere [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
## <a name="see-also"></a>Vedere anche
- [Nomi di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Caratteristiche di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
- [Variabili](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Operatore New](../../../../visual-basic/language-reference/operators/new-operator.md)
- [Public](../../../../visual-basic/language-reference/modifiers/public.md)

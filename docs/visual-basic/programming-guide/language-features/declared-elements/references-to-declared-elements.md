---
title: References to Declared Elements
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: 23bff2eb098982f67ecb1b709e59096d5259a644
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405183"
---
# <a name="references-to-declared-elements-visual-basic"></a>Riferimenti a elementi dichiarati (Visual Basic)
Quando il codice fa riferimento a un elemento dichiarato, il compilatore Visual Basic corrisponde al nome nel riferimento alla dichiarazione appropriata di tale nome. Se più di un elemento viene dichiarato con lo stesso nome, è possibile controllare a quali di questi elementi deve essere fatto riferimento *qualificando* il relativo nome.  
  
 Il compilatore tenta di far corrispondere un riferimento a un nome a una dichiarazione di nome con l' *ambito più restrittivo*. Ciò significa che inizia con il codice che fa riferimento e funziona in modo esterno attraverso i livelli successivi di elementi che lo contengono.  
  
 Nell'esempio seguente vengono illustrati i riferimenti a due variabili con lo stesso nome. Nell'esempio vengono dichiarate due variabili, ciascuna denominata `totalCount` , a diversi livelli di ambito nel modulo `container` . Quando la procedura `showCount` viene visualizzata `totalCount` senza qualificazione, il Visual Basic compilatore risolve il riferimento alla dichiarazione con l'ambito più piccolo, ovvero la dichiarazione locale all'interno di `showCount` . Quando si qualifica `totalCount` con il modulo contenitore `container` , il compilatore risolve il riferimento alla dichiarazione con l'ambito più ampio.  
  
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
  
## <a name="qualifying-an-element-name"></a>Qualificazione del nome di un elemento  
 Se si desidera eseguire l'override di questo processo di ricerca e specificare un nome dichiarato in un ambito più ampio, è necessario *qualificare* il nome con l'elemento contenitore dell'ambito più ampio. In alcuni casi, potrebbe anche essere necessario qualificare l'elemento contenitore.  
  
 Per qualificare un nome si intende precederlo nell'istruzione source con le informazioni che identificano la posizione in cui è definito l'elemento di destinazione. Queste informazioni sono definite *stringa di qualificazione*. Può includere uno o più spazi dei nomi e un modulo, una classe o una struttura.  
  
 La stringa di qualificazione deve specificare in modo univoco il modulo, la classe o la struttura contenente l'elemento di destinazione. Il contenitore può a sua volta trovarsi in un altro elemento contenitore, in genere uno spazio dei nomi. Potrebbe essere necessario includere diversi elementi contenenti nella stringa di qualificazione.  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a>Per accedere a un elemento dichiarato qualificando il nome  
  
1. Determinare la posizione in cui è stato definito l'elemento. Potrebbe includere uno spazio dei nomi o persino una gerarchia di spazi dei nomi. All'interno dello spazio dei nomi di livello più basso, l'elemento deve essere contenuto in un modulo, una classe o una struttura.  
  
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
  
2. Determinare un percorso di qualificazione in base alla posizione dell'elemento di destinazione. Iniziare con lo spazio dei nomi di livello più alto, passare allo spazio dei nomi di livello più basso e terminare con il modulo, la classe o la struttura contenente l'elemento di destinazione. Ogni elemento nel percorso deve contenere l'elemento che lo segue.  
  
     `outerSpace` → `innerSpace` → `holdsTotals` → `totals`  
  
3. Preparare la stringa di qualificazione per l'elemento di destinazione. Inserire un punto ( `.` ) dopo ogni elemento del percorso. L'applicazione deve avere accesso a ogni elemento nella stringa di qualificazione.  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4. Scrivere l'espressione o l'istruzione di assegnazione che fa riferimento all'elemento di destinazione nel modo normale.  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5. Precede il nome dell'elemento di destinazione con la stringa di qualificazione. Il nome deve seguire immediatamente il punto ( `.` ) che segue il modulo, la classe o la struttura che contiene l'elemento.  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6. Il compilatore usa la stringa di qualificazione per trovare una dichiarazione chiara e non ambigua a cui può corrispondere il riferimento all'elemento di destinazione.  
  
 Potrebbe anche essere necessario qualificare un riferimento al nome se l'applicazione ha accesso a più di un elemento di programmazione con lo stesso nome. Ad esempio, gli <xref:System.Windows.Forms> <xref:System.Web.UI.WebControls> spazi dei nomi e contengono entrambi una `Label` classe ( <xref:System.Windows.Forms.Label?displayProperty=nameWithType> e <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType> ). Se l'applicazione usa entrambi o se definisce la propria `Label` classe, è necessario distinguere i diversi `Label` oggetti. Includere lo spazio dei nomi o l'alias di importazione nella dichiarazione di variabile. Nell'esempio seguente viene usato l'alias di importazione.  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a>Membri di altri elementi contenenti  
 Quando si utilizza un membro non condiviso di un'altra classe o struttura, è necessario innanzitutto qualificare il nome del membro con una variabile o un'espressione che punta a un'istanza della classe o della struttura. Nell'esempio seguente `demoClass` è un'istanza di una classe denominata `class1` .  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 Non è possibile usare il nome della classe per qualificare un membro non [condiviso](../../../language-reference/modifiers/shared.md). È innanzitutto necessario creare un'istanza in una variabile oggetto (in questo caso `demoClass` ) e quindi farvi riferimento tramite il nome della variabile.  
  
 Se una classe o una struttura dispone di un `Shared` membro, è possibile qualificare il membro con il nome della classe o della struttura oppure con una variabile o un'espressione che punta a un'istanza di.  
  
 Un modulo non dispone di istanze separate e tutti i relativi membri sono `Shared` per impostazione predefinita. Pertanto, è necessario qualificare un membro del modulo con il nome del modulo.  
  
 Nell'esempio seguente vengono illustrati i riferimenti completi alle procedure dei membri del modulo. Nell'esempio vengono dichiarate due `Sub` procedure, entrambe denominate `perform` , in moduli diversi in un progetto. Ognuno di essi può essere specificato senza qualificazione all'interno del proprio modulo, ma deve essere qualificato se vi si fa riferimento da qualsiasi altra posizione. Poiché il riferimento finale in non `module3` è qualificata `perform` , il compilatore non è in grado di risolvere il riferimento.  
  
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
  
## <a name="references-to-projects"></a>Riferimenti ai progetti  
 Per usare elementi [pubblici](../../../language-reference/modifiers/public.md) definiti in un altro progetto, è necessario innanzitutto impostare un *riferimento* all'assembly o alla libreria dei tipi del progetto. Per impostare un riferimento, fare clic su **Aggiungi riferimento** nel menu **progetto** oppure utilizzare l'opzione del compilatore della riga [di comando-Reference (Visual Basic)](../../../reference/command-line-compiler/reference.md) .  
  
 È ad esempio possibile utilizzare il modello a oggetti XML del .NET Framework. Se si imposta un riferimento allo <xref:System.Xml> spazio dei nomi, è possibile dichiarare e utilizzare una delle relative classi, ad esempio <xref:System.Xml.XmlDocument> . Nell'esempio seguente viene utilizzato <xref:System.Xml.XmlDocument>:  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a>Importazione di elementi contenenti  
 È possibile utilizzare l' [istruzione Imports (tipo e spazio dei nomi .NET)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) per *importare* gli spazi dei nomi che contengono i moduli o le classi che si desidera utilizzare. In questo modo è possibile fare riferimento agli elementi definiti in uno spazio dei nomi importato senza qualificare il nome completo. Nell'esempio seguente viene riscritto l'esempio precedente per importare lo <xref:System.Xml> spazio dei nomi.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 Inoltre, l' `Imports` istruzione può definire un *alias di importazione* per ogni spazio dei nomi importato. Questo può rendere il codice sorgente più breve e più facile da leggere. Nell'esempio seguente viene riscritto l'esempio precedente da utilizzare `xD` come alias per lo <xref:System.Xml> spazio dei nomi.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 L' `Imports` istruzione non rende disponibili gli elementi di altri progetti per l'applicazione. Ciò significa che non viene eseguita l'impostazione di un riferimento. Se si importa uno spazio dei nomi, viene semplicemente rimosso il requisito per qualificare i nomi definiti nello spazio dei nomi.  
  
 È anche possibile usare l' `Imports` istruzione per importare moduli, classi, strutture ed enumerazioni. È quindi possibile usare i membri di tali elementi importati senza qualifica. Tuttavia, è sempre necessario qualificare i membri non condivisi di classi e strutture con una variabile o un'espressione che restituisce un'istanza della classe o della struttura.  
  
## <a name="naming-guidelines"></a>Convenzioni di denominazione  
 Quando si definiscono due o più elementi di programmazione con lo stesso nome, un' *ambiguità dei nomi* può verificarsi quando il compilatore tenta di risolvere un riferimento a tale nome. Se più di una definizione è nell'ambito o se nessuna definizione è nell'ambito, il riferimento è irrisolvibile. Per un esempio, vedere "esempio di riferimento completo" in questa pagina della guida.  
  
 È possibile evitare l'ambiguità dei nomi assegnando a tutti gli elementi nomi univoci. È quindi possibile fare riferimento a qualsiasi elemento senza che sia necessario qualificarne il nome con uno spazio dei nomi, un modulo o una classe. Si riducono inoltre le probabilità di riferimento accidentale all'elemento errato.  
  
## <a name="shadowing"></a>Shadowing  
 Quando due elementi di programmazione condividono lo stesso nome, uno di essi può nascondere, o *ombreggiare*, l'altro. Un elemento ombreggiato non è disponibile per riferimento. al contrario, quando il codice usa il nome dell'elemento ombreggiato, il compilatore Visual Basic lo risolve nell'elemento shadowing. Per una spiegazione più dettagliata con esempi, vedere [shadowing in Visual Basic](shadowing.md).  
  
## <a name="see-also"></a>Vedere anche

- [Declared Element Names](declared-element-names.md)
- [Caratteristiche di elementi dichiarati](declared-element-characteristics.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
- [Variabili](../variables/index.md)
- [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Operatore New](../../../language-reference/operators/new-operator.md)
- [Pubblica](../../../language-reference/modifiers/public.md)

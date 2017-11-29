---
title: Riferimenti a elementi dichiarati (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9b3847164b4e577a9265a746b9329218b4af928b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="references-to-declared-elements-visual-basic"></a>Riferimenti a elementi dichiarati (Visual Basic)
Quando il codice fa riferimento a un elemento dichiarato, il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilatore corrisponde al nome nel riferimento alla dichiarazione appropriata di tale nome. Se più di un elemento viene dichiarato con lo stesso nome, è possibile controllare quale di questi elementi viene riferimento *qualificazione* il relativo nome.  
  
 Il compilatore tenta di ottenere un riferimento al nome di una dichiarazione del nome di *ambito più ristretto*. Ciò significa inizia con il codice di riferimento e procede verso l'esterno tra i livelli successivi di contenente gli elementi.  
  
 L'esempio seguente mostra i riferimenti a due variabili con lo stesso nome. Nell'esempio vengono dichiarate due variabili, ogni denominata `totalCount`, con diversi livelli di ambito nel modulo `container`. Quando la procedura `showCount` Visualizza `totalCount` senza qualifica il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilatore risolve il riferimento alla dichiarazione con l'ambito più ristretto, ovvero la dichiarazione locale all'interno di `showCount`. Quando è qualificato `totalCount` con il modulo contenente `container`, il compilatore risolve il riferimento alla dichiarazione con ambito più ampio.  
  
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
  
## <a name="qualifying-an-element-name"></a>Nome di un elemento di qualificazione  
 Se si desidera eseguire l'override di questo processo di ricerca e specificare un nome dichiarato in un ambito più ampio, è necessario *qualificare* il nome con l'elemento contenitore dell'ambito più ampio. In alcuni casi, potrebbe essere anche necessario qualificare l'elemento contenitore.  
  
 Qualificare un nome significa precedono nell'istruzione di origine con informazioni che identificano in cui è definito l'elemento di destinazione. Queste informazioni vengono definite una *stringa di qualificazione*. Può includere uno o più spazi dei nomi e un modulo, classe o struttura.  
  
 La stringa di qualificazione necessario specificare in modo univoco il modulo, classe o struttura che contiene l'elemento di destinazione. Il contenitore a sua volta potrebbe trovarsi in un altro contenitore, in genere uno spazio dei nomi. Potrebbe essere necessario includere diversi elementi che contiene la stringa di qualificazione.  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a>Per accedere a un elemento dichiarato qualificando il nome  
  
1.  Determinare il percorso in cui è stato definito l'elemento. Può includere uno spazio dei nomi, o anche una gerarchia di spazi dei nomi. Nello spazio dei nomi di livello più basso, l'elemento deve essere incluso in un modulo, classe o struttura.  
  
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
  
2.  Determinare il percorso di qualificazione in base alla posizione dell'elemento di destinazione. Iniziare con lo spazio dei nomi di livello più alto, procedere allo spazio dei nomi di livello più basso e terminare con il modulo, classe o struttura che contiene l'elemento di destinazione. Ogni elemento del percorso deve contenere l'elemento che lo segue.  
  
     `outerSpace` → `innerSpace` → `holdsTotals` → `totals`  
  
3.  Preparare la stringa di qualificazione per l'elemento di destinazione. Inserire un punto (`.`) dopo ogni elemento nel percorso. L'applicazione deve avere accesso a ogni elemento nella stringa di qualificazione.  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4.  Scrivere l'espressione o istruzione di assegnazione che fa riferimento all'elemento di destinazione in modo normale.  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5.  Anteporre al nome di elemento di destinazione con la stringa di qualificazione. Il nome deve seguire immediatamente il periodo (`.`) che segue il modulo, classe o struttura che contiene l'elemento.  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6.  Il compilatore utilizza la stringa di qualificazione per trovare una dichiarazione di non crittografata e non ambigua a cui può far corrispondere il riferimento all'elemento di destinazione.  
  
 Potrebbe inoltre essere necessario qualificare un riferimento al nome, se l'applicazione ha accesso a più di un elemento di programmazione che ha lo stesso nome. Ad esempio, il <xref:System.Windows.Forms> e <xref:System.Web.UI.WebControls> spazi dei nomi di entrambi contengono una `Label` classe (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> e <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>). Se l'applicazione utilizza entrambi, o se definisce il proprio `Label` (classe), è necessario distinguere i diversi `Label` oggetti. Includere l'alias di importazione o dello spazio dei nomi nella dichiarazione di variabile. Nell'esempio seguente usa l'alias di importazione.  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a>Membri di altri elementi contenitore  
 Quando si utilizza un membro non condiviso di un'altra classe o struttura, è innanzitutto necessario qualificare il nome del membro con una variabile o espressione che fa riferimento a un'istanza della classe o struttura. Nell'esempio seguente, `demoClass` è un'istanza di una classe denominata `class1`.  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 È possibile utilizzare il nome della classe per qualificare un membro che non è [Shared](../../../../visual-basic/language-reference/modifiers/shared.md). È innanzitutto necessario creare un'istanza in una variabile oggetto (in questo caso `demoClass`) e quindi farvi riferimento tramite il nome della variabile.  
  
 Se una classe o struttura è un `Shared` membro, è possibile qualificare tale membro con il nome di classe o struttura oppure a una variabile o espressione che fa riferimento a un'istanza.  
  
 Un modulo non dispone di istanze separate e tutti i relativi membri sono `Shared` per impostazione predefinita. Pertanto, qualificare un membro del modulo con il nome del modulo.  
  
 L'esempio seguente mostra i riferimenti qualificati a procedure di membri di modulo. Nell'esempio vengono dichiarati due `Sub` procedure, entrambi denominati `perform`, in moduli diversi in un progetto. Ciascuna di esse può essere specificato senza qualifica all'interno di un proprio modulo, ma deve essere qualificato se viene fatto riferimento da qualsiasi altra posizione. Poiché l'ultimo riferimento in `module3` non soddisfa i requisiti `perform`, il compilatore non è possibile risolvere il riferimento.  
  
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
 Per utilizzare [pubblica](../../../../visual-basic/language-reference/modifiers/public.md) elementi definiti in un altro progetto, è innanzitutto necessario impostare un *riferimento* alla raccolta di assembly o un tipo di progetto. Per impostare un riferimento, fare clic su **Aggiungi riferimento** sul **progetto** menu o utilizzare il [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) l'opzione del compilatore da riga di comando.  
  
 Ad esempio, è possibile utilizzare il modello a oggetti XML del [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Se si imposta un riferimento al <xref:System.Xml> dello spazio dei nomi, è possibile dichiarare e utilizzare le relative classi, ad esempio <xref:System.Xml.XmlDocument>. L'esempio seguente usa <xref:System.Xml.XmlDocument>.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a>Importazione di elementi contenitore  
 È possibile utilizzare il [istruzione Imports (tipo e Namespace .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) a *importare* gli spazi dei nomi che contengono i moduli o le classi che si desidera utilizzare. In questo modo è possibile fare riferimento agli elementi definiti in uno spazio dei nomi importato senza i relativi nomi completi. Nell'esempio seguente viene riscritto l'esempio precedente per importare il <xref:System.Xml> dello spazio dei nomi.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 Inoltre, il `Imports` istruzione è possibile definire un *alias di importazione* per ogni spazio dei nomi importato. Ciò può rendere il codice sorgente più breve e facile da leggere. Nell'esempio seguente viene riscrive l'esempio precedente per utilizzare `xD` come alias per il <xref:System.Xml> dello spazio dei nomi.  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 Il `Imports` istruzione non rende disponibili elementi di altri progetti all'applicazione. Ovvero, non viene preso il posto di un riferimento all'impostazione. L'importazione di uno spazio dei nomi solo rimuove il requisito per qualificare i nomi definiti nello spazio dei nomi.  
  
 È inoltre possibile utilizzare il `Imports` per importare i moduli, classi, strutture ed enumerazioni. È quindi possibile utilizzare i membri degli elementi importati senza qualifica. Tuttavia, è sempre necessario qualificare i membri non condivisi di classi e strutture con una variabile o espressione che restituisce un'istanza della classe o struttura.  
  
## <a name="naming-guidelines"></a>Convenzioni di denominazione  
 Quando si definiscono due o più elementi di programmazione che hanno lo stesso nome, un *ambiguità dei nomi* possono verificarsi quando il compilatore tenta di risolvere un riferimento a tale nome. Se più di una definizione è nell'ambito oppure se non è una definizione nell'ambito, il riferimento non risolvibile. Per un esempio, vedere "Esempio di riferimento completo" di questa pagina della Guida.  
  
 Per evitare ambiguità dei nomi, è possibile assegnare tutti gli elementi di nomi univoci. È possibile quindi creare riferimento a qualsiasi elemento senza dover qualificare il nome con un spazio dei nomi, modulo o classe. È anche possibile ridurre le probabilità di errore che fa riferimento a un elemento non corretto.  
  
## <a name="shadowing"></a>Shadowing  
 Quando due elementi di programmazione condividono lo stesso nome, è possibile nascondere uno di essi, o *shadow*, l'altro. Un elemento nascosto non è disponibile per riferimento; Quando il codice utilizza invece il nome di elemento nascosto, il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilatore risolve tale nome nell'elemento di shadowing. Per una spiegazione più dettagliata con esempi, vedere [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Nomi di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Caratteristiche di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)  
 [Variabili](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Operatore New](../../../../visual-basic/language-reference/operators/new-operator.md)  
 [Public](../../../../visual-basic/language-reference/modifiers/public.md)

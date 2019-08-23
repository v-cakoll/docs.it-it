---
title: Istruzione Using (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: 346a26ad5751599831d8b0d3e0497e4d488eb76c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957538"
---
# <a name="using-statement-visual-basic"></a>Istruzione Using (Visual Basic)
Dichiara l'inizio di un `Using` blocco e, facoltativamente, acquisisce le risorse di sistema controllate dal blocco.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`resourcelist`|Obbligatorio se non si specifica `resourceexpression`. Elenco di una o più risorse di sistema che `Using` questo blocco controlla, separate da virgole.|  
|`resourceexpression`|Obbligatorio se non si specifica `resourcelist`. Variabile di riferimento o espressione che fa riferimento a una risorsa di sistema che deve essere `Using` controllata da questo blocco.|  
|`statements`|facoltativo. Blocco di istruzioni eseguite dal `Using` blocco.|  
|`End Using`|Richiesto. Termina la definizione del `Using` blocco ed Elimina tutte le risorse che controlla.|  
  
 Ogni risorsa `resourcelist` della parte presenta la sintassi e le parti seguenti:  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 -oppure-  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a>Parti Resources  
  
|Termine|Definizione|  
|---|---|  
|`resourcename`|Richiesto. Variabile di riferimento che fa riferimento a una risorsa di `Using` sistema controllata dal blocco.|  
|`New`|Obbligatorio se l' `Using` istruzione acquisisce la risorsa. Se la risorsa è già stata acquisita, utilizzare la seconda alternativa della sintassi.|  
|`resourcetype`|Richiesto. Classe della risorsa. La classe deve implementare l' <xref:System.IDisposable> interfaccia.|  
|`arglist`|facoltativo. Elenco di argomenti passati al costruttore per creare un'istanza di `resourcetype`. Vedere [elenco di parametri](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`resourceexpression`|Richiesto. Variabile o espressione che fa riferimento a una risorsa di sistema che soddisfa i `resourcetype`requisiti di. Se si usa la seconda sintassi alternativa, è necessario acquisire la risorsa prima di passare il `Using` controllo all'istruzione.|  
  
## <a name="remarks"></a>Note  
 A volte il codice richiede una risorsa non gestita, ad esempio un handle di file, un wrapper COM o una connessione SQL. Un `Using` blocco garantisce l'eliminazione di una o più risorse di questo tipo al termine del codice. In modo da renderli disponibili per l'utilizzo da altro codice.  
  
 Le risorse gestite vengono eliminate dal .NET Framework Garbage Collector (GC) senza alcuna codifica aggiuntiva da parte dell'utente. Non è necessario un `Using` blocco per le risorse gestite. Tuttavia, è comunque possibile usare un `Using` blocco per forzare l'eliminazione di una risorsa gestita anziché attendere il Garbage Collector.  
  
 Un `Using` blocco è costituito da tre parti: acquisizione, utilizzo e eliminazione.  
  
- L' *acquisizione* significa creare una variabile e inizializzarla per fare riferimento alla risorsa di sistema. L' `Using` istruzione può acquisire una o più risorse oppure è possibile acquisire esattamente una risorsa prima `Using` di immettere il blocco e fornirla all'istruzione. Se si specifica `resourceexpression`, è necessario acquisire la risorsa prima di passare il `Using` controllo all'istruzione.  
  
- L' *utilizzo* indica l'accesso alle risorse e l'esecuzione di azioni con loro. Le istruzioni tra `Using` e `End Using` rappresentano l'utilizzo delle risorse.  
  
- Per *eliminazione* si intende <xref:System.IDisposable.Dispose%2A> la chiamata al metodo sull' `resourcename`oggetto in. Questo consente all'oggetto di terminare in modo corretto le risorse. L' `End Using` istruzione Elimina le risorse sotto il `Using` controllo del blocco.  
  
## <a name="behavior"></a>Comportamento  
 Un `Using` blocco si comporta `Try`come... costruzione in cui il `Try` blocco utilizza le risorse e il `Finally` blocco ne comporta l'eliminazione. `Finally` Per questo motivo, il `Using` blocco garantisce l'eliminazione delle risorse, indipendentemente dal modo in cui si esce dal blocco. Questo vale anche nel caso di un'eccezione non gestita, ad eccezione di <xref:System.StackOverflowException>.  
  
 L'ambito di ogni variabile di risorsa acquisita `Using` dall'istruzione è limitato `Using` al blocco.  
  
 Se nell' `Using` istruzione si specifica più di una risorsa di sistema, l'effetto sarà identico a quello di un `Using` blocco annidato in un altro.  
  
 Se `resourcename` <xref:System.IDisposable.Dispose%2A> è `Nothing`, non viene effettuata alcuna chiamata a e non viene generata alcuna eccezione.  
  
## <a name="structured-exception-handling-within-a-using-block"></a>Gestione strutturata delle eccezioni in un blocco using  
 Se è necessario gestire un'eccezione che può verificarsi all'interno del `Using` blocco, è possibile aggiungere `Try`un... `Finally` creazione. Se è necessario gestire il caso in cui l' `Using` istruzione non riesce ad acquisire una risorsa, è possibile verificare se `resourcename` è `Nothing`.  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a>Gestione strutturata delle eccezioni anziché un blocco using  
 Se è necessario un `Finally` `Try`controllo più preciso sull'acquisizione delle risorse o se è necessario codice aggiuntivo nel blocco, è possibile riscrivere il `Using` blocco come... `Finally` creazione. Nell'esempio seguente vengono illustrati `Using` scheletri `Try` e costruzioni equivalenti nell'acquisizione e nell'eliminazione di `resource`.  
  
```vb  
Using resource As New resourceType   
    ' Insert code to work with resource.  
End Using  
  
' For the acquisition and disposal of resource, the following  
' Try construction is equivalent to the Using block.  
Dim resource As New resourceType  
Try   
    ' Insert code to work with resource.  
Finally   
    If resource IsNot Nothing Then  
        resource.Dispose()   
    End If  
End Try   
```  
  
> [!NOTE]
> Il codice all'interno `Using` del blocco non deve assegnare l'oggetto `resourcename` in a un'altra variabile. Quando si esce dal `Using` blocco, la risorsa viene eliminata e l'altra variabile non può accedere alla risorsa a cui fa riferimento.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un file denominato log. txt che scrive due righe di testo nel file. Nell'esempio viene inoltre letto lo stesso file e vengono visualizzate le righe di testo.  
  
 Poiché le classi <xref:System.IO.TextReader>eimplementano l' <xref:System.IDisposable> interfaccia, il codice può `Using` utilizzare le istruzioni per garantire che il file venga chiuso correttamente dopo le operazioni di scrittura e lettura. <xref:System.IO.TextWriter>  
  
 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IDisposable>
- [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Procedura: Eliminare una risorsa di sistema](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)

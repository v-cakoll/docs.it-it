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
ms.openlocfilehash: fe53ea58dc98a4de793fe9dad1c3ceeac71622fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58843201"
---
# <a name="using-statement-visual-basic"></a>Istruzione Using (Visual Basic)
Dichiara l'inizio di un `Using` in blocchi e, facoltativamente, acquisisce le risorse di sistema che controlla il blocco.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`resourcelist`|Obbligatorio se non si fornisce `resourceexpression`. Elenco di uno o più risorse di sistema che questo `Using` blocco dei controlli, separati da virgole.|  
|`resourceexpression`|Obbligatorio se non si fornisce `resourcelist`. Variabile di riferimento o un'espressione che fa riferimento a una risorsa di sistema da parte di questo `Using` blocco.|  
|`statements`|Facoltativo. Blocco di istruzioni che la `Using` bloccare l'esecuzione.|  
|`End Using`|Obbligatorio. Termina la definizione del `Using` blocco ed Elimina tutte le risorse da essa controllati.|  
  
 Ogni risorsa nel `resourcelist` parte ha la sintassi e le parti seguenti:  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 -oppure-  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a>Parti resourcelist  
  
|Termine|Definizione|  
|---|---|  
|`resourcename`|Obbligatorio. Variabile di riferimento che fa riferimento a una risorsa di sistema che la `Using` blocco dei controlli.|  
|`New`|Obbligatorio se il `Using` istruzione acquisisce la risorsa. Se la risorsa è già stata acquisita, usare la seconda alternativa di sintassi.|  
|`resourcetype`|Obbligatorio. La classe della risorsa. La classe deve implementare il <xref:System.IDisposable> interfaccia.|  
|`arglist`|Facoltativo. Elenco di argomenti passati al costruttore per creare un'istanza di `resourcetype`. Visualizzare [elenco di parametri](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`resourceexpression`|Obbligatorio. Variabile o espressione che fa riferimento a una risorsa di sistema che soddisfano i requisiti di `resourcetype`. Se si usa la seconda alternativa di sintassi, è necessario acquisire la risorsa prima di passare il controllo al `Using` istruzione.|  
  
## <a name="remarks"></a>Note  
 In alcuni casi il codice richiede una risorsa non gestita, ad esempio un handle di file, un wrapper COM o una connessione SQL. Oggetto `Using` blocco garantisce l'eliminazione di uno o più di tali risorse al termine del codice con essi. Ciò li rende disponibili per altro codice da usare.  
  
 Le risorse gestite vengono eliminate dal garbage collector (GC) di .NET Framework senza scrivere codice aggiuntivo da parte dell'utente. Non è necessario un `Using` blocco per le risorse gestite. Tuttavia, è comunque possibile usare un `Using` blocco per forzare l'eliminazione di una risorsa gestita anziché attendere che il garbage collector.  
  
 Oggetto `Using` blocco è costituito da tre parti: acquisizione, utilizzo ed eliminazione.  
  
-   *Acquisizione* implica la creazione di una variabile e inizializzarla per fare riferimento alla risorsa di sistema. Il `Using` istruzione può acquisire una o più risorse, oppure è possibile acquisire esattamente una risorsa prima di immettere il blocco e forniscono al `Using` istruzione. Se si specificano `resourceexpression`, è necessario acquisire la risorsa prima di passare il controllo al `Using` istruzione.  
  
-   *Utilizzo* significa accedere alle risorse e l'esecuzione di operazioni su tali elementi. Le istruzioni comprese tra `Using` e `End Using` rappresentano l'utilizzo delle risorse.  
  
-   *Disposizione* significa che la chiamata di <xref:System.IDisposable.Dispose%2A> metodo sull'oggetto nelle `resourcename`. In questo modo l'oggetto di terminare correttamente le relative risorse. Il `End Using` istruzione elimina le risorse sotto il `Using` controllo del blocco.  
  
## <a name="behavior"></a>Comportamento  
 Oggetto `Using` blocco si comporta come un `Try`... `Finally` costruzione in cui la `Try` blocco Usa le risorse e il `Finally` blocco le Elimina. Per questo motivo, il `Using` blocco garantisce l'eliminazione delle risorse, indipendentemente dal modo in cui si esce dal blocco. Questo vale anche in caso di un'eccezione non gestita, ad eccezione di un <xref:System.StackOverflowException>.  
  
 L'ambito di ogni variabile di risorsa acquisita dal `Using` istruzione è limitata al `Using` blocco.  
  
 Se si specifica più di una risorsa di sistema nel `Using` istruzione, l'effetto è lo stesso come se annidati `Using` blocca l'uno all'interno di altra.  
  
 Se `resourcename` viene `Nothing`, nessuna chiamata a <xref:System.IDisposable.Dispose%2A> viene effettuata, e viene generata alcuna eccezione.  
  
## <a name="structured-exception-handling-within-a-using-block"></a>All'interno di un blocco tramite gestione strutturata delle eccezioni  
 Se è necessario gestire un'eccezione che potrebbe verificarsi all'interno di `Using` blocco, è possibile aggiungere una completa `Try`... `Finally` costruzione a esso. Se è necessario gestire il caso in cui il `Using` istruzione non ha esito positivo l'acquisizione di una risorsa, è possibile verificare se `resourcename` è `Nothing`.  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a>Invece di un blocco tramite gestione strutturata delle eccezioni  
 Se è necessario un controllo più preciso l'acquisizione delle risorse oppure è necessario codice aggiuntivo nel `Finally` blocco, è possibile riscrivere il `Using` block come un `Try`... `Finally` costruzione. L'esempio seguente mostra scheletro `Try` e `Using` costruzioni equivalenti nell'acquisizione e l'eliminazione di `resource`.  
  
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
>  Il codice all'interno di `Using` blocco non è necessario assegnare l'oggetto in `resourcename` a un'altra variabile. Quando si esce dal `Using` blocco, la risorsa viene eliminato e l'altra variabile non è possibile accedere alla risorsa a cui punta.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea un file denominato log. txt e scrive due righe di testo nel file. Nell'esempio viene inoltre legge tale file e visualizza le righe di testo.  
  
 Poiché il <xref:System.IO.TextWriter> e <xref:System.IO.TextReader> sono classi che implementano le <xref:System.IDisposable> interfaccia, è possibile usare il codice `Using` istruzioni per assicurarsi che il file viene chiuso dopo l'operazione di scrittura correttamente e le operazioni di lettura.  
  
 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IDisposable>
- [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Procedura: Eliminare una risorsa di sistema](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)

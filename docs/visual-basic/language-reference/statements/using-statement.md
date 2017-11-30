---
title: Istruzione Using (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
caps.latest.revision: "36"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ed9cc0d04c89eac1fe342a0924dd89bb1e258a11
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="using-statement-visual-basic"></a>Istruzione Using (Visual Basic)
Dichiara l'inizio di un `Using` blocco e facoltativamente acquisisce le risorse di sistema che controlla il blocco.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`resourcelist`|Obbligatoria se non viene fornito `resourceexpression`. Elenco di uno o più risorse di sistema da questo `Using` blocco dei controlli, separati da virgole.|  
|`resourceexpression`|Obbligatoria se non viene fornito `resourcelist`. Variabile di riferimento o un'espressione che fa riferimento a una risorsa di sistema per essere controllato da questo `Using` blocco.|  
|`statements`|Parametro facoltativo. Blocco di istruzioni che il `Using` bloccare l'esecuzione.|  
|`End Using`|Obbligatorio. Termina la definizione del `Using` blocco ed Elimina tutte le risorse da essa controllati.|  
  
 Ogni risorsa di `resourcelist` parte con la sintassi e le parti seguenti:  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 -oppure-  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a>Parti di resourcelist  
  
|Termine|Definizione|  
|---|---|  
|`resourcename`|Obbligatorio. Variabile di riferimento che fa riferimento a una risorsa di sistema che il `Using` blocco dei controlli.|  
|`New`|Obbligatorio se il `Using` istruzione acquisisce la risorsa. Se la risorsa è già stata acquisita, utilizzare la seconda alternativa di sintassi.|  
|`resourcetype`|Obbligatorio. La classe della risorsa. La classe deve implementare il <xref:System.IDisposable> interfaccia.|  
|`arglist`|Parametro facoltativo. Elenco di argomenti passati al costruttore per creare un'istanza di `resourcetype`. Vedere [elenco parametri](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`resourceexpression`|Obbligatorio. Variabile o espressione che fa riferimento a una risorsa di sistema che soddisfano i requisiti di `resourcetype`. Se si utilizza la seconda alternativa di sintassi, è necessario acquisire la risorsa prima di passare il controllo per il `Using` istruzione.|  
  
## <a name="remarks"></a>Note  
 In alcuni casi il codice richiede una risorsa non gestita, ad esempio un handle di file, un wrapper COM o una connessione SQL. Oggetto `Using` blocco garantisce di tali risorse al termine del codice con essi. Questo li rende disponibile per altro codice.  
  
 Le risorse gestite vengano eliminate dal garbage collector (GC) di .NET Framework senza alcuna codifica aggiuntiva da parte dell'utente. Non è necessario un `Using` blocco per le risorse gestite. Tuttavia, è comunque possibile usare un `Using` blocco per forzare l'eliminazione di una risorsa gestita anziché attendere che il garbage collector.  
  
 Oggetto `Using` blocco è costituito da tre parti: acquisizione, utilizzo ed eliminazione.  
  
-   *Acquisizione* implica la creazione di una variabile e inizializzarlo per fare riferimento alla risorsa di sistema. Il `Using` istruzione può acquisire una o più risorse, o è possibile acquisire esattamente una risorsa prima di immettere il blocco e per fornire il `Using` istruzione. Se si fornisce `resourceexpression`, è necessario acquisire la risorsa prima di passare il controllo per il `Using` istruzione.  
  
-   *Utilizzo* si intende l'accesso alle risorse e di eseguire operazioni su tali. Le istruzioni comprese tra `Using` e `End Using` rappresentano l'utilizzo delle risorse.  
  
-   *Eliminazione* indica la chiamata di <xref:System.IDisposable.Dispose%2A> metodo sull'oggetto in `resourcename`. In questo modo l'oggetto di terminare correttamente le risorse. Il `End Using` istruzione elimina le risorse sotto il `Using` controllo del blocco.  
  
## <a name="behavior"></a>Comportamento  
 Oggetto `Using` blocco si comporta come un `Try`... `Finally` costruzione in cui il `Try` blocco utilizza le risorse e `Finally` blocco le Elimina. Per questo motivo, il `Using` blocco garantisce l'eliminazione delle risorse, indipendentemente da come si esce dal blocco. Questo vale anche nel caso di un'eccezione non gestita, ad eccezione di un <xref:System.StackOverflowException>.  
  
 L'ambito di ogni variabile di risorsa acquisita dal `Using` istruzione è limitata al `Using` blocco.  
  
 Se si specifica più di una risorsa di sistema nel `Using` istruzione, l'effetto è lo stesso nidificando `Using` blocca l'uno all'interno di altra.  
  
 Se `resourcename` è `Nothing`, nessuna chiamata a <xref:System.IDisposable.Dispose%2A> viene eseguita e viene generata alcuna eccezione.  
  
## <a name="structured-exception-handling-within-a-using-block"></a>Strutturata delle eccezioni all'interno di un blocco Using  
 Se è necessario gestire un'eccezione che potrebbe verificarsi all'interno di `Using` blocco, è possibile aggiungere completa `Try`... `Finally` costruzione a esso. Se è necessario gestire il caso in cui il `Using` istruzione non è riuscita durante l'acquisizione di una risorsa, è possibile verificare se `resourcename` è `Nothing`.  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a>Strutturata delle eccezioni anziché un blocco Using  
 Se è necessario un controllo più preciso l'acquisizione delle risorse, oppure è necessario codice aggiuntivo nel `Finally` blocco, è possibile riscrivere la `Using` blocco come un `Try`... `Finally` costruzione. Nell'esempio seguente viene illustrato scheletro `Try` e `Using` costruzioni, equivalenti per l'acquisizione e l'eliminazione di `resource`.  
  
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
>  Il codice all'interno di `Using` blocco non è necessario assegnare l'oggetto in `resourcename` a un'altra variabile. Quando si esce dal `Using` blocco, la risorsa viene eliminato e l'altra variabile non è possibile accedere alla risorsa a cui fa riferimento.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente crea un file denominato >.log.txt e scrive nel file di due righe di testo. Nell'esempio viene inoltre legge di tale file e visualizza le righe di testo.  
  
 Poiché il <xref:System.IO.TextWriter> e <xref:System.IO.TextReader> sono classi che implementano il <xref:System.IDisposable> interfaccia, è possibile utilizzare il codice `Using` istruzioni per assicurarsi che il file viene chiuso dopo la scrittura e operazioni di lettura correttamente.  
  
 [!code-vb[VbVbalrStatements#50](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/using-statement_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IDisposable>  
 [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Procedura: Eliminare una risorsa di sistema](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)

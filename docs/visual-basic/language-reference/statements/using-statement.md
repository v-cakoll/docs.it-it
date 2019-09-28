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
ms.openlocfilehash: 819af63acb6a1f038300bcb999dcfb904eb8a457
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592082"
---
# <a name="using-statement-visual-basic"></a>Istruzione Using (Visual Basic)

Dichiara l'inizio di un blocco `Using` e, facoltativamente, acquisisce le risorse di sistema controllate dal blocco.

## <a name="syntax"></a>Sintassi

```vb
Using { resourcelist | resourceexpression }
    [ statements ]
End Using
```

## <a name="parts"></a>Parti

|Nome|Definizione|  
|---|---|  
|`resourcelist`|Obbligatorio se non si specifica `resourceexpression`. Elenco di una o più risorse di sistema che questa `Using` blocca i controlli, separate da virgole.|  
|`resourceexpression`|Obbligatorio se non si specifica `resourcelist`. Variabile di riferimento o espressione che fa riferimento a una risorsa di sistema che deve essere controllata da questo blocco `Using`.|  
|`statements`|facoltativo. Blocco di istruzioni eseguite dal blocco `Using`.|  
|`End Using`|Obbligatorio. Termina la definizione del blocco `Using` ed Elimina tutte le risorse che controlla.|  

 Ogni risorsa nella parte `resourcelist` presenta la sintassi e le parti seguenti:

 `resourcename As New resourcetype [ ( [ arglist ] ) ]`

 -oppure-

 `resourcename As resourcetype = resourceexpression`

## <a name="resourcelist-parts"></a>Parti Resources

|Nome|Definizione|  
|---|---|  
|`resourcename`|Obbligatorio. Variabile di riferimento che fa riferimento a una risorsa di sistema controllata dal blocco `Using`.|  
|`New`|Obbligatorio se l'istruzione `Using` acquisisce la risorsa. Se la risorsa è già stata acquisita, utilizzare la seconda alternativa della sintassi.|  
|`resourcetype`|Obbligatorio. Classe della risorsa. La classe deve implementare l'interfaccia <xref:System.IDisposable>.|  
|`arglist`|facoltativo. Elenco di argomenti passati al costruttore per creare un'istanza di `resourcetype`. Vedere [elenco di parametri](parameter-list.md).|  
|`resourceexpression`|Obbligatorio. Variabile o espressione che fa riferimento a una risorsa di sistema che soddisfa i requisiti di `resourcetype`. Se si usa la seconda sintassi alternativa, è necessario acquisire la risorsa prima di passare il controllo all'istruzione `Using`.|  
  
## <a name="remarks"></a>Note

 A volte il codice richiede una risorsa non gestita, ad esempio un handle di file, un wrapper COM o una connessione SQL. Un blocco `Using` garantisce l'eliminazione di una o più risorse di questo tipo al termine del codice. In modo da renderli disponibili per l'utilizzo da altro codice.

 Le risorse gestite vengono eliminate dal .NET Framework Garbage Collector (GC) senza alcuna codifica aggiuntiva da parte dell'utente. Non è necessario un blocco `Using` per le risorse gestite. Tuttavia, è comunque possibile usare un blocco `Using` per forzare l'eliminazione di una risorsa gestita anziché attendere l'Garbage Collector.

 Un blocco `Using` è costituito da tre parti: acquisizione, utilizzo e eliminazione.

- L' *acquisizione* significa creare una variabile e inizializzarla per fare riferimento alla risorsa di sistema. L'istruzione `Using` può acquisire una o più risorse oppure è possibile acquisire esattamente una risorsa prima di immettere il blocco e fornirla all'istruzione `Using`. Se si specifica `resourceexpression`, è necessario acquisire la risorsa prima di passare il controllo all'istruzione `Using`.

- L' *utilizzo* indica l'accesso alle risorse e l'esecuzione di azioni con loro. Le istruzioni comprese tra `Using` e `End Using` rappresentano l'utilizzo delle risorse.

- L' *eliminazione* significa chiamare il metodo <xref:System.IDisposable.Dispose%2A> sull'oggetto in `resourcename`. Questo consente all'oggetto di terminare in modo corretto le risorse. L'istruzione `End Using` Elimina le risorse nel controllo del blocco `Using`.

## <a name="behavior"></a>Comportamento

 Un blocco `Using` si comporta come una costruzione `Try`... `Finally` in cui il blocco `Try` utilizza le risorse e il blocco `Finally` li elimina. Per questo motivo, il blocco `Using` garantisce l'eliminazione delle risorse, a prescindere dal modo in cui si esce dal blocco. Questo vale anche nel caso di un'eccezione non gestita, ad eccezione di un <xref:System.StackOverflowException>.

 L'ambito di ogni variabile di risorsa acquisita dall'istruzione `Using` è limitato al blocco `Using`.

 Se si specifica più di una risorsa di sistema nell'istruzione `Using`, l'effetto è identico a quello che si annida `Using` in un altro.

 Se `resourcename` è `Nothing`, non viene effettuata alcuna chiamata a <xref:System.IDisposable.Dispose%2A> e non viene generata alcuna eccezione.

## <a name="structured-exception-handling-within-a-using-block"></a>Gestione strutturata delle eccezioni in un blocco using

 Se è necessario gestire un'eccezione che può verificarsi all'interno del blocco `Using`, è possibile aggiungere una costruzione completa `Try`... `Finally`. Se è necessario gestire il caso in cui l'istruzione `Using` ha esito negativo nell'acquisizione di una risorsa, è possibile verificare se `resourcename` è `Nothing`.

## <a name="structured-exception-handling-instead-of-a-using-block"></a>Gestione strutturata delle eccezioni anziché un blocco using

 Se è necessario un controllo più preciso sull'acquisizione delle risorse o se è necessario codice aggiuntivo nel blocco `Finally`, è possibile riscrivere il blocco `Using` come costruzione `Try`... `Finally`. Nell'esempio seguente vengono illustrate le costruzioni Skeleton `Try` e `Using` equivalenti nell'acquisizione e nell'eliminazione di `resource`.

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
> Il codice all'interno del blocco `Using` non deve assegnare l'oggetto in `resourcename` a un'altra variabile. Quando si esce dal blocco `Using`, la risorsa viene eliminata e l'altra variabile non può accedere alla risorsa a cui fa riferimento.

## <a name="example"></a>Esempio

 Nell'esempio seguente viene creato un file denominato log. txt che scrive due righe di testo nel file. Nell'esempio viene inoltre letto lo stesso file e vengono visualizzate le righe di testo:

 Poiché le classi <xref:System.IO.TextWriter> e <xref:System.IO.TextReader> implementano l'interfaccia <xref:System.IDisposable>, il codice può utilizzare le istruzioni `Using` per garantire che il file venga chiuso correttamente dopo le operazioni di scrittura e lettura.

 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]

## <a name="see-also"></a>Vedere anche

- <xref:System.IDisposable>
- [Istruzione Try...Catch...Finally](try-catch-finally-statement.md)
- [Procedura: Eliminazione di una risorsa di sistema @ no__t-0

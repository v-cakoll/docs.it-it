---
title: Istruzione Using
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: 6ec0e228b3898f66f27e322b5db2dd7f3bf3d7d6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352764"
---
# <a name="using-statement-visual-basic"></a>Istruzione Using (Visual Basic)

Dichiara l'inizio di un blocco di `Using` e, facoltativamente, acquisisce le risorse di sistema controllate dal blocco.

## <a name="syntax"></a>Sintassi

```vb
Using { resourcelist | resourceexpression }
    [ statements ]
End Using
```

## <a name="parts"></a>Parti

|Termine|Definizione|  
|---|---|  
|`resourcelist`|Obbligatorio se non si specifica `resourceexpression`. Elenco di una o più risorse di sistema che questa `Using` blocca i controlli, separate da virgole.|  
|`resourceexpression`|Obbligatorio se non si specifica `resourcelist`. Una variabile di riferimento o un'espressione che fa riferimento a una risorsa di sistema che deve essere controllata da questo blocco `Using`.|  
|`statements`|Facoltativa. Blocco di istruzioni eseguite dal blocco `Using`.|  
|`End Using`|Obbligatoria. Termina la definizione del blocco `Using` ed Elimina tutte le risorse che controlla.|  

 Ogni risorsa della parte `resourcelist` presenta la sintassi e le parti seguenti:

 `resourcename As New resourcetype [ ( [ arglist ] ) ]`

 -oppure-

 `resourcename As resourcetype = resourceexpression`

## <a name="resourcelist-parts"></a>Parti Resources

|Termine|Definizione|  
|---|---|  
|`resourcename`|Obbligatoria. Variabile di riferimento che fa riferimento a una risorsa di sistema che la `Using` blocca i controlli.|  
|`New`|Obbligatorio se l'istruzione `Using` acquisisce la risorsa. Se la risorsa è già stata acquisita, utilizzare la seconda alternativa della sintassi.|  
|`resourcetype`|Obbligatoria. Classe della risorsa. La classe deve implementare l'interfaccia <xref:System.IDisposable>.|  
|`arglist`|Facoltativa. Elenco di argomenti passati al costruttore per creare un'istanza di `resourcetype`. Vedere [elenco di parametri](parameter-list.md).|  
|`resourceexpression`|Obbligatoria. Variabile o espressione che fa riferimento a una risorsa di sistema che soddisfa i requisiti di `resourcetype`. Se si usa la seconda sintassi alternativa, è necessario acquisire la risorsa prima di passare il controllo all'istruzione `Using`.|  
  
## <a name="remarks"></a>Note

 A volte il codice richiede una risorsa non gestita, ad esempio un handle di file, un wrapper COM o una connessione SQL. Un blocco `Using` garantisce l'eliminazione di una o più risorse di questo tipo al termine del codice. In modo da renderli disponibili per l'utilizzo da altro codice.

 Le risorse gestite vengono eliminate dal .NET Framework Garbage Collector (GC) senza alcuna codifica aggiuntiva da parte dell'utente. Non è necessario un blocco `Using` per le risorse gestite. Tuttavia, è comunque possibile usare un blocco `Using` per forzare l'eliminazione di una risorsa gestita anziché attendere il Garbage Collector.

 Un blocco `Using` è costituito da tre parti: acquisizione, utilizzo e eliminazione.

- L' *acquisizione* significa creare una variabile e inizializzarla per fare riferimento alla risorsa di sistema. L'istruzione `Using` può acquisire una o più risorse oppure è possibile acquisire esattamente una risorsa prima di immettere il blocco e fornirla all'istruzione `Using`. Se si fornisce `resourceexpression`, è necessario acquisire la risorsa prima di passare il controllo all'istruzione `Using`.

- L' *utilizzo* indica l'accesso alle risorse e l'esecuzione di azioni con loro. Le istruzioni tra `Using` e `End Using` rappresentano l'utilizzo delle risorse.

- Per *eliminazione* si intende la chiamata al metodo <xref:System.IDisposable.Dispose%2A> sull'oggetto `resourcename`. Questo consente all'oggetto di terminare in modo corretto le risorse. L'istruzione `End Using` Elimina le risorse sotto il controllo del blocco di `Using`.

## <a name="behavior"></a>Comportamento

 Un blocco di `Using` si comporta come una costruzione di `Try`...`Finally` in cui il blocco `Try` usa le risorse e il `Finally` blocco ne comporta l'eliminazione. Per questo motivo, il blocco `Using` garantisce l'eliminazione delle risorse, indipendentemente dal modo in cui si esce dal blocco. Questo vale anche nel caso di un'eccezione non gestita, ad eccezione di un <xref:System.StackOverflowException>.

 L'ambito di ogni variabile di risorsa acquisita dall'istruzione `Using` è limitato al blocco di `Using`.

 Se si specifica più di una risorsa di sistema nell'istruzione `Using`, l'effetto è identico a quello che si annida `Using` blocca un oggetto all'interno di un altro.

 Se `resourcename` è `Nothing`, non viene effettuata alcuna chiamata a <xref:System.IDisposable.Dispose%2A> e non viene generata alcuna eccezione.

## <a name="structured-exception-handling-within-a-using-block"></a>Gestione strutturata delle eccezioni in un blocco using

 Se è necessario gestire un'eccezione che può verificarsi all'interno del blocco di `Using`, è possibile aggiungere una costruzione completa `Try`...`Finally`. Se è necessario gestire il caso in cui l'istruzione `Using` non riesce ad acquisire una risorsa, è possibile verificare se `resourcename` è `Nothing`.

## <a name="structured-exception-handling-instead-of-a-using-block"></a>Gestione strutturata delle eccezioni anziché un blocco using

 Se è necessario un controllo più accurato sull'acquisizione delle risorse o se è necessario codice aggiuntivo nel blocco `Finally`, è possibile riscrivere il blocco `Using` come una costruzione `Try`...`Finally`. Nell'esempio seguente vengono illustrate `Try` di ossatura e costruzioni `Using` equivalenti nell'acquisizione e nell'eliminazione di `resource`.

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
> Il codice all'interno del blocco `Using` non deve assegnare l'oggetto `resourcename` a un'altra variabile. Quando si esce dal blocco `Using`, la risorsa viene eliminata e l'altra variabile non può accedere alla risorsa a cui fa riferimento.

## <a name="example"></a>Esempio

 Nell'esempio seguente viene creato un file denominato log. txt che scrive due righe di testo nel file. Nell'esempio viene inoltre letto lo stesso file e vengono visualizzate le righe di testo:

 Poiché le classi <xref:System.IO.TextWriter> e <xref:System.IO.TextReader> implementano l'interfaccia <xref:System.IDisposable>, il codice può utilizzare `Using` istruzioni per garantire che il file venga chiuso correttamente dopo le operazioni di scrittura e lettura.

 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]

## <a name="see-also"></a>Vedere anche

- <xref:System.IDisposable>
- [Istruzione Try...Catch...Finally](try-catch-finally-statement.md)
- [Procedura: Eliminare una risorsa di sistema](../../programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)

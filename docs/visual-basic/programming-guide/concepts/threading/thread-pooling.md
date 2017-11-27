---
title: (Visual Basic) di Pooling dei thread
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4903fb7a-eaad-435a-9add-1d1b32de3b83
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 33b89d261aa2d038926f8c7e1832436b0cd34019
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="thread-pooling-visual-basic"></a>(Visual Basic) di Pooling dei thread
Un *pool di thread* è una Collection di thread che è possibile usare per eseguire diverse attività in background. (Vedere [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) per informazioni generali.) In questo modo il thread primario è libero di eseguire altre attività in modo asincrono.  
  
 I pool di thread vengono spesso usati nelle applicazioni server. Ad ogni richiesta in arrivo viene assegnato un thread del pool. In questo modo la richiesta può essere elaborata in modo asincrono, senza bloccare il thread primario o ritardare l'elaborazione delle richieste successive.  
  
 Una volta completata l'attività, il thread del pool torna in una coda di thread in attesa, dove potrà essere riusato evitando in questo modo la necessità di creare un nuovo thread per ogni attività.  
  
 Esiste in genere un numero massimo di thread che è possibile inserire in un pool. Se tutti i thread sono occupati, le altre attività vengono inserite in coda finché non potranno essere eseguite dai thread che si renderanno disponibili.  
  
 È possibile implementare un pool di thread personalizzato, ma risulta più agevole usare quello fornito con .NET Framework tramite la classe <xref:System.Threading.ThreadPool>.  
  
 Pool di thread, si chiama il <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> metodo con un delegato per la procedura da eseguire e Visual Basic viene creato il thread e viene eseguita la stored procedure.  
  
## <a name="thread-pooling-example"></a>Esempio di limitazione delle richieste di thread  
 Nell'esempio seguente viene illustrato come usare la limitazione delle richieste di thread per avviare svariate attività.  
  
```vb  
Public Sub DoWork()  
    ' Queue a task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        New System.Threading.WaitCallback(AddressOf SomeLongTask))  
    ' Queue another task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        New System.Threading.WaitCallback(AddressOf AnotherLongTask))  
End Sub  
Private Sub SomeLongTask(ByVal state As Object)  
    ' Insert code to perform a long task.  
End Sub  
Private Sub AnotherLongTask(ByVal state As Object)  
    ' Insert code to perform another long task.  
End Sub  
```  
  
 Uno dei vantaggi offerti dalla limitazione di richieste di thread consiste nella possibilità di passare argomenti in un oggetto di stato alla routine di attività. Se per la routine chiamata è necessario più di un argomento, è possibile eseguire il cast di una struttura o un'istanza di una classe in un tipo di dati `Object`.  
  
## <a name="thread-pool-parameters-and-return-values"></a>Parametri e valori restituiti del pool di thread  
 La restituzione di valori da un thread del pool di thread non risulta semplicissima. Non è possibile avvalersi della soluzione standard per la restituzione di valori da una chiamata di funzione, poiché in un pool di thread possono essere accodate solo le routine `Sub`. Un modo per specificare i parametri e restituire valori è incapsulando i parametri, valori restituiti, e i metodi in un classe wrapper come descritto in [parametri e valori restituiti per routine multithreading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).  
  
 La variabile facoltativa dell'oggetto di stato `ByVal` del metodo <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> offre un metodo più semplice per fornire i parametri e restituire valori. Se si usa tale variabile per passare un riferimento a un'istanza di una classe, i membri dell'istanza potranno essere modificati dal thread del pool di thread e usati come valori restituiti.  
  
 Inizialmente potrebbe non essere evidente che è possibile modificare un oggetto a cui fa riferimento una variabile che viene passata per valore. Questa operazione può essere eseguita perché solo il riferimento oggetto viene inviato dal valore. Quando si apportano modifiche ai membri dell'oggetto indicato dal riferimento all'oggetto, le modifiche vengono applicate all'istanza di classe effettiva.  
  
 Non è possibile usare le strutture per restituire valori all'interno di oggetti di stato. Poiché le strutture sono tipi valore, le modifiche apportate dal processo asincrono non comportano la modifica dei membri della struttura originale. Utilizzare le strutture per fornire parametri nei casi in cui non sono necessari i valori restituiti.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [Procedura: Usare un pool di thread (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)  
 [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)  
 [Applicazioni multithreading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)  
 [Sincronizzazione di thread (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)

---
title: Limitazione delle richieste di thread (C#)
ms.date: 07/20/2015
ms.assetid: 98ae68c1-ace8-44b9-9317-8920ac9ef2b6
ms.openlocfilehash: 42e1dcedc1897dc82bbd13f12882cbef6a5da4c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33334197"
---
# <a name="thread-pooling-c"></a>Limitazione delle richieste di thread (C#)
Un *pool di thread* è una Collection di thread che è possibile usare per eseguire diverse attività in background. Per informazioni generali, vedere [Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md). In questo modo il thread primario è libero di eseguire altre attività in modo asincrono.  
  
 I pool di thread vengono spesso usati nelle applicazioni server. Ad ogni richiesta in arrivo viene assegnato un thread del pool. In questo modo la richiesta può essere elaborata in modo asincrono, senza bloccare il thread primario o ritardare l'elaborazione delle richieste successive.  
  
 Una volta completata l'attività, il thread del pool torna in una coda di thread in attesa, dove potrà essere riusato evitando in questo modo la necessità di creare un nuovo thread per ogni attività.  
  
 Esiste in genere un numero massimo di thread che è possibile inserire in un pool. Se tutti i thread sono occupati, le altre attività vengono inserite in coda finché non potranno essere eseguite dai thread che si renderanno disponibili.  
  
 È possibile implementare un pool di thread personalizzato, ma risulta più agevole usare quello fornito con .NET Framework tramite la classe <xref:System.Threading.ThreadPool>.  
  
 Per creare un pool di thread, si chiama il metodo <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> con un delegato per la routine da eseguire e tramite C# si crea il thread e si esegue la routine.  
  
## <a name="thread-pooling-example"></a>Esempio di limitazione delle richieste di thread  
 Nell'esempio seguente viene illustrato come usare la limitazione delle richieste di thread per avviare svariate attività.  
  
```csharp  
public void DoWork()  
{  
    // Queue a task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        new System.Threading.WaitCallback(SomeLongTask));  
    // Queue another task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        new System.Threading.WaitCallback(AnotherLongTask));  
}  
  
private void SomeLongTask(Object state)  
{  
    // Insert code to perform a long task.  
}  
  
private void AnotherLongTask(Object state)  
{  
    // Insert code to perform a long task.  
}  
```  
  
 Uno dei vantaggi offerti dalla limitazione di richieste di thread consiste nella possibilità di passare argomenti in un oggetto di stato alla routine di attività. Se per la routine chiamata è necessario più di un argomento, è possibile eseguire il cast di una struttura o un'istanza di una classe in un tipo di dati `Object`.  
  
## <a name="thread-pool-parameters-and-return-values"></a>Parametri e valori restituiti del pool di thread  
 La restituzione di valori da un thread del pool di thread non risulta semplicissima. Non è possibile avvalersi della soluzione standard per la restituzione di valori da una chiamata di funzione, poiché in un pool di thread possono essere accodate solo le routine `Sub`. Un modo per fornire parametri e restituire valori è incapsulando i parametri, i valori restituiti e i metodi in una classe wrapper come descritto in [Parametri e valori restituiti per routine multithreading (C#)](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).  
  
 La `ByVal`variabile facoltativa dell'oggetto di stato<xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> del metodo offre un metodo più semplice per fornire i parametri e restituire valori. Se si usa tale variabile per passare un riferimento a un'istanza di una classe, i membri dell'istanza potranno essere modificati dal thread del pool di thread e usati come valori restituiti.  
  
 Inizialmente potrebbe non essere evidente che è possibile modificare un oggetto a cui fa riferimento una variabile che viene passata per valore. Questa operazione può essere eseguita perché solo il riferimento oggetto viene inviato dal valore. Quando si apportano modifiche ai membri dell'oggetto indicato dal riferimento all'oggetto, le modifiche vengono applicate all'istanza di classe effettiva.  
  
 Non è possibile usare le strutture per restituire valori all'interno di oggetti di stato. Poiché le strutture sono tipi valore, le modifiche apportate dal processo asincrono non comportano la modifica dei membri della struttura originale. Utilizzare le strutture per fornire parametri nei casi in cui non sono necessari i valori restituiti.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [Procedura: Usare un pool di thread (C#)](../../../../csharp/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)  
 [Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md)  
 [Applicazioni multithreading (C#)](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)  
 [Sincronizzazione di thread (C#)](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)

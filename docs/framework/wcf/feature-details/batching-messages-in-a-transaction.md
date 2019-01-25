---
title: Raggruppamento di messaggi in una transazione
ms.date: 03/30/2017
helpviewer_keywords:
- batching messages [WCF]
ms.assetid: 53305392-e82e-4e89-aedc-3efb6ebcd28c
ms.openlocfilehash: a09cbbe8b77523184a3e75b8fd4301ca956d5cd2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700554"
---
# <a name="batching-messages-in-a-transaction"></a>Raggruppamento di messaggi in una transazione
Le applicazioni in coda utilizzano le transazioni per garantire che i messaggi siano corretti e che vengano recapitati in modo affidabile. Tuttavia, le transazioni sono operazioni che richiedono un'elevata quantità di risorse e che pertanto possono comportare una notevole riduzione della velocità effettiva di recapito dei messaggi. Un modo per migliorare questa velocità è configurare un'applicazione affinché legga ed elabori più messaggi in un'unica transazione. Il compromesso è tra prestazioni e ripristino: il numero di messaggi raggruppati in un batch è infatti direttamente proporzionale alla quantità di operazioni di ripristino necessarie in caso di rollback delle transazioni. È importante notare la differenza tra raggruppare i messaggi in una transazione e raggruppare i messaggi in una sessione. Oggetto *sessione* è un raggruppamento di messaggi correlati che vengono elaborati da un'unica applicazione e sottoposte a commit come singola unità. In genere le sessioni vengono utilizzate quando occorre elaborare nello stesso contesto un gruppo di messaggi correlati. Ad esempio, questo tipo di elaborazione viene utilizzato nei siti Web che consentono di fare acquisti in linea. *Batch* vengono usati per elaborare più, non correlata di messaggi in modo che aumenta la velocità effettiva dei messaggi. Per altre informazioni sulle sessioni, vedere [raggruppamento di messaggi in coda in una sessione](../../../../docs/framework/wcf/feature-details/grouping-queued-messages-in-a-session.md). Anche per i messaggi raggruppati in batch l'elaborazione viene eseguita da un'unica applicazione e il commit viene svolto in un'unica operazione. A differenza delle sessioni, tuttavia, fra i messaggi di un batch è possibile che non sussista alcuna correlazione. Il raggruppamento dei messaggi in una transazione è un'ottimizzazione che non influisce sulla modalità di esecuzione dell'applicazione.  
  
## <a name="entering-batching-mode"></a>Passaggio in modalità batch  
 Il comportamento dell'endpoint <xref:System.ServiceModel.Description.TransactedBatchingBehavior> controlla la funzionalità di batch. Aggiunta di questo comportamento dell'endpoint a un endpoint del servizio, indica a Windows Communication Foundation (WCF) per i messaggi in batch in una transazione. Non tutti i messaggi richiedono una transazione, in modo che solo i messaggi che richiedono una transazione vengono inseriti in un batch e solo i messaggi inviati da operazioni contrassegnate con `TransactionScopeRequired`  =  `true` e `TransactionAutoComplete`  =  `true` sono considerato per un batch. Se tutte le operazioni nel contratto di servizio sono contrassegnate con `TransactionScopeRequired`  =  `false` e `TransactionAutoComplete`  =  `false`, quindi in modalità batch non passa mai.  
  
## <a name="committing-a-transaction"></a>Commit di una transazione  
 Il commit di una transazione eseguita in batch viene eseguito nei casi seguenti:  
  
-   `MaxBatchSize`. Si tratta di una proprietà del comportamento <xref:System.ServiceModel.Description.TransactedBatchingBehavior>. Questa proprietà determina il numero massimo di messaggi raggruppati in un batch. Quando questo numero viene raggiunto, il sistema esegue il commit del batch. Questo valore non rappresenta un limite rigido: è infatti possibile eseguire il commit di un batch prima che venga raggiunto il numero specificato di messaggi.  
  
-   `Transaction Timeout`. Dopo aver atteso per un periodo di tempo corrispondente all'80% del timeout della transazione, il sistema esegue il commit del batch e ne crea uno nuovo. Ciò significa che se resta il 20% o meno del tempo previsto per il completamento della transazione, il sistema esegue il commit del batch.  
  
-   `TransactionScopeRequired`. Durante l'elaborazione di un batch di messaggi, se WCF trovato uno che dispone `TransactionScopeRequired`  =  `false`, esegue il commit del batch e si riapre un nuovo batch al momento della ricezione del primo messaggio con `TransactionScopeRequired`  =  `true` e `TransactionAutoComplete`  = `true`.  
  
-   Se nella coda non esistono più messaggi, il sistema esegue il commit del batch corrente. Ciò si verifica anche se non è stato raggiunto il limite `MaxBatchSize` e se non è trascorso l'80% del timeout della transazione.  
  
## <a name="leaving-batching-mode"></a>Uscita dalla modalità batch  
 Se una transazione viene interrotta a causa di un messaggio appartenente a un batch, si verifica la sequenza di eventi seguente:  
  
1.  Viene eseguito il rollback dell'intero batch di messaggi.  
  
2.  I messaggi vengono letti uno alla volta fino al superamento di un limite pari al doppio della dimensione massima di batch.  
  
3.  Il sistema passa nuovamente in modalità batch.  
  
## <a name="choosing-the-batch-size"></a>Scelta della dimensione di batch  
 La dimensione di batch dipende dall'applicazione utilizzata. Il metodo empirico è il miglior modo per determinare la dimensione di batch ottimale per l'applicazione. La scelta della dimensione di batch deve essere eseguita in base al modello effettivo di distribuzione dell'applicazione utilizzata. Ad esempio, si supponga che il modello di distribuzione dell'applicazione preveda un server SLQ in un computer remoto e una transazione che coinvolge sia la coda sia il server SQL. In tal caso, per ottimizzare la scelta della dimensione di batch, è necessario eseguire l'applicazione attenendosi rigidamente alla configurazione appena descritta.  
  
## <a name="concurrency-and-batching"></a>Esecuzione di più batch simultanei  
 Per aumentare la velocità effettiva è inoltre possibile eseguire più batch contemporaneamente. Per attivare questa funzionalità occorre impostare l'elemento `ConcurrencyMode.Multiple` dell'attributo `ServiceBehaviorAttribute`.  
  
 *Limitazione del servizio* è un comportamento del servizio che consente di indicare il numero massimo di chiamate simultanee può accadere che il servizio. Quando viene utilizzato con la funzionalità di batch, questo numero viene interpretato come numero massimo di batch eseguibili simultaneamente. Se la limitazione del servizio non è impostata, WCF predefinito è il numero massimo di chiamate simultanee su 16. Pertanto, se viene aggiunto il comportamento dell'invio in batch per impostazione predefinita, può essere attivo un massimo di 16 batch contemporaneamente. Le impostazioni della limitazione di servizio e della funzionalità di batch devono essere scelte in base alla capacità del sistema. Si consideri ad esempio il caso di una coda da 100 messaggi per cui si desidera un batch da 20 messaggi. In tal caso, un limite massimo di chiamate simultanee pari a 16 risulta essere poco conveniente. Infatti, a seconda della velocità effettiva, è possibile che siano attive 16 transazioni. Ovvero, è quasi come non aver attivato la funzionalità di batch. Pertanto, quando si ottimizzano le prestazioni, è consigliabile evitare batch simultanei oppure utilizzarli impostando correttamente le dimensioni della limitazione di servizio.  
  
## <a name="batching-and-multiple-endpoints"></a>Impostazione della dimensione di batch in caso di endpoint multipli  
 Un endpoint è costituito da un indirizzo e un contratto. È possibile che più endpoint condividano la stessa associazione. In particolare, è possibile che due endpoint condividano la stessa associazione e lo stesso URI (Uniform Resource Identifier) di attesa, ovvero lo stesso indirizzo di coda. Se due endpoint leggono dalla stessa coda ed entrambi presentano il comportamento di batch transazionale, è possibile che si verifichi un conflitto fra le dimensioni di batch specificate. Per risolvere questo problema è possibile implementare la funzionalità di batch utilizzando la dimensione di batch minore fra quelle specificate nei comportanti di batch transazionale. In questo scenario, se uno degli endpoint non specifica la funzionalità di batch transazionale, nessuno dei due endpoint implementa la funzionalità di batch.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare il comportamento `TransactedBatchingBehavior` in un file di configurazione.  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="TransactedBatchingBehavior"
              maxBatchSize="100" />
  </endpointBehaviors>
</behaviors>
```  
  
 Nell'esempio seguente viene illustrato come specificare il comportamento <xref:System.ServiceModel.Description.TransactedBatchingBehavior> in codice.  
  
```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))
{
     ServiceEndpoint sep = ServiceHost.AddServiceEndpoint(typeof(IOrderProcessor), new NetMsmqBinding(), "net.msmq://localhost/private/ServiceModelSamplesTransacted");
     sep.Behaviors.Add(new TransactedBatchingBehavior(100));
     
     // Open the ServiceHost to create listeners and start listening for messages.
    serviceHost.Open();
  
    // The service can now be accessed.
    Console.WriteLine("The service is ready.");
    Console.WriteLine("Press <ENTER> to terminate service.");
    Console.WriteLine();
    Console.ReadLine();
  
    // Close the ServiceHostB to shut down the service.
    serviceHost.Close();
}  
```  
  
## <a name="see-also"></a>Vedere anche
- [Panoramica delle code](../../../../docs/framework/wcf/feature-details/queues-overview.md)
- [Accodamento in WCF](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)

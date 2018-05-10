---
title: Invio e ricezione degli errori
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handling faults [WCF], sending
ms.assetid: 7be6fb96-ce2a-450b-aebe-f932c6a4bc5d
ms.openlocfilehash: 5a4b4dc79b0f0dad661d99fae6377d1c86b673b6
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
---
# <a name="sending-and-receiving-faults"></a>Invio e ricezione degli errori
Gli errori SOAP trasportano informazioni sulla condizione di errore da un servizio a un client e, nel caso duplex, da un client a un servizio in modo interoperativo. In genere, un servizio definisce un contenuto di errore personalizzato e specifica quali operazioni possono restituirlo. (Per ulteriori informazioni, vedere [definizione e gli errori specifica](../../../docs/framework/wcf/defining-and-specifying-faults.md).) In questo argomento vengono descritti il modo in cui un servizio o un client duplex può inviare tali errori quando si verifica la condizione di errore corrispondente e la modalità con cui un'applicazione client o server gestisce tali errori. Per una panoramica di gestione degli errori in applicazioni Windows Communication Foundation (WCF), vedere [specifica e gestione degli errori in contratti e servizi](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
## <a name="sending-soap-faults"></a>Invio di errori SOAP  
 Gli errori SOAP dichiarati sono quelli in cui un'operazione presenta un <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> che specifica un tipo di errore SOAP personalizzato. Gli errori SOAP non dichiarati sono quelli che non vengono specificati nel contratto per un'operazione.  
  
### <a name="sending-declared-faults"></a>Invio di errori dichiarati  
 Per inviare un errore SOAP dichiarato, rilevare la condizione di errore adatta all'errore SOAP e generare una nuova eccezione <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> in cui il parametro di tipo è un nuovo oggetto del tipo specificato nell'attributo <xref:System.ServiceModel.FaultContractAttribute> di tale operazione. Nell'esempio di codice seguente viene illustrato come utilizzare l'attributo <xref:System.ServiceModel.FaultContractAttribute> per specificare che l'operazione `SampleMethod` può restituire un errore SOAP contente informazioni dettagliate di tipo `GreetingFault`.  
  
 [!code-csharp[FaultContractAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#4)]
 [!code-vb[FaultContractAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#4)]  
  
 Per trasportare le informazioni sull'errore `GreetingFault` al client, intercettare la condizione di errore appropriata e generare una nuova eccezione <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> di tipo `GreetingFault` con un nuovo oggetto `GreetingFault` come argomento, come mostrato nell'esempio di codice seguente. Se il client è un'applicazione client WCF, questa eccezione viene considerata come un'eccezione gestita in cui il tipo è <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> di tipo `GreetingFault`.  
  
 [!code-csharp[FaultContractAttribute#5](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#5)]
 [!code-vb[FaultContractAttribute#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#5)]  
  
### <a name="sending-undeclared-faults"></a>Invio di errori non dichiarati  
 Inviare gli errori non dichiarati possono essere molto utili per diagnosticare rapidamente e debug dei problemi nelle applicazioni WCF, tuttavia, l'utilità come uno strumento di debug è limitato. Più in generale, quando si esegue il debug è consigliabile utilizzare la proprietà <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType>. Quando si imposta questo valore su True, i client considerano questi errori come eccezioni <xref:System.ServiceModel.FaultException%601> di tipo <xref:System.ServiceModel.ExceptionDetail>.  
  
> [!IMPORTANT]
>  Poiché le eccezioni gestite possono esporre informazioni interne dell'applicazione, se si imposta <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> oppure <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> a `true` può consentire ai client WCF di ottenere informazioni sulle eccezioni delle operazioni interne del servizio, incluse le informazioni informazioni personali o comunque riservate.  
>   
>  Di conseguenza, l'impostazione della proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> o della proprietà <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> su `true` è consigliabile solo come modalità temporanea di debug di un'applicazione di servizio. Inoltre, il codice WSDL di un metodo che restituisce in questo modo eccezioni gestite senza tuttavia gestirle non contiene il contratto dell'eccezione <xref:System.ServiceModel.FaultException%601> di tipo <xref:System.ServiceModel.ExceptionDetail>. I client devono prevedere la possibilità di un errore SOAP sconosciuto (restituito ai client WCF come <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> oggetti) per ottenere correttamente le informazioni di debug.  
  
 Per inviare un errore SOAP non dichiarato, generare un oggetto <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> (ovvero, non l'eccezione generica <xref:System.ServiceModel.FaultException%601>) e passare la stringa al costruttore. Questa funzionalità è esposta alle applicazioni client WCF come un'eccezione <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> eccezione in cui la stringa è disponibile chiamando il <xref:System.ServiceModel.FaultException%601.ToString%2A?displayProperty=nameWithType> metodo.  
  
> [!NOTE]
>  Se si dichiara un errore SOAP di tipo stringa e quindi si genera nel servizio l'eccezione corrispondente a tale errore come eccezione <xref:System.ServiceModel.FaultException%601> in cui il parametro di tipo è una stringa <xref:System.String?displayProperty=nameWithType>, il valore di tale stringa viene assegnato alla proprietà <xref:System.ServiceModel.FaultException%601.Detail%2A?displayProperty=nameWithType> e non è ottenibile tramite il metodo <xref:System.ServiceModel.FaultException%601.ToString%2A?displayProperty=nameWithType>.  
  
## <a name="handling-faults"></a>Gestione degli errori  
 Nei client WCF, gli errori SOAP che si verificano durante la comunicazione di interesse per le applicazioni client vengono generati come eccezioni gestite. Sebbene esistano molte eccezioni che possono verificarsi durante l'esecuzione di tutti i programmi, le applicazioni usando il modello di programmazione client WCF possono prevedere di gestire le eccezioni dei due seguenti come risultato di comunicazione.  
  
-   <xref:System.TimeoutException>  
  
-   <xref:System.ServiceModel.CommunicationException>  
  
 Gli oggetti <xref:System.TimeoutException> vengono generati quando un'operazione supera il periodo di timeout specificato.  
  
 Gli oggetti <xref:System.ServiceModel.CommunicationException> vengono generati quando nel servizio o nel client si verifica una condizione di errore di comunicazione risolvibile.  
  
 La classe <xref:System.ServiceModel.CommunicationException> dispone di due tipi derivati importanti: <xref:System.ServiceModel.FaultException> e il tipo <xref:System.ServiceModel.FaultException%601> generico.  
  
 Le eccezioni <xref:System.ServiceModel.FaultException> vengono generate quando un listener riceve un errore che non è previsto o non è specificato nel contratto dell'operazione. Ciò in genere si verifica quando durante il debug dell'applicazione la proprietà <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> del servizio è impostata su `true`.  
  
 Le eccezioni <xref:System.ServiceModel.FaultException%601> vengono generate nel client quando un errore specificato nel contratto dell'operazione viene ricevuto in risposta a un'operazione bidirezionale, ovvero a un metodo avente un attributo <xref:System.ServiceModel.OperationContractAttribute> in cui la proprietà <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> è impostata su `false`.  
  
> [!NOTE]
>  Quando un servizio WCF presenta il <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> oppure <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> impostata su `true` il client considera ciò come un identificatore non dichiarato <xref:System.ServiceModel.FaultException%601> di tipo <xref:System.ServiceModel.ExceptionDetail>. I client possono intercettare questo errore specifico oppure gestire l'errore in un blocco catch per l'eccezione <xref:System.ServiceModel.FaultException>.  
  
 In genere, solo le eccezioni <xref:System.ServiceModel.FaultException%601>, <xref:System.TimeoutException> e <xref:System.ServiceModel.CommunicationException> sono di interesse per client e servizi.  
  
> [!NOTE]
>  Naturalmente, si verificano anche eccezioni di altro tipo. Un esempio di eccezione imprevista è l'errore irreparabile <xref:System.OutOfMemoryException?displayProperty=nameWithType>. In genere, le applicazioni non devono intercettare tali metodi.  
  
### <a name="catch-fault-exceptions-in-the-correct-order"></a>Intercettazione delle eccezioni di errore nell'ordine corretto  
 Poiché la classe <xref:System.ServiceModel.FaultException%601> deriva dalla classe <xref:System.ServiceModel.FaultException> e la classe <xref:System.ServiceModel.FaultException> deriva dalla classe <xref:System.ServiceModel.CommunicationException> è importante intercettare queste eccezioni nell'ordine corretto. Se ad esempio si utilizza un blocco try/catch nel quale si intercetta prima l'eccezione <xref:System.ServiceModel.CommunicationException>, tutti gli errori SOAP, siano essi specificati o non specificati, vengono gestiti in tale blocco. Qualsiasi blocco catch successivo finalizzato alla gestione di eccezioni <xref:System.ServiceModel.FaultException%601> personalizzate non viene mai chiamato.  
  
 Si tenga presente che una stessa operazione può restituire un numero qualsiasi di errori specificati. Ogni errore è un tipo univoco e deve essere gestito in modo individuale.  
  
### <a name="handle-exceptions-when-closing-the-channel"></a>Gestione delle eccezioni in caso di chiusura del canale  
 La maggior parte della discussione precedente ha a che fare con errori inviati durante l'elaborazione di messaggi dell'applicazione, vale a dire, i messaggi inviati dal client in modo esplicito quando l'applicazione client chiama operazioni sull'oggetto client WCF.  
  
 Anche nel caso di oggetti locali, l'eliminazione dell'oggetto può generare oppure nascondere le eccezioni che si verificano durante il processo di riciclo. Un comportamento simile può verificarsi quando si utilizzano oggetti client WCF. La chiamata di un'operazione comporta l'invio di messaggi tramite una connessione stabilita. Se la connessione è già stata chiusa oppure non può essere chiusa in modo corretto, la chiusura del canale può generare eccezioni. Ciò si verifica anche se tutte le operazioni hanno eseguito la restituzione in modo corretto.  
  
 In genere i canali dell'oggetto client vengono chiusi in uno dei casi seguenti:  
  
-   Quando l'oggetto client WCF viene riciclato.  
  
-   Quando l'applicazione client chiama il metodo <xref:System.ServiceModel.ClientBase%601.Close%2A?displayProperty=nameWithType>.  
  
-   Quando l'applicazione client chiama il metodo <xref:System.ServiceModel.ICommunicationObject.Close%2A?displayProperty=nameWithType>.  
  
-   Quando l'applicazione client chiama un'operazione di chiusura di una sessione.  
  
 In tutti i casi, quando viene chiuso, il canale inizia a chiudere qualsiasi canale sottostante in grado di inviare messaggi allo scopo di supportare funzionalità complesse al livello applicazione. Ad esempio, quando un contratto richiede le sessioni, un'associazione tenta di stabilire una sessione scambiando messaggi con il canale del servizio fino a stabilire una sessione. Quando il canale viene chiuso, il canale della sessione sottostante comunica al servizio che la sessione è terminata. In questo caso, se il canale risulta interrotto, chiuso o comunque inutilizzabile (ad esempio quando si scollega un cavo di rete), il canale client non può comunicare al canale del servizio che la sessione è terminata e pertanto è possibile che venga generata un'eccezione.  
  
### <a name="abort-the-channel-if-necessary"></a>Interruzione del canale  
 Poiché anche la chiusura del canale può generare eccezioni, oltre a intercettare le eccezioni nell'ordine corretto è consigliabile interrompere il canale utilizzato per effettuare la chiamata al blocco catch.  
  
 Se l'errore trasporta informazioni sull'errore specifiche di un'operazione ed esiste la possibilità che tali informazioni possano essere utilizzate da terzi, non occorre interrompere il canale. Si tratta tuttavia di un caso raro. In tutti gli altri casi è consigliabile interrompere il canale. Per un esempio che illustra tutti questi punti, vedere [previsto eccezioni](../../../docs/framework/wcf/samples/expected-exceptions.md).  
  
 Nell'esempio di codice seguente viene mostrato come gestire le eccezioni di errore SOAP in un'applicazione client di base, sia nel caso di errore dichiarato sia nel caso di errore non dichiarato.  
  
> [!NOTE]
>  Questo esempio di codice non utilizza il costrutto `using`. Poiché la chiusura di canali può generare eccezioni, è consigliabile che le applicazioni creano un utilizzo di prima e quindi l'aperto, client WCF e chiudere il client WCF nello stesso blocco try. Per informazioni dettagliate, vedere [panoramica dei Client WCF](../../../docs/framework/wcf/wcf-client-overview.md) e [evitare problemi con l'istruzione Using](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).  
  
 [!code-csharp[FaultContractAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/client.cs#3)]
 [!code-vb[FaultContractAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/client.vb#3)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.FaultException>  
 <xref:System.ServiceModel.FaultException%601>  
 <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>  
 [Eccezioni previste](../../../docs/framework/wcf/samples/expected-exceptions.md)  
 [Prevenzione dei problemi con l'istruzione Using](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)

---
title: Scelta di un codificatore di messaggi
ms.date: 03/30/2017
ms.assetid: 2204d82d-d962-4922-a79e-c9a231604f19
ms.openlocfilehash: d93d7039d034262cd47edd437d5d7d8d63890f02
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635770"
---
# <a name="choose-a-message-encoder"></a>Scegliere un codificatore di messaggiChoose a Message Encoder

In questo articolo vengono illustrati i criteri per la scelta tra i codificatori di messaggi inclusi in Windows Communication Foundation (WCF): binario, testo e mTOM (Message Transmission Optimization Mechanism).  
  
 In WCF si specifica come trasferire i dati attraverso una rete tra endpoint tramite *un'associazione*, costituita da una sequenza di elementi di *associazione.* Un codificatore di messaggi è rappresentato da un elemento di associazione di codifica dei messaggi nello stack dell'associazione. Un'associazione include elementi facoltativi di associazione del protocollo, ad esempio un elemento di associazione di sicurezza o un elemento di associazione di messaggistica affidabile, un elemento di associazione di codifica dei messaggi obbligatorio e un elemento di associazione di trasporto obbligatorio.  
  
 L'elemento di associazione di codifica dei messaggi si trova sotto gli elementi facoltativi binding del protocollo e sopra l'elemento associazione del trasporto obbligatorio. Sul lato in uscita, un codificatore di messaggi serializza <xref:System.ServiceModel.Channels.Message> in uscita e lo passa al trasporto. Sul lato in ingresso, un codificatore di messaggi riceve il formato serializzato di un <xref:System.ServiceModel.Channels.Message> dal trasporto e lo passa al livello di protocollo superiore, se presente. In caso contrario, lo passa all'applicazione.  
  
 In caso di connessione a un client o a un server preesistente, potrebbe non essere possibile scegliere una particolare codifica dei messaggi dato che questi devono essere codificati come previsto dall'altro lato. Tuttavia, se si scrive un servizio WCF, è possibile esporre il servizio tramite più endpoint, ognuno dei quali usa una codifica dei messaggi diversa. In tal modo i client possono scegliere la migliore codifica per conversare con il servizio sull'endpoint, e possono avere la flessibilità di scegliere la migliore codifica per se stessi. L'utilizzo di più endpoint consente anche di combinare i vantaggi di codifiche del messaggio diverse con altri elementi di associazione.  
  
## <a name="system-provided-encoders"></a>Codificatori forniti dal sistema  
 WCF include tre codificatori di messaggi, rappresentati dalle tre classi seguenti:WCF includes three messageencoders, which are represented by the following three classes:  
  
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>, il codificatore dei messaggi di testo, supporta codifica XML semplice e codifica SOAP. La modalità di codifica XML semplice del codificatore dei messaggi di testo è chiamata POX (Plain Old XML) per distinguerla dalla codifica SOAP basata su testo. Per abilitare POX, impostare la proprietà <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement.MessageVersion%2A> su <xref:System.ServiceModel.Channels.MessageVersion.None%2A>. Usare il codificatore di messaggi di testo per interagire con endpoint non WCF.  
  
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>, il codificatore di messaggi binari, utilizza un formato binario compatto ed è ottimizzato per la comunicazione WCF per la comunicazione WCF e pertanto non è interoperabile. Questo è anche il codificatore più performante di tutti i codificatori WCF fornisce.  
  
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>, l'elemento di associazione, specifica la codifica dei caratteri e la versione dei messaggi che utilizzano MTOM. MTOM è una tecnologia efficiente per la trasmissione di dati binari nei messaggi di WCF. Il codificatore MTOM cerca di creare un equilibrio tra efficienza e interoperabilità. La codifica MTOM trasmette la maggior parte del codice XML in formato testo, ma ottimizza grandi blocchi di dati binari trasmettendoli senza introdurre modifiche e senza convertirli in formato testo. In termini di efficienza, tra i codificatori WCF fornisce, MTOM è tra il testo (il più lento) e binario (il più veloce).  
  
## <a name="how-to-choose-a-message-encoder"></a>Come scegliere un codificatore di messaggi  
 Nella tabella seguente vengono descritti i fattori comuni utilizzati per scegliere un codificatore di messaggi. Dare la priorità ai fattori che sono importanti per l'applicazione, quindi scegliere i codificatori più efficienti per tali fattori. Tenere anche conto di eventuali fattori aggiuntivi non elencati in questa tabella e qualsiasi codificatore di messaggi personalizzato che può essere richiesto nell'applicazione.  
  
|Fattore|Descrizione|Codificatori che supportano questo fattore|  
|------------|-----------------|---------------------------------------|  
|Set di caratteri supportati|<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>e <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> supporta solo le codifiche UTF8 e UTF16 Unicode (*big-endian* e *little-endian*). Se sono richieste altre codifiche, ad esempio UTF7 o ASCII, deve essere utilizzato un codificatore personalizzato. Per un codificatore personalizzato di esempio, vedere [Custom Message Encoder](https://docs.microsoft.com/dotnet/framework/wcf/samples/custom-message-encoder-custom-text-encoder).|Testo|  
|Ispezione|L'ispezione è la capacità di esaminare i messaggi durante la trasmissione. Le codifiche di testo, con o senza l'utilizzo di SOAP, consentono a numerose applicazioni di ispezionare e analizzare i messaggi senza utilizzare strumenti specializzati. L'uso della sicurezza di trasferimento, a livello di messaggio o di trasporto, influisce sulla capacità di controllare i messaggi. La riservatezza evita che un messaggio venga esaminato, mentre l'integrità lo protegge dalle modifiche.|Testo|  
|Affidabilità|L'affidabilità è la flessibilità di un codificatore nei confronti degli errori di trasmissione. L'affidabilità può essere fornita anche a livello di messaggio, trasporto o applicazione. Tutti i codificatori WCF standard presuppongono che un altro livello fornisca affidabilità. Il codificatore non ha grandi capacità di recupero da un errore di trasmissione.|nessuno|  
|Semplicità|La semplicità rappresenta la facilità con cui è possibile creare codificatori e decodificatori per una specifica di codifica. Le codifiche di testo sono particolarmente vantaggiose per la semplicità. La codifica di testo POX, inoltre, ha anche il vantaggio che non richiede supporto per l'elaborazione di SOAP.|Testo (POX)|  
|Dimensione|La codifica determina la quantità di sovraccarico imposto sul contenuto. La dimensione dei messaggi codificati è direttamente correlata alla velocità effettiva massima delle operazioni del servizio. Le codifiche binarie in genere sono più compatte di quelle di testo. Quando la dimensione del messaggio è importante, prendere in considerazione anche la compressione del contenuto del messaggio durante la codifica. La compressione aumenta tuttavia gli oneri di elaborazione sia per il mittente che per il destinatario del messaggio.|Binary|  
|Streaming|Il flusso consente alle applicazioni di iniziare a elaborare un messaggio prima che sia arrivato tutto. Per utilizzare in modo efficiente un flusso, è necessario che i dati importanti di un messaggio siano disponibili all'inizio del messaggio, affinché l'applicazione ricevente non debba attenderne l'arrivo. Le applicazioni che utilizzano il trasferimento tramite flussi, inoltre, devono organizzare i dati nel messaggio in modo incrementale affinché il contenuto non abbia dipendenze in avanti. In molti casi, è necessario trovare un compromesso tra l'utilizzo di un flusso e la riduzione massima delle dimensioni di trasferimento di quel contenuto.|nessuno|  
|Supporto di strumenti di terze parti|Le aree di supporto per una codifica comprendono sviluppo e diagnosi. Gli sviluppatori di terze parti hanno investito massicciamente in librerie e toolkit per la gestione dei messaggi codificati nel formato POX.|Testo (POX)|  
|Interoperabilità|Questo fattore si riferisce alla capacità di un codificatore WCF di interagire con servizi non WCF.|Testo<br /><br /> MTOM (parziale)|  
  
Nota: quando si utilizza il codificatore binario, l'utilizzo dell'impostazione IgnoreWhitespace durante la creazione di un elemento XMLReader non avrà effetto.  Ad esempio, se si effettua quanto riportato di seguito in un'operazione del servizio:  

```csharp
public void OperationContract(XElement input)
{
    Console.WriteLine("{0}", input.Value);
    int counter = 0;
    var xreader = input.CreateReader();
    var reader = XmlReader.Create(xreader, new XmlReaderSettings() { IgnoreWhitespace = true });
    while (reader.Read())
    {
        counter++;
    }

    Console.WriteLine("Read {0} lines with reader", counter);
}
```  
  
L'impostazione IgnoreWhitespace viene ignorata.  
  
## <a name="compression-and-the-binary-encoder"></a>Compressione e codificatore binario

A partire da WCF 4.5, il codificatore binario WCF aggiunge il supporto per la compressione. Questo consente di utilizzare l'algoritmo gzip/deflate per inviare messaggi compressi da un client WCF, nonché rispondere con messaggi compressi da un servizio WCF self-hosted. Questa funzionalità consente la compressione sui trasporti TCP e HTTP. Un servizio WCF ospitato da IIS può sempre essere abilitato per l'invio di risposte compresse configurando il server host di IIS. Il tipo di compressione è configurato con la proprietà <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement.CompressionFormat%2A?displayProperty=nameWithType>. Questa proprietà è impostata su uno dei valori dell'enumerazione <xref:System.ServiceModel.Channels.CompressionFormat?displayProperty=nameWithType>:

- <xref:System.ServiceModel.Channels.CompressionFormat.Deflate>
- <xref:System.ServiceModel.Channels.CompressionFormat.GZip>
- <xref:System.ServiceModel.Channels.CompressionFormat.None>
  
Poiché questa proprietà è esposta solo su binaryMessageEncodingBindingElement, sarà necessario creare un'associazione personalizzata simile alla seguente per utilizzare questa funzionalità:Since this property is only exposed on the binaryMessageEncodingBindingElement, you will need to create a custom binding like the following to use this feature:

 ```xml
 <customBinding>
   <binding name="BinaryCompressionBinding">
     <binaryMessageEncoding compressionFormat ="GZip" />
     <httpTransport />
  </binding>
</customBinding>
 ```

Sia il client che il servizio devono accettare di inviare e ricevere messaggi compressi e pertanto la proprietà compressionFormat deve essere configurata sull'elemento binaryMessageEncoding sia nel client che nel servizio. Se il servizio o il client non è configurato per la compressione, viene generata un'eccezione ProtocolException se il servizio o il client non è configurato, ma l'altro lato lo è. L'abilitazione della compressione deve essere attentamente considerata. La compressione è particolarmente utile se la larghezza di banda della rete costituisce un collo di bottiglia. Nel caso in cui la CPU sia un collo di bottiglia, la compressione diminuirà la velocità effettiva. È necessario effettuare prove appropriate in un ambiente simulato per verificare eventuali vantaggi per l'applicazione  
  
## <a name="see-also"></a>Vedere anche

- [Associazioni](../../../../docs/framework/wcf/feature-details/bindings.md)

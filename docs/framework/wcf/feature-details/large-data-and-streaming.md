---
title: Dati di grandi dimensioni e flussi
ms.date: 03/30/2017
ms.assetid: ab2851f5-966b-4549-80ab-c94c5c0502d2
ms.openlocfilehash: 21993f230b19a76020807e1f17bd6256f2ee0b1c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84586325"
---
# <a name="large-data-and-streaming"></a>Dati di grandi dimensioni e flussi

Windows Communication Foundation (WCF) è un'infrastruttura di comunicazione basata su XML. Poiché i dati XML sono comunemente codificati nel formato di testo standard definito nella [specifica XML 1,0](https://www.w3.org/TR/REC-xml/), gli sviluppatori e i progettisti di sistemi connessi sono in genere preoccupati per il footprint di rete (o le dimensioni) dei messaggi inviati attraverso la rete e la codifica del codice XML basata su testo pone particolari difficoltà per il trasferimento efficiente di dati binari.  
  
## <a name="basic-considerations"></a>Considerazioni di base  
 Per fornire informazioni di base sulle informazioni seguenti per WCF, in questa sezione vengono illustrate alcune considerazioni e considerazioni generali relative a codifiche, dati binari e flussi che in genere si applicano alle infrastrutture di sistemi connessi.  
  
### <a name="encoding-data-text-vs-binary"></a>Codifica dei dati: testo o formato binario  
 Gli sviluppatori hanno espresso preoccupazioni comuni, tra cui la percezione che il codice XML generi un notevole sovraccarico se paragonato ai formati binari a causa della natura ripetitiva dei tag di inizio e fine, l'osservazione che la codifica di valori numerici sia significativamente più grande poiché vengono espressi in valori di testo, e l'opinione che i dati binari non possono essere espressi in modo efficiente perché devono essere codificati appositamente per essere incorporati in un formato di testo.  
  
 Sebbene molte di queste e altre preoccupazioni simili siano valide, la differenza effettiva tra messaggi codificati in formato di testo-XML in un ambiente di servizi Web XML e messaggi con codifica binaria in un ambiente legacy di chiamata a procedura remota (RPC) è spesso molto meno significativa di quanto la considerazione iniziale possa suggerire.  
  
 Mentre i messaggi con codifica in formato testo-XML sono messaggi leggibili, i messaggi binari sono spesso incomprensibili e difficili da decodificare senza strumenti appropriati. Questa differenza di leggibilità porta a trascurare il fatto che i messaggi binari spesso contengono metadati inline nel payload, con conseguente aumento del sovraccarico, proprio come con i messaggi di testo-XML. Questa considerazione è particolarmente valida per i formati binari destinati a fornire funzionalità a regime di controllo libero e di chiamata dinamica.  
  
 Tuttavia, i formati binari in genere contengono tali informazioni sui metadati descrittivi in un'intestazione, che dichiara anche il layout dei dati per i record di dati seguenti. Il payload segue quindi questa dichiarazione del blocco di metadati comuni con un ulteriore sovraccarico minimo. Diversamente, il formato XML racchiude i singoli elementi di dati in un elemento o attributo in modo che i metadati che li racchiudono vengano inclusi ripetitivamente per ogni oggetto del payload serializzato. Di conseguenza, le dimensioni di un singolo oggetto del payload serializzato sono simili se si confronta il testo alle rappresentazioni binarie perché alcuni metadati descrittivi devono essere espressi per entrambi, anche se il formato binario trae vantaggio dalla descrizione dei metadati condivisa con ogni oggetto del payload aggiuntivo che viene trasferito a causa del sovraccarico complessivo inferiore.  
  
 In ogni modo, per certi tipi di dati, quali i numeri, potrebbe essere svantaggioso utilizzare rappresentazioni numeriche binarie di dimensioni fisse, ad esempio un tipo decimale a 128 bit anziché il testo normale, poiché la rappresentazione in testo normale potrebbe essere di molto inferiore. Anche i dati di testo potrebbero trarre vantaggio in termini di dimensioni dalle opzioni di codifica in testo-XML tipicamente più flessibili, mentre alcuni formati binari potrebbero impostare come valore predefinito il formato Unicode a 16 bit o anche a 32 bit, che non può essere applicato al formato XML binario di .NET.  
  
 Di conseguenza, la scelta tra formato testo e formato binario non può essere basata semplicemente sul fatto che i messaggi binari sono sempre più piccoli dei messaggi in formato testo-XML.  
  
 Un chiaro vantaggio dei messaggi in formato testo-XML è che sono basati su standard e offrono la più ampia scelta di opzioni di interoperabilità e supporto di piattaforme. Per ulteriori informazioni, vedere la sezione "codifiche" più avanti in questo argomento.  
  
### <a name="binary-content"></a>Contenuto binario  
 Un'area in cui le codifiche binarie sono superiori alle codifiche basate su testo, per quanto concerne la dimensione del messaggio risultante, è costituita dai dati binari di grandi dimensioni quali immagini, video, clip audio o qualsiasi altro tipo di dati opachi binari che devono essere scambiati tra servizi e utenti. Per adattare questi tipi di dati nel testo XML, l'approccio comune è di codificarli utilizzando la codifica Base64.  
  
 In una stringa con codifica Base64, ogni carattere rappresenta 6 bit dei dati originali a 8 bit, con un conseguente rapporto di codifica-sovraccarico di 4:3 per Base64, senza contare i caratteri aggiuntivi della formattazione (ritorno a capo/avanzamento riga) che vengono normalmente aggiunti per convenzione. Mentre l'importanza delle differenze tra le codifiche XML e binaria dipende in genere dallo scenario, un aumento della dimensione di oltre il 33% durante la trasmissione di un payload da 500 MB non è in genere accettabile.  
  
 Per evitare questo sovraccarico della codifica, lo standard MTOM (Message Transmission Optimization Mechanism) consente di esternalizzare i dati di grandi dimensioni contenuti in un messaggio per trasportarli con il messaggio in forma di dati binari senza alcuna codifica speciale. Con MTOM, i messaggi vengono scambiati in modo analogo ai messaggi di posta elettronica Simple Mail Transfer Protocol (SMTP) con allegati o contenuto incorporato (immagini e altro contenuto incorporato); I messaggi MTOM vengono inclusi nel pacchetto come sequenze MIME multipart/correlate con la parte radice che è il messaggio SOAP effettivo.  
  
 Un messaggio SOAP MTOM viene modificato rispetto alla versione non codificata in modo che tag di elemento speciali, riferiti alle relative parti MIME, sostituiscano gli elementi originali nel messaggio che conteneva dati binari. Di conseguenza, il messaggio SOAP fa riferimento al contenuto binario puntando alle parti MIME inviate con il messaggio stesso, ma contiene solo dati di testo XML. Poiché questo modello è perfettamente allineato al diffuso modello SMTP, sono disponibili numerosi strumenti di supporto per codificare e decodificare i messaggi MTOM su molte piattaforme. Questa scelta diventa quindi estremamente interoperativa.  
  
 Lo standard MTOM, come la codifica Base64, comporta un sovraccarico indispensabile per il formato MIME, pertanto i vantaggi dell'utilizzo di MTOM sono visibili solo quando la dimensione dei dati binari supera 1 KB. A causa del sovraccarico, i messaggi con codifica MTOM potrebbero essere più grandi dei messaggi con codifica Base64 per i dati binari, se il payload binario rimane sotto tale soglia. Per ulteriori informazioni, vedere la sezione "codifiche" più avanti in questo argomento.  
  
### <a name="large-data-content"></a>Contenuto costituito da dati di grandi dimensioni  
 A parte il footprint in rete, il payload precedentemente menzionato di 500 MB crea un significativo problema locale anche per il servizio e il client. Per impostazione predefinita, WCF elabora i messaggi in *modalità di memorizzazione nel buffer*. Questo vuole dire che l'intero contenuto di un messaggio è presente in memoria prima di essere inviato o dopo essere stato ricevuto. Sebbene questa strategia si riveli valida per la maggior parte degli scenari e necessaria per le funzionalità di messaggistica quali firme digitali e recapito affidabile, i messaggi di grandi dimensioni potrebbero esaurire le risorse di un sistema.  
  
 La strategia adatta per gestire ingenti payload consiste nella trasmissione di flussi. Anche se i messaggi, in particolar modo quelli espressi in formato XML, sono comunemente considerati pacchetti di dati relativamente compatti, un messaggio può avere dimensioni pari a più gigabyte ed essere più simile a un flusso di dati continuo, anziché a un pacchetto di dati. Quando i dati vengono trasferiti in modalità flusso anziché in modalità di memorizzazione nel buffer, il mittente rende disponibile il contenuto del corpo del messaggio al destinatario sotto forma di flusso e l'infrastruttura di messaggistica inoltra continuamente i dati dal mittente al destinatario, man mano che sono disponibili.  
  
 Lo scenario più comune nel quale si verificano trasferimenti di contenuto costituito da dati di grandi dimensioni è rappresentato dai trasferimenti di oggetti dati binari che:  
  
- Non possono essere facilmente suddivisi in una sequenza di messaggi.  
  
- Devono essere recapitati in maniera tempestiva.  
  
- Non sono disponibili per intero al momento dell'avvio del trasferimento.  
  
 Per i dati che non presentano questi vincoli, in genere è consigliabile inviare sequenze di messaggi nell'ambito di una sessione, anziché un solo grande messaggio. Per ulteriori informazioni, vedere la sezione "flusso di dati" più avanti in questo argomento.  
  
 Quando si inviano grandi quantità di dati, è necessario impostare l' `maxAllowedContentLength` impostazione IIS (per ulteriori informazioni, vedere la pagina relativa alla [configurazione dei limiti delle richieste IIS](https://docs.microsoft.com/iis/configuration/system.webServer/security/requestFiltering/requestLimits/)) e l'impostazione dell'associazione, `maxReceivedMessageSize` ad esempio [System. ServiceModel. BasicHttpBinding. MaxReceivedMessageSize](xref:System.ServiceModel.HttpBindingBase.MaxReceivedMessageSize%2A) o <xref:System.ServiceModel.NetTcpBinding.MaxReceivedMessageSize%2A> . `maxAllowedContentLength`Per impostazione predefinita, la proprietà è 28,6 MB e `maxReceivedMessageSize` per impostazione predefinita la proprietà è 64KB.  
  
## <a name="encodings"></a>Codifiche  
 Una *codifica* definisce un set di regole relative alla modalità di presentazione dei messaggi in transito. Un *codificatore* implementa tale codifica ed è responsabile sul lato mittente, per trasformare un in memoria in <xref:System.ServiceModel.Channels.Message> un flusso di byte o in un buffer di byte che può essere inviato attraverso la rete. Sul lato destinatario, il codificatore trasforma una sequenza di byte in un messaggio in memoria.  
  
 WCF include tre codificatori e consente di scrivere e inserire codificatori personalizzati, se necessario.  
  
 Per impostazione predefinita, ognuna delle associazioni standard include un codificatore preconfigurato, pertanto le associazioni con il prefisso Net* utilizzano il codificatore binario (inclusa la classe <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>) mentre le classi <xref:System.ServiceModel.BasicHttpBinding> e <xref:System.ServiceModel.WSHttpBinding> utilizzano il codificatore del messaggio di testo (mediante la classe <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>).  
  
|Elemento di associazione del codificatore|Descrizione|  
|-----------------------------|-----------------|  
|<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>|Il codificatore del messaggio di testo è il codificatore predefinito per tutte le associazioni basate su HTTP e rappresenta la scelta giusta per tutte le associazioni personalizzate in cui l'interoperabilità ha la massima priorità. Questo codificatore legge e scrive messaggi di testo SOAP 1.1/SOAP 1.2 standard senza gestire in modo particolare i dati binari. Se la <xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType> proprietà di un messaggio è impostata su <xref:System.ServiceModel.Channels.MessageVersion.None?displayProperty=nameWithType> , il wrapper SOAP envelope viene omesso dall'output e viene serializzato solo il contenuto del corpo del messaggio.|  
|<xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>|Il codificatore dei messaggi MTOM è un codificatore di testo che implementa una gestione speciale per i dati binari e, per impostazione predefinita, non viene utilizzato nelle associazioni standard poiché è un'utilità di ottimizzazione che valuta caso per caso. Se il messaggio contiene dati binari che superano la soglia entro la quale la codifica MTOM produce un vantaggio, i dati vengono esternalizzati in una parte MIME che segue l'envelope del messaggio. Vedere Attivazione di MTOM più avanti in questa sezione.|  
|<xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>|Il codificatore di messaggi binario è il codificatore predefinito per le associazioni NET * e la scelta appropriata quando entrambe le parti di comunicazione sono basate su WCF. Il codificatore di messaggi binari utilizza il formato XML binario di .NET, una rappresentazione binaria specifica per Microsoft degli Infoset (set di informazioni XML) che generalmente produce un footprint più piccolo rispetto alla rappresentazione XML 1.0 equivalente e codifica dati binari come un flusso di byte.|  
  
 La codifica dei messaggi di testo è in genere la scelta migliore per qualsiasi percorso di comunicazione che richiede interoperabilità, mentre la codifica dei messaggi binari è la scelta migliore per qualsiasi altro percorso di comunicazione. La codifica dei messaggi binari in genere produce messaggi di dimensioni minori se confrontate al testo per un solo messaggio e progressivamente sempre minori nell'arco di una sessione di comunicazione. A differenza della codifica di testo, la codifica binaria non deve gestire i dati binari in modo speciale, come nel caso della codifica Base64, ma rappresenta byte per byte.  
  
 Se la soluzione in uso non richiede l'interoperabilità, ma si desidera comunque utilizzare il trasporto HTTP, è possibile comporre <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> in un'associazione personalizzata che utilizza la classe <xref:System.ServiceModel.Channels.HttpTransportBindingElement> per il trasporto. Se alcuni client del servizio richiedono l'interoperabilità, è consigliabile esporre endpoint paralleli per i quali siano abilitate le scelte di codifica e trasporto appropriate per i rispettivi client.  
  
### <a name="enabling-mtom"></a>Attivazione di MTOM  
 Quando l'interoperabilità è essenziale e devono essere inviati dati binari di grandi dimensioni, la codifica dei messaggi MTOM è la strategia di codifica alternativa che può essere abilitata sulle associazioni <xref:System.ServiceModel.BasicHttpBinding> o <xref:System.ServiceModel.WSHttpBinding> standard impostando la rispettiva proprietà `MessageEncoding` su <xref:System.ServiceModel.WSMessageEncoding.Mtom> o componendo <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> in una classe <xref:System.ServiceModel.Channels.CustomBinding>. Nell'esempio di codice riportato di seguito, estratto dall'esempio di [codifica MTOM](../samples/mtom-encoding.md) , viene illustrato come abilitare MTOM nella configurazione.  
  
```xml  
<system.serviceModel>  
     …  
    <bindings>  
      <wsHttpBinding>  
        <binding name="ExampleBinding" messageEncoding="Mtom"/>  
      </wsHttpBinding>  
    </bindings>  
     …  
</system.serviceModel>  
```  
  
 Come indicato in precedenza, la decisione di utilizzare la codifica MTOM dipende dal volume dei dati che si intende inviare. Inoltre, poiché MTOM è abilitato a livello dell'associazione, l'attivazione di MTOM influisce su tutte le operazioni su un endpoint specificato.  
  
 Poiché il codificatore MTOM genera sempre un messaggio MIME/multipart con codifica MTOM indipendentemente dal fatto che i dati binari vengano o meno esternalizzati, è in genere consigliabile attivare MTOM solo per gli endpoint che scambiano messaggi contenenti più di 1 KB di dati binari. Inoltre, i contratti di servizio progettati per l'utilizzo con gli endpoint abilitati per MTOM devono, quando possibile, essere vincolati a specificare tali operazioni di trasferimento dati. La relativa funzionalità di controllo deve essere basata su un contratto separato. Questa regola che prevede l'abilitazione esclusiva di MTOM si applica solo a messaggi inviati tramite un endpoint abilitato per MTOM; il codificatore MTOM può decodificare e analizzare anche i messaggi non MTOM in arrivo.  
  
 L'utilizzo del codificatore MTOM è conforme a tutte le altre funzionalità di WCF. Si noti che in alcuni casi non è possibile osservare questa regola, ad esempio quando è richiesto il supporto della sessione.  
  
### <a name="programming-model"></a>Modello di programmazione  
 Indipendentemente da quale dei tre codificatori incorporati viene utilizzato nell'applicazione, l'esperienza di programmazione è identica per quanto concerne il trasferimento di dati binari. La differenza risiede nel modo in cui WCF gestisce i dati in base ai relativi tipi di dati.  
  
```csharp
[DataContract]  
class MyData  
{  
    [DataMember]  
    byte[] binaryBuffer;  
    [DataMember]  
    string someStringData;  
}
```  
  
 Se si utilizza MTOM, il contratto dati precedente viene serializzato secondo le regole seguenti:  
  
- Se `binaryBuffer` non è `null` e contiene abbastanza dati per giustificare il sovraccarico di esternalizzazione di MTOM (intestazioni MIME e così via) rispetto alla codifica Base64, i dati vengono esternalizzati e trasportati con il messaggio come una parte MIME binaria. Se la soglia non viene superata, i dati vengono codificati con il formato Base64.  
  
- La stringa (e tutti gli altri tipi non binari) viene sempre rappresentata come una stringa nel corpo del messaggio, indipendentemente dalle dimensioni.  
  
 Sia che si utilizzi un contratto dati esplicito, come illustrato nell'esempio precedente, un elenco di parametri in un'operazione, contratti dati annidati o si trasferisca un oggetto contratto dati in una raccolta, l'effetto sulla codifica MTOM è lo stesso. Le matrici di byte sono sempre candidate per l'ottimizzazione e vengono ottimizzate se le soglie di ottimizzazione vengono soddisfatte.  
  
> [!NOTE]
> Non utilizzare tipi derivati da <xref:System.IO.Stream?displayProperty=nameWithType> all'interno di contratti dati. I dati del flusso devono essere comunicati utilizzando il modello di flusso, illustrato nella sezione "Flusso di dati" seguente.  
  
## <a name="streaming-data"></a>Flusso di dati  
 Quando si dispone di una grande quantità di dati da trasferire, la modalità di trasferimento in flusso in WCF rappresenta un'alternativa possibile al comportamento predefinito di memorizzazione nel buffer ed elaborazione dei messaggi in memoria.  
  
 Come indicato in precedenza, attivare il flusso solo per i messaggi di grandi dimensioni (con contenuto di testo o binario) se i dati non possono essere segmentati, se il messaggio deve essere recapitato tempestivamente o se i dati non sono ancora completamente disponibili quando ha inizio il trasferimento.  
  
### <a name="restrictions"></a>Restrizioni  
 Non è possibile usare un numero significativo di funzionalità WCF quando è abilitato il flusso:  
  
- Non è possibile applicare firme digitali al corpo del messaggio poiché richiedono il calcolo di un hash sull'intero contenuto del messaggio. Con il flusso, il contenuto non è completamente disponibile quando le intestazioni del messaggio vengono create e inviate e, pertanto, non è possibile calcolare una firma digitale.  
  
- Per verificare che i dati siano stati ricostruiti correttamente, la crittografia dipende dalle firme digitali.  
  
- Le sessioni affidabili devono memorizzare nel buffer i messaggi inviati sul client per riconsegnare un messaggio qualora si perda durante il trasferimento e devono trattenere i messaggi nel servizio prima di passarli all'implementazione del servizio per preservare l'ordine dei messaggi nel caso in cui i messaggi vengano ricevuti fuori sequenza.  
  
 A causa di questi vincoli funzionali, è possibile utilizzare solo opzioni di sicurezza a livello di trasporto per il flusso e non è possibile attivare sessioni affidabili. Il flusso è disponibile solo con le associazioni definite dal sistema seguenti:  
  
- <xref:System.ServiceModel.BasicHttpBinding>  
  
- <xref:System.ServiceModel.NetTcpBinding>  
  
- <xref:System.ServiceModel.NetNamedPipeBinding>  
  
- <xref:System.ServiceModel.WebHttpBinding>  
  
 Perché i trasporti sottostanti di <xref:System.ServiceModel.NetTcpBinding> e <xref:System.ServiceModel.NetNamedPipeBinding> possono contare sul recapito affidabile inerente e sul supporto della sessione basato sulla connessione, a differenza di HTTP, in pratica questi vincoli influiscono minimamente su queste due associazioni.  
  
 Il flusso non è disponibile con il trasporto dell'accodamento messaggi (MSMQ) e pertanto non può essere utilizzato con la classe <xref:System.ServiceModel.NetMsmqBinding> o <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>. Il trasporto dell'accodamento messaggi supporta solo i trasferimenti di dati memorizzati nel buffer con dimensioni di messaggio vincolate, mentre tutti gli altri trasporti non presentano pressoché alcun limite alle dimensioni dei messaggi per la maggior parte degli scenari.  
  
 Il flusso non è disponibile neanche in caso di utilizzo del trasporto del canale peer, pertanto non è disponibile con <xref:System.ServiceModel.NetPeerTcpBinding>.  
  
#### <a name="streaming-and-sessions"></a>Sessioni e flusso  
 È possibile ricevere un comportamento imprevisto quando viene eseguito il flusso delle chiamate con un'associazione basata sulla sessione. Tutte le chiamate del flusso sono eseguite tramite un solo canale (il canale del datagramma) che non supporta sessioni anche se l'associazione utilizzata è configurata per utilizzare sessioni. Se più client effettuano un flusso di chiamate allo stesso oggetto servizio con un'associazione basata sulla sessione e la modalità di concorrenza dell'oggetto servizio è impostata su singola e la modalità di contesto dell'istanza è impostata su PerSession, tutte le chiamate devono transitare attraverso il canale del datagramma, pertanto viene elaborata una sola chiamata alla volta. È possibile che si verifichi il timeout di uno o più client. È possibile risolvere questo problema impostando la modalità di contesto dell'istanza dell'oggetto servizio su PerCall o Concurrency su multiple.  
  
> [!NOTE]
> In questo caso, MaxConcurrentSessions non ha effetto perché è disponibile una sola "sessione".  
  
### <a name="enabling-streaming"></a>Abilitazione del flusso  
 È possibile abilitare il flusso nei modi seguenti:  
  
- Inviare e accettare richieste in modalità flusso, e accettare e restituire risposte in modalità di memorizzazione nel buffer (<xref:System.ServiceModel.TransferMode.StreamedRequest>).  
  
- Inviare e accettare richieste in modalità di memorizzazione nel buffer, e accettare e restituire risposte in modalità flusso (<xref:System.ServiceModel.TransferMode.StreamedResponse>).  
  
- Inviare e ricevere richieste e risposte in modalità flusso in entrambe le direzioni (<xref:System.ServiceModel.TransferMode.Streamed>).  
  
 È possibile disabilitare il flusso impostando la modalità di trasferimento su <xref:System.ServiceModel.TransferMode.Buffered>, ovvero l'impostazione predefinita per tutte le associazioni. Nel codice seguente viene illustrato come impostare la modalità di trasferimento nella configurazione.  
  
```xml  
<system.serviceModel>  
     …  
    <bindings>  
      <basicHttpBinding>  
        <binding name="ExampleBinding" transferMode="Streamed"/>  
      </basicHttpBinding>  
    </bindings>  
     …  
</system.serviceModel>  
```  
  
 Quando si crea un'istanza dell'associazione nel codice, è necessario impostare la rispettiva proprietà `TransferMode` dell'associazione (o l'elemento di associazione del trasporto per la composizione di un'associazione personalizzata) su uno dei valori indicati precedentemente.  
  
 È possibile attivare il flusso per le richieste e le risposte o per entrambe le direzioni in modo indipendente su una delle parti in comunicazione senza influire sulla funzionalità. Tuttavia, è necessario presupporre sempre che la dimensione dei dati trasferita sia talmente significativa da giustificare l'abilitazione del flusso su entrambi gli endpoint di un collegamento di comunicazione. Per la comunicazione multipiattaforma in cui uno degli endpoint non è implementato con WCF, la possibilità di usare lo streaming dipende dalle funzionalità di streaming della piattaforma. Un'altra eccezione rara potrebbe essere un scenario incentrato sul consumo di memoria dove un client o un servizio devono ridurre al minimo il working set e possono permettersi solo buffer di piccole dimensioni.  
  
### <a name="enabling-asynchronous-streaming"></a>Abilitazione del flusso asincrono  
 Per abilitare il flusso asincrono, aggiungere il comportamento dell'endpoint <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior> all'host del servizio e impostare la relativa proprietà <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior.AsynchronousSendEnabled%2A> su `true`. Inoltre è stata aggiunta la funzionalità di un vero flusso asincrono sul lato di invio. In questo modo si migliora la scalabilità del servizio negli scenari in cui vengono trasmessi messaggi a più client, alcuni dei quali sono lenti nella lettura, probabilmente a causa della congestione della rete, o non effettuano l'operazione. In questi scenari, non vengono bloccati i singoli thread sul servizio per client. In questo modo si assicura che il servizio possa elaborare molti più client, migliorando pertanto la scalabilità del servizio.  
  
### <a name="programming-model-for-streamed-transfers"></a>Modello di programmazione per i trasferimenti in flussi  
 Il modello di programmazione per il flusso è semplice. Per ricevere flussi di dati, specificare un contratto di operazione con un solo parametro di input tipizzato <xref:System.IO.Stream>. Per restituire flussi di dati, restituire un riferimento <xref:System.IO.Stream>.  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IStreamedService  
{  
    [OperationContract]  
    Stream Echo(Stream data);  
    [OperationContract]  
    Stream RequestInfo(string query);  
    [OperationContract(OneWay=true)]  
    void ProvideInfo(Stream data);  
}  
```  
  
 L'operazione `Echo` nell'esempio precedente riceve e restituisce un flusso e deve pertanto essere utilizzato su un'associazione con <xref:System.ServiceModel.TransferMode.Streamed>. Per l'operazione `RequestInfo`, <xref:System.ServiceModel.TransferMode.StreamedResponse> è la soluzione ideale, in quanto restituisce solo un <xref:System.IO.Stream>. L'operazione unidirezionale è particolarmente indicata per <xref:System.ServiceModel.TransferMode.StreamedRequest>.  
  
 Si noti che aggiungendo un secondo parametro alle operazioni `Echo` o `ProvideInfo` successive, il modello di servizio deve ripristinare una strategia di memorizzazione nel buffer e utilizzare la rappresentazione della serializzazione di runtime del flusso. Solo le operazioni con un singolo parametro di input del flusso sono compatibili con flusso di richiesta end-to-end.  
  
 Questa regola si applica in modo analogo ai contratti di messaggio. Come illustrato nel contratto di messaggio seguente, un solo membro del corpo nel contratto del messaggio può essere un flusso. Se si desidera comunicare informazioni aggiuntive con il flusso, queste informazioni devono essere incluse nelle intestazioni del messaggio. Il corpo del messaggio è riservato esclusivamente al contenuto del flusso.  
  
```csharp
[MessageContract]  
public class UploadStreamMessage  
{  
   [MessageHeader]  
   public string appRef;  
   [MessageBodyMember]  
   public Stream data;  
}
```  
  
 Il trasferimento del flusso termina e il messaggio viene chiuso quando il flusso raggiunge la fine del file. Quando si invia un messaggio (restituendo un valore o richiamando un'operazione), è possibile passare un oggetto <xref:System.IO.FileStream> e l'infrastruttura WCF esegue successivamente il pull di tutti i dati dal flusso fino a quando il flusso non è stato completamente letto e raggiunto EOF. Per trasferire flussi di dati per l'origine se non esiste una classe derivata <xref:System.IO.Stream> predefinita, costruire tale classe, sovrapporla all'origine del flusso e utilizzarla come argomento o valore restituito.  
  
 Quando si riceve un messaggio, WCF costruisce un flusso sul contenuto del corpo del messaggio con codifica Base64 (o sulla parte MIME corrispondente se si utilizza MTOM) e il flusso raggiunge la fine del periodo di tempo in cui il contenuto è stato letto.  
  
 Il flusso a livello di trasporto funziona anche con qualsiasi altro tipo di contratto di messaggio (elenchi di parametri, argomenti del contratto dati e contratto di messaggio esplicito), ma poiché la serializzazione e deserializzazione di questi tipi di messaggi richiede la memorizzazione nel buffer da parte del serializzatore, l'utilizzo di tali varianti di contratto non è consigliabile.  
  
### <a name="special-security-considerations-for-large-data"></a>Considerazioni speciali sulla protezione per i dati di grandi dimensioni  
 Tutte le associazioni consentono di vincolare le dimensioni dei messaggi in arrivo per impedire attacchi Denial of Service. <xref:System.ServiceModel.BasicHttpBinding>, Ad esempio, espone una proprietà [System. ServiceModel. BasicHttpBinding. MaxReceivedMessageSize](xref:System.ServiceModel.HttpBindingBase.MaxReceivedMessageSize%2A) che delimita le dimensioni del messaggio in arrivo, quindi delimita anche la quantità massima di memoria a cui si accede durante l'elaborazione del messaggio. Questa unità è indicata in byte con un valore predefinito di 65.536 byte.  
  
 Un rischio per la sicurezza specifico per gli scenari con flussi di dati di grandi dimensioni provoca un attacco Denial of Service che causa la memorizzazione nel buffer dei dati mentre il destinatario si aspetta che vengano trasmessi in un flusso. Ad esempio, WCF memorizza sempre nel buffer le intestazioni SOAP di un messaggio, quindi un utente malintenzionato può costruire un messaggio dannoso di grandi dimensioni costituito interamente da intestazioni per forzare il buffering dei dati. Quando il flusso è abilitato, è possibile che `MaxReceivedMessageSize` sia impostato su un valore estremamente elevato, perché il destinatario non si aspetta che l'intero messaggio venga memorizzato immediatamente nel buffer in memoria. Se WCF è forzato a memorizzare nel buffer il messaggio, si verifica un overflow della memoria.  
  
 Di conseguenza, limitare le dimensioni massime del messaggio in arrivo non è sufficiente in questo caso. La `MaxBufferSize` proprietà è necessaria per vincolare la memoria memorizzata nei buffer WCF. È importante impostare questa proprietà su un valore sicuro (o lasciare il valore predefinito) per il flusso. Ad esempio, si supponga che il servizio debba ricevere file di dimensioni fino a 4 GB e debba archiviarli sul disco locale. Si supponga inoltre che la memoria sia vincolata in modo da poter memorizzare nel buffer solo 64 KB di dati per volta. In tal caso, è necessario impostare `MaxReceivedMessageSize` su 4 GB e `MaxBufferSize` su 64 KB. Inoltre, nell'implementazione del servizio è necessario verificare di poter eseguire solo la lettura dal flusso in ingresso in blocchi di 64 KB, impedendo la lettura del blocco successivo prima che il precedente sia stato scritto su disco ed eliminato dalla memoria.  
  
 È inoltre importante comprendere che questa quota limita solo la memorizzazione nel buffer eseguita da WCF e non è in grado di proteggersi da eventuali buffer eseguiti nell'implementazione del servizio o del client. Per ulteriori informazioni sulle considerazioni relative alla sicurezza, vedere [considerazioni sulla sicurezza per i dati](security-considerations-for-data.md).  
  
> [!NOTE]
> La scelta di utilizzare trasferimenti memorizzati nel buffer o in flussi è una decisione specifica dell'endpoint. Per i trasporti HTTP, la modalità di trasferimento non si propaga attraverso una connessione o ai server proxy e agli altri intermediari. L'impostazione della modalità di trasferimento non si riflette nella descrizione dell'interfaccia del servizio. Dopo la generazione di un client WCF in un servizio, è necessario modificare il file di configurazione per i servizi destinati a essere utilizzati con i trasferimenti trasmessi per impostare la modalità. Per i trasporti TCP e named pipe, la modalità di trasferimento viene propagata come asserzione di criteri.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: attivare il flusso](how-to-enable-streaming.md)

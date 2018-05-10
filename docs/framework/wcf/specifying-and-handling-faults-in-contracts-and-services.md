---
title: Specifica e gestione di errori in contratti e servizi
ms.date: 03/30/2017
helpviewer_keywords:
- handling faults [WCF]
ms.assetid: a9696563-d404-4905-942d-1e0834c26dea
ms.openlocfilehash: 93ebbf3410dc197982ca617b4e989d07f0e0b454
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
---
# <a name="specifying-and-handling-faults-in-contracts-and-services"></a>Specifica e gestione di errori in contratti e servizi
Le applicazioni di Windows Communication Foundation (WCF) gestire situazioni di errore eseguendo il mapping di oggetti eccezione gestiti a oggetti errore SOAP e oggetti errore SOAP a oggetti eccezione gestiti. Negli argomenti di questa sezione viene illustrato come progettare contratti per esporre condizioni di errore come errori SOAP personalizzati, come restituire tali errori come parte dell'implementazione del servizio e come tali errori vengono rilevati dai client.  
  
## <a name="error-handling-overview"></a>Panoramica sulla gestione degli errori  
 Tutte le applicazioni gestite prevedono che gli errori di elaborazione siano rappresentati dagli oggetti <xref:System.Exception>. Nelle applicazioni basate su SOAP, ad esempio le applicazioni WCF, informazioni sugli errori di elaborazione tramite messaggi di errore SOAP vengono comunicate dai metodi di servizio. Gli errori SOAP sono tipi di messaggio inclusi nei metadati per un'operazione del servizio e pertanto creano un contratto di errore che i client possono utilizzare per rendere il proprio funzionamento più affidabile o interattivo. Inoltre, poiché gli errori SOAP sono espressi ai client in formato XML, è un sistema di tipo altamente interoperabile utilizzabile dai client su qualsiasi piattaforma, aumentando la portata dell'applicazione WCF.  
  
 Poiché le applicazioni WCF eseguite con entrambi i tipi di sistemi di errore, le informazioni sulle eccezioni gestite che viene inviati al client deve essere convertite da eccezioni in errori SOAP sul servizio, inviate e convertite da errori SOAP in eccezioni di errore nei client WCF. Nel caso di client duplex, i contratti client possono anche restituire errori SOAP a un servizio. In entrambi i casi, è possibile utilizzare i comportamenti predefiniti delle eccezioni di servizio. In alternativa, è possibile stabilire in modo esplicito se convertire le eccezioni in messaggi di errore e, in tal caso, definire le modalità di conversione.  
  
 Due tipi di errori SOAP possono essere inviati: *dichiarato* e *non dichiarato*. Gli errori SOAP dichiarati sono quelli in cui un'operazione presenta un attributo <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> che specifica un tipo di errore SOAP personalizzato. *Non dichiarato* errori SOAP non sono specificati nel contratto per un'operazione.  
  
 È consigliabile che le operazioni del servizio dichiarino gli errori utilizzando l'attributo <xref:System.ServiceModel.FaultContractAttribute> per specificare formalmente tutti gli errori SOAP che un client può aspettarsi di ricevere durante il normale funzionamento di un'operazione. Per ridurre al minimo la divulgazione delle informazioni è inoltre consigliabile restituire negli errori SOAP solo le informazioni che il client deve conoscere.  
  
 In genere, i servizi (e i client duplex) prevedono i passaggi seguenti per integrare correttamente la gestione degli errori nelle applicazioni:  
  
-   Eseguire il mapping delle condizioni di eccezione a errori SOAP personalizzati.  
  
-   I client e i servizi inviano e ricevono errori SOAP come eccezioni.  
  
 Inoltre, client e servizi WCF possono utilizzare errori soap non dichiarati a scopo di debug e possono estendere il comportamento predefinito degli errori. Nelle sezioni seguenti vengono esaminati questi concetti e attività.  
  
## <a name="map-exceptions-to-soap-faults"></a>Eseguire il mapping delle eccezioni a errori SOAP  
 Il primo passaggio per creare un'operazione che gestisca condizioni di errore consiste nel decidere a quali condizioni un'applicazione client deve essere informata degli errori. Alcune operazioni hanno condizioni di errore specifiche per la propria funzionalità. Ad esempio, un'operazione `PurchaseOrder` potrebbe restituire informazioni specifiche a clienti a cui non è più consentito avviare un ordine d'acquisto. In altri casi, quali, ad esempio, un servizio `Calculator`, un errore SOAP `MathFault` più generale potrebbe essere in grado di descrivere tutte le condizioni di errore di un intero servizio. Dopo avere identificato tutte le condizioni di errore dei client del servizio, è possibile costruire un errore SOAP personalizzato e contrassegnare l'operazione come restituzione dell'errore SOAP quando si verifica la condizione di errore corrispondente.  
  
 Per ulteriori informazioni su questo passaggio dello sviluppo del servizio o client, vedere [definizione e gli errori specificando](../../../docs/framework/wcf/defining-and-specifying-faults.md).  
  
## <a name="clients-and-services-handle-soap-faults-as-exceptions"></a>Gestione degli errori SOAP come eccezioni da parte di client e servizi  
 Identificando le condizioni di errore di operazione, definire errori SOAP personalizzati e contrassegnare le operazioni perché restituiscano gli errori sono i primi passaggi nella corretta gestione degli errori in applicazioni WCF. Il passaggio successivo è invece rappresentato dall'implementazione di invio e ricezione degli errori. In genere, i servizi inviano errori per informare le applicazioni client delle condizioni di errore, ma anche i client duplex  possono inviare errori SOAP ai servizi.  
  
 Per ulteriori informazioni, vedere [invio e ricezione di errori](../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
## <a name="undeclared-soap-faults-and-debugging"></a>Errori SOAP non dichiarati e debug  
 Gli errori SOAP non dichiarati sono estremamente utili per la compilazione di solide applicazioni distribuite e interoperabili. Tuttavia, in alcuni casi, è utile per un servizio (o un client duplex) inviare un errore SOAP non dichiarato, uno di quegli errori non menzionati nel codice WSDL (Web Services Description Language) dell'operazione. Ad esempio, quando si sviluppa un servizio, possono verificarsi situazioni impreviste in cui è utile, a scopo di debug, reinviare informazioni al client. Inoltre, è possibile impostare il <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> proprietà o il <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> proprietà `true` per consentire ai client WCF per ottenere informazioni sulle eccezioni delle operazioni interne del servizio. L'invio di errori di singoli e impostando le proprietà del comportamento di debug sono descritti in [invio e ricezione di errori](../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
> [!IMPORTANT]
>  Poiché le eccezioni gestite possono esporre informazioni interne dell'applicazione, se si imposta <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> oppure <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> a `true` può consentire ai client WCF di ottenere informazioni sulle eccezioni delle operazioni interne del servizio, incluse le informazioni informazioni personali o comunque riservate.  
>   
>  Di conseguenza, l'impostazione della proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> su `true` è consigliabile solo come modalità temporanea di debug di un'applicazione del servizio. Inoltre, il codice WSDL di un metodo che restituisce in questo modo eccezioni gestite senza tuttavia gestirle non contiene il contratto dell'eccezione <xref:System.ServiceModel.FaultException%601> di tipo <xref:System.ServiceModel.ExceptionDetail>. I client devono prevedere la possibilità di un errore SOAP sconosciuto (restituito ai client WCF come <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> oggetti) per ottenere correttamente le informazioni di debug.  
  
## <a name="customizing-error-handling-with-ierrorhandler"></a>Personalizzazione della gestione degli errori con IErrorHandler  
 Se si ha l'esigenza di personalizzare il messaggio di risposta al client, quando si verifica un'eccezione a livello di applicazione, o di effettuare alcune operazioni di elaborazione personalizzate dopo la restituzione del messaggio di risposta, implementare l'interfaccia <xref:System.ServiceModel.Dispatcher.IErrorHandler?displayProperty=nameWithType>.  
  
## <a name="fault-serialization-issues"></a>Problemi di serializzazione  
 Durante la deserializzazione di un contratto di errore, in WCF viene innanzitutto effettuato il tentativo di far corrispondere il nome del contratto di errore nel messaggio SOAP con il tipo di contratto di errore. Se non si trova una corrispondenza esatta, verrà effettuata una ricerca, in ordine alfabetico, di un tipo compatibile nell'elenco di contratti di errore disponibile. Se due contratti di errore sono tipi compatibili (ad esempio uno è una sottoclasse dell'altro), per deserializzare l'errore potrebbe essere utilizzato il tipo non corretto. Tale situazione si verifica solo se nel contratto di errore non vengono specificati un nome, uno spazio dei nomi e un'azione. Per evitare il verificarsi di tale errore, specificare sempre completamente i contratti di errore indicando il nome, lo spazio dei nomi e gli attributi dell'azione. Inoltre, se è stato definito un numero di contratti di errore correlati derivati da una classe base condivisa, assicurarsi di contrassegnare qualsiasi membro nuovo con `[DataMember(IsRequired=true)]`. Per ulteriori informazioni su questo attributo `IsRequired`, vedere <xref:System.Runtime.Serialization.DataMemberAttribute>. In questo modo si potrà evitare che la classe base sia di tipo compatibile e si consentirà la deserializzazione dell'errore nel tipo derivato corretto.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.FaultException>  
 <xref:System.ServiceModel.FaultContractAttribute>  
 <xref:System.ServiceModel.FaultException>  
 <xref:System.Xml.Serialization.XmlSerializer>  
 <xref:System.ServiceModel.XmlSerializerFormatAttribute>  
 <xref:System.ServiceModel.FaultContractAttribute>  
 <xref:System.ServiceModel.CommunicationException>  
 <xref:System.ServiceModel.FaultContractAttribute.Action%2A>  
 <xref:System.ServiceModel.FaultException.Code%2A>  
 <xref:System.ServiceModel.FaultException.Reason%2A>  
 <xref:System.ServiceModel.FaultCode.SubCode%2A>  
 <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>  
 [Definizione e specifica degli errori](../../../docs/framework/wcf/defining-and-specifying-faults.md)

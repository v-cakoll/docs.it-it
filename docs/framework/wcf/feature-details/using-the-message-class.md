---
title: Utilizzo della classe Message
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d1d62bfb-2aa3-4170-b6f8-c93d3afdbbed
ms.openlocfilehash: 142578ef76a70fed27dc0137378b59e228cd25c9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84585649"
---
# <a name="using-the-message-class"></a>Utilizzo della classe Message
La <xref:System.ServiceModel.Channels.Message> classe è fondamentale per Windows Communication Foundation (WCF). Tutte le comunicazioni tra client e servizi implicano in ultima istanza l'invio e la ricezione di istanze di <xref:System.ServiceModel.Channels.Message>.  
  
 Di norma non si interagisce con la classe <xref:System.ServiceModel.Channels.Message> in modo diretto. Al contrario, i costrutti del modello del servizio WCF, ad esempio i contratti dati, i contratti di messaggio e i contratti di operazione, vengono utilizzati per descrivere i messaggi in ingresso e in uscita. Tuttavia, in alcuni scenari avanzati, è possibile eseguire la programmazione usando direttamente la classe <xref:System.ServiceModel.Channels.Message>. Ad esempio, può essere necessario usare la classe <xref:System.ServiceModel.Channels.Message>:  
  
- Quando è necessario un modo alternativo per creare il contenuto dei messaggi in uscita (ad esempio, la creazione di un messaggio direttamente da un file su disco) invece di serializzare .NET Framework oggetti.  
  
- Quando è necessario un modo alternativo per utilizzare il contenuto dei messaggi in ingresso, ad esempio quando si desidera applicare una trasformazione XSLT al contenuto XML non elaborato, anziché deserializzare in oggetti .NET Framework.  
  
- Quando è necessario gestire i messaggi in modo generico, indipendentemente dal contenuto (ad esempio, per l'indirizzamento o l'inoltro di messaggi durante la creazione di un router, un servizio di bilanciamento del carico o un sistema di pubblicazione-sottoscrizione).  
  
 Prima di utilizzare la <xref:System.ServiceModel.Channels.Message> classe, acquisire familiarità con l'architettura di trasferimento dei dati WCF in [trasferimento dati panoramica dell'architettura](data-transfer-architectural-overview.md).  
  
 Una classe <xref:System.ServiceModel.Channels.Message> è un contenitore generico di dati, la cui progettazione segue però da vicino quella di un messaggio nel protocollo SOAP. Proprio come in SOAP, un messaggio ha un corpo e delle intestazioni. Il corpo del messaggio contiene i dati del payload effettivi, mentre le intestazioni contengono contenitori dei dati denominati aggiuntivi. Le regole per la lettura e la scrittura del corpo e delle intestazioni sono diverse, ad esempio, le intestazioni vengono sempre memorizzate nel buffer in memoria ed è possibile accedervi in qualsiasi ordine, tutte le volte che si desidera, il corpo può invece essere letto una sola volta ed essere trasmesso. In genere, quando si usa SOAP, il corpo del messaggio viene mappato al corpo SOAP e le intestazioni vengono mappate alle intestazioni SOAP.  
  
## <a name="using-the-message-class-in-operations"></a>Uso della classe Message nelle operazioni  
 È possibile usare la classe <xref:System.ServiceModel.Channels.Message> come parametro di input e/o valore restituito di un'operazione. Se la classe <xref:System.ServiceModel.Channels.Message> viene usata in un punto qualsiasi di un'operazione, si applicano le restrizioni seguenti:  
  
- L'operazione non può avere qualsiasi parametro `out` o `ref`.  
  
- Non può essere presente più di un parametro `input`. Se il parametro è presente, deve essere di tipo Message o contratto di messaggio.  
  
- Il tipo restituito deve essere `void`, `Message` o un tipo di contratto di messaggio.  
  
 L'esempio di codice seguente contiene un contratto di operazione valido.  
  
 [!code-csharp[C_UsingTheMessageClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#1)]
 [!code-vb[C_UsingTheMessageClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#1)]  
  
## <a name="creating-basic-messages"></a>Creazione di messaggi di base  
 La classe <xref:System.ServiceModel.Channels.Message> fornisce metodi factory `CreateMessage` statici che è possibile usare per creare messaggi di base.  
  
 Tutti gli overload `CreateMessage` accettano un parametro di versione di tipo <xref:System.ServiceModel.Channels.MessageVersion>, che indica le versioni SOAP e WS-Addressing da usare per il messaggio. Se si desidera usare le stesse versioni del protocollo del messaggio in ingresso, è possibile usare la proprietà <xref:System.ServiceModel.OperationContext.IncomingMessageVersion%2A> sull'istanza di <xref:System.ServiceModel.OperationContext> ottenuta dalla proprietà <xref:System.ServiceModel.OperationContext.Current%2A>. La maggior parte degli overload `CreateMessage` hanno anche un parametro stringa che indica l'azione SOAP da usare per il messaggio. È possibile impostare la versione su `None` per disabilitare la generazione di SOAP envelope. Il messaggio è costituito dal solo corpo.  
  
## <a name="creating-messages-from-objects"></a>Creazione di messaggi da oggetti  
 Tramite l'overload `CreateMessage` più elementare, che accetta solo una versione e un'azione, viene creato un messaggio con un corpo vuoto. Un altro overload accetta un parametro <xref:System.Object> aggiuntivo, creando un messaggio il cui corpo è la rappresentazione serializzata dell'oggetto specificato. Usare la classe <xref:System.Runtime.Serialization.DataContractSerializer> con le impostazioni predefinite per la serializzazione. Se si desidera usare un serializzatore diverso o si desidera che la classe `DataContractSerializer` venga configurata in modo diverso, usare l'overload `CreateMessage` che accetta anche un parametro `XmlObjectSerializer`.  
  
 Per restituire un oggetto in un messaggio è, ad esempio, possibile usare il codice seguente.  
  
 [!code-csharp[C_UsingTheMessageClass#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#2)]
 [!code-vb[C_UsingTheMessageClass#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#2)]  
  
## <a name="creating-messages-from-xml-readers"></a>Creazione di messaggi da lettori XML  
 Esistono overload `CreateMessage` che accettano una classe <xref:System.Xml.XmlReader> o <xref:System.Xml.XmlDictionaryReader> per il corpo invece di un oggetto. In questo caso il corpo del messaggio contiene il codice XML prodotto dalla lettura del lettore XML passato. Ad esempio, nel codice seguente viene restituito un messaggio con il contenuto del corpo letto da un file XML.  
  
 [!code-csharp[C_UsingTheMessageClass#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#3)]
 [!code-vb[C_UsingTheMessageClass#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#3)]  
  
 Esistono, inoltre, overload `CreateMessage` che accettano una classe <xref:System.Xml.XmlReader> o <xref:System.Xml.XmlDictionaryReader> che rappresenta l'intero messaggio e non solo il corpo. Questi overload accettano anche un parametro `maxSizeOfHeaders` intero. Le intestazioni vengono sempre memorizzate nel buffer in memoria non appena viene creato il messaggio e questo parametro limita la quantità di memorizzazione nel buffer eseguita. È importante impostare questo parametro su un valore sicuro, se il codice XML proviene da un'origine non attendibile, per ridurre la possibilità di un attacco di tipo Denial of Service. Le versioni SOAP e WS-Addressing del messaggio rappresentato dal lettore XML devono corrispondere alle versioni indicate mediante il parametro di versione.  
  
## <a name="creating-messages-with-bodywriter"></a>Creazione di messaggi con BodyWriter  
 Un overload `CreateMessage` accetta un'istanza di `BodyWriter` per descrivere il corpo del messaggio. `BodyWriter` è una classe astratta che può essere derivata per personalizzare la modalità di creazione dei corpi dei messaggi. È possibile creare una classe derivata `BodyWriter` personalizzata per descrivere i corpi dei messaggi nel modo desiderato. È necessario eseguire l'override del metodo `BodyWriter.OnWriteBodyContents` che accetta <xref:System.Xml.XmlDictionaryWriter>. Questo metodo è responsabile della scrittura del corpo.  
  
 I body writer possono essere memorizzati nel buffer oppure no (trasmessi). I body writer memorizzati nel buffer possono scrivere il proprio contenuto qualsiasi numero di volte, quelli trasmessi possono invece scrivere il proprio contenuto una sola volta. La proprietà `IsBuffered` indica se un body writer è memorizzato o meno nel buffer. Per impostare questa proprietà per il body writer chiamare il costruttore `BodyWriter` protetto che accetta un parametro booleano `isBuffered`. I body writer supportano la creazione di un body writer memorizzato nel buffer da un body writer non memorizzato nel buffer. È possibile eseguire l'override del metodo `OnCreateBufferedCopy` per personalizzare questo processo. Per impostazione predefinita, viene usato un buffer in memoria contenente il codice XML restituito da `OnWriteBodyContents`. `OnCreateBufferedCopy` accetta un parametro di tipo Integer `maxBufferSize`. Se si esegue l'override di questo metodo, non è necessario creare buffer più grandi della dimensione massima specificata.  
  
 La classe `BodyWriter` fornisce i metodi `WriteBodyContents` e `CreateBufferedCopy` che sono essenzialmente thin wrapper rispettivamente dei metodi `OnWriteBodyContents` e `OnCreateBufferedCopy`. Questi metodi eseguono un controllo dello stato per assicurare che non sia possibile accedere a un body writer non memorizzato nel buffer più di una volta. I metodi vengono chiamati direttamente solo in caso di creazione di classi derivate `Message` personalizzate basate su `BodyWriters`.  
  
## <a name="creating-fault-messages"></a>Creazione di messaggi di errore  
 È possibile usare determinati overload `CreateMessage` per creare messaggi di errore SOAP. Il più elementare accetta un oggetto <xref:System.ServiceModel.Channels.MessageFault> che descrive l'errore. Altri overload vengono forniti per comodità. Il primo di tali overload accetta un elemento `FaultCode` e una stringa motivo e crea un elemento `MessageFault` usando `MessageFault.CreateFault` che usa queste informazioni. L'altro overload accetta un oggetto Detail e lo passa a `CreateFault` insieme al codice e al motivo dell'errore. Ad esempio, nell'operazione seguente viene restituito un errore.  
  
 [!code-csharp[C_UsingTheMessageClass#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#4)]
 [!code-vb[C_UsingTheMessageClass#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#4)]  
  
## <a name="extracting-message-body-data"></a>Estrazione di dati del corpo del messaggio  
 La classe `Message` supporta più modalità di estrazione delle informazioni dal proprio corpo. Queste modalità possono essere classificate nelle categorie seguenti:  
  
- Recupero dell'intero corpo del messaggio scritto tutto in sola volta in un writer XML. Questa operazione viene definita *scrittura di un messaggio*.  
  
- Recupero di un lettore XML sul corpo del messaggio. Questo consente di accedere in seguito al corpo del messaggio un pezzo alla volta, come richiesto. Questa operazione viene definita *lettura di un messaggio*.  
  
- L'intero messaggio, incluso il corpo, può essere copiato in un buffer in memoria di tipo <xref:System.ServiceModel.Channels.MessageBuffer>. Questa operazione viene definita *copia di un messaggio*.  
  
 È possibile accedere al corpo di una classe `Message` una sola volta, indipendentemente dalla modalità di accesso. Un oggetto messaggio ha una proprietà `State`, impostata inizialmente su Creato. I tre metodi di accesso descritti nell'elenco precedente impostano lo stato rispettivamente su Scritto, Letto e Copiato. Inoltre, un metodo `Close` può impostare lo stato su Chiuso, quando il contenuto del corpo del messaggio non è più necessario. Il corpo del messaggio è accessibile solo nello stato Creato e non c'è alcun modo per tornare allo stato Creato dopo che è stato modificato.  
  
## <a name="writing-messages"></a>Scrittura di messaggi  
 Il metodo <xref:System.ServiceModel.Channels.Message.WriteBodyContents%28System.Xml.XmlDictionaryWriter%29> scrive il contenuto del corpo di un'istanza di `Message` in un determinato writer XML. Il <xref:System.ServiceModel.Channels.Message.WriteBody%2A> metodo esegue la stessa operazione, ad eccezione del fatto che racchiude il contenuto del corpo nell'elemento wrapper appropriato, ad esempio <`soap:body`>. Infine, <xref:System.ServiceModel.Channels.Message.WriteMessage%2A> scrive l'intero messaggio, incluse l'envelope SOAP di wrapping e le intestazioni. Se SOAP è disattivato ( <xref:System.ServiceModel.Channels.Message.Version> is <xref:System.ServiceModel.Channels.MessageVersion.None?displayProperty=nameWithType> ), tutti e tre i metodi eseguono la stessa operazione: scrivono il contenuto del corpo del messaggio.  
  
 Ad esempio, nel codice seguente viene scritto il corpo di un messaggio in ingresso in un file.  
  
 [!code-csharp[C_UsingTheMessageClass#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#5)]
 [!code-vb[C_UsingTheMessageClass#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#5)]  
  
 Due metodi di supporto aggiuntivi scrivono determinati tag di elemento iniziali SOAP. Questi metodi non accedono al corpo del messaggio, pertanto non modificano lo stato del messaggio. Sono inclusi:  
  
- <xref:System.ServiceModel.Channels.Message.WriteStartBody%2A> scrive l'elemento del corpo iniziale, ad esempio, `<soap:Body>`.  
  
- <xref:System.ServiceModel.Channels.Message.WriteStartEnvelope%2A> scrive l'elemento envelope iniziale, ad esempio, `<soap:Envelope>`.  
  
 Per scrivere i corrispondenti tag di elemento finali, chiamare `WriteEndElement` sul writer XML corrispondente. È raro che questi metodi vengano chiamati direttamente.  
  
## <a name="reading-messages"></a>Lettura di messaggi  
 La modalità principale per leggere il corpo di un messaggio consiste nel chiamare <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A>. Si ottiene una classe <xref:System.Xml.XmlDictionaryReader> usabile per leggere il corpo del messaggio. Si noti che <xref:System.ServiceModel.Channels.Message> passa allo stato Letto non appena viene chiamato <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A>, non quando si usa il lettore XML restituito.  
  
 Il metodo <xref:System.ServiceModel.Channels.Message.GetBody%2A> consente anche di accedere al corpo del messaggio come oggetto tipizzato. Internamente, questo metodo usa `GetReaderAtBodyContents` e quindi esegue anche la transizione dello stato del messaggio allo stato <xref:System.ServiceModel.Channels.MessageState.Read> (vedere la proprietà <xref:System.ServiceModel.Channels.Message.State%2A>).  
  
 È buona norma controllare la proprietà <xref:System.ServiceModel.Channels.Message.IsEmpty%2A>, caso in cui il corpo del messaggio è vuoto e <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> genera una <xref:System.InvalidOperationException>. Inoltre, se si tratta di un messaggio ricevuto (ad esempio una risposta), può essere necessario controllare anche <xref:System.ServiceModel.Channels.Message.IsFault%2A>, che indica se il messaggio contiene un errore.  
  
 L'overload più elementare di <xref:System.ServiceModel.Channels.Message.GetBody%2A> deserializza il corpo del messaggio in un'istanza di un tipo (indicato dal parametro generico) usando un oggetto <xref:System.Runtime.Serialization.DataContractSerializer> configurato con le impostazioni predefinite e con la quota <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A> disabilitata. Se si desidera usare un altro motore di serializzazione o configurare `DataContractSerializer` in modo non predefinito, usare l'overload <xref:System.ServiceModel.Channels.Message.GetBody%2A> che accetta una classe <xref:System.Runtime.Serialization.XmlObjectSerializer>.  
  
 Ad esempio, nel codice seguente vengono estratti i dati dal corpo di un messaggio che contiene un oggetto `Person` serializzato e viene stampato il nome della persona.  
  
 [!code-csharp[C_UsingTheMessageClass#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#6)]
 [!code-vb[C_UsingTheMessageClass#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#6)]  
  
## <a name="copying-a-message-into-a-buffer"></a>Copia di un messaggio in un buffer  
 Talvolta è necessario accedere al corpo del messaggio più di una volta, ad esempio per inoltrare lo stesso messaggio a più destinazioni come parte di un sistema di pubblicazione-sottoscrizione. In questo caso è necessario memorizzare nel buffer l'intero messaggio (incluso il corpo) in memoria. A questo scopo è possibile chiamare <xref:System.ServiceModel.Channels.Message.CreateBufferedCopy%28System.Int32%29>. Questo metodo accetta un parametro integer che rappresenta la dimensione massima del buffer e crea un buffer che non supera tale dimensione. È importante impostare il parametro su un valore sicuro, se il messaggio proviene da un'origine non attendibile.  
  
 Il buffer viene restituito come istanza di <xref:System.ServiceModel.Channels.MessageBuffer>. È possibile accedere ai dati nel buffer in diversi modi. Il modo principale consiste nel chiamare <xref:System.ServiceModel.Channels.Message.CreateMessage%2A> per creare istanze di `Message` dal buffer.  
  
 Un altro modo per accedere ai dati nel buffer consiste nell'implementare l'interfaccia <xref:System.Xml.XPath.IXPathNavigable> implementata dalla classe <xref:System.ServiceModel.Channels.MessageBuffer> per accedere direttamente al codice XML sottostante. Alcuni overload di <xref:System.ServiceModel.Channels.MessageBuffer.CreateNavigator%2A> consentono di creare strumenti di spostamento <xref:System.Xml.XPath> protetti da una quota del nodo, limitando il numero di nodi XML che è possibile visitare. Questo consente di impedire attacchi di tipo Denial of Service basati su lunghi tempi di elaborazione. Questa quota è disattivata per impostazione predefinita. Alcuni overload `CreateNavigator` consentono di specificare la modalità di gestione dello spazio vuoto nel codice XML usando l'enumerazione <xref:System.Xml.XmlSpace>, con l'impostazione predefinita `XmlSpace.None`.  
  
 Un modo finale per accedere al contenuto di un buffer dei messaggi consiste nello scriverne il contenuto in un flusso usando <xref:System.ServiceModel.Channels.Message.WriteMessage%2A>.  
  
 Nell'esempio seguente viene illustrato il processo d'uso di `MessageBuffer`: un messaggio in ingresso viene inoltrato a più destinatari e quindi registrato in un file. Senza la memorizzazione nel buffer, questa operazione non può essere eseguita, perché è possibile accedere al corpo del messaggio una sola volta.  
  
 [!code-csharp[C_UsingTheMessageClass#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#7)]
 [!code-vb[C_UsingTheMessageClass#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#7)]  
  
 La classe `MessageBuffer` ha altri membri non degni di nota. È possibile chiamare il metodo <xref:System.ServiceModel.Channels.MessageBuffer.Close%2A> per liberare risorse quando il contenuto del buffer non è più necessario. La proprietà <xref:System.ServiceModel.Channels.MessageBuffer.BufferSize%2A> restituisce la dimensione del buffer allocato. La proprietà <xref:System.ServiceModel.Channels.MessageBuffer.MessageContentType%2A> restituisce il tipo di contenuti MIME del messaggio.  
  
## <a name="accessing-the-message-body-for-debugging"></a>Accesso al corpo del messaggio a scopo di debug  
 A scopo di debug, è possibile chiamare il metodo <xref:System.ServiceModel.Channels.Message.ToString%2A> per ottenere una rappresentazione del messaggio come stringa. Questa rappresentazione corrisponde in genere all'aspetto che avrebbe il messaggio in transito se fosse codificato con il codificatore di testo, eccetto per il fatto che il codice XML sarebbe formattato in modo leggibile. L'unica eccezione è il corpo del messaggio. Il corpo può essere letto una sola volta e `ToString` non modifica lo stato del messaggio. Pertanto, il `ToString` metodo potrebbe non essere in grado di accedere al corpo e potrebbe sostituire un segnaposto, ad esempio "..." o tre punti) invece del corpo del messaggio. Non usare quindi `ToString` per registrare messaggi con contenuto del corpo importante.  
  
## <a name="accessing-other-message-parts"></a>Accesso ad altre parti del messaggio  
 Vengono fornite varie proprietà per accedere a informazioni sul messaggio diverse dal contenuto del corpo. Queste proprietà non possono tuttavia essere chiamate dopo la chiusura del messaggio:  
  
- La proprietà <xref:System.ServiceModel.Channels.Message.Headers%2A> rappresenta le intestazioni del messaggio. Vedere la sezione "utilizzo delle intestazioni" più avanti in questo argomento.  
  
- La proprietà <xref:System.ServiceModel.Channels.Message.Properties%2A> rappresenta le proprietà del messaggio, che sono pezzi di dati denominati collegati al messaggio che non vengono generalmente generati quando il messaggio viene inviato. Vedere la sezione sull'uso di proprietà più avanti in questo argomento.  
  
- La proprietà <xref:System.ServiceModel.Channels.Message.Version%2A> indica la versione SOAP e WS-Addressing associata al messaggio o `None` se SOAP è disattivato.  
  
- La proprietà <xref:System.ServiceModel.Channels.Message.IsFault%2A> restituisce `true` se il messaggio e un messaggio di errore SOAP.  
  
- La proprietà <xref:System.ServiceModel.Channels.Message.IsEmpty%2A> restituisce `true` se il messaggio è vuoto.  
  
 È possibile usare il metodo <xref:System.ServiceModel.Channels.Message.GetBodyAttribute%28System.String%2CSystem.String%29> per accedere a un particolare attributo sull'elemento wrapper del corpo, ad esempio, `<soap:Body>`, identificato da un nome e uno spazio dei nomi particolari. Se tale attributo non viene trovato, verrà restituito `null`. Questo metodo può essere chiamato solo quando `Message` si trova nello stato Creato, ovvero quando non si è ancora avuto accesso al corpo del messaggio.  
  
## <a name="working-with-headers"></a>Uso di intestazioni  
 Un oggetto `Message` può contenere un numero qualsiasi di frammenti XML denominati, denominati *intestazioni*. Ogni frammento è normalmente mappato a un'intestazione SOAP. Alle intestazioni si accede tramite la proprietà `Headers` di tipo <xref:System.ServiceModel.Channels.MessageHeaders>. <xref:System.ServiceModel.Channels.MessageHeaders> è una raccolta di oggetti <xref:System.ServiceModel.Channels.MessageHeaderInfo> e le singole intestazioni sono accessibili tramite la relativa interfaccia <xref:System.Collections.IEnumerable> o il relativo indicizzatore. Nel codice seguente vengono, ad esempio, elencati i nomi di tutte le intestazioni in una classe `Message`.  
  
 [!code-csharp[C_UsingTheMessageClass#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#8)]
 [!code-vb[C_UsingTheMessageClass#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#8)]  
  
#### <a name="adding-removing-finding-headers"></a>Aggiunta, rimozione e individuazione di intestazioni  
 È possibile aggiungere una nuova intestazione alla fine di tutte le intestazioni esistenti usando il metodo <xref:System.ServiceModel.Channels.MessageHeaders.Add%2A>. È possibile usare il metodo <xref:System.ServiceModel.Channels.MessageHeaders.Insert%2A> per inserire un'intestazione all'altezza di un particolare indice. Le intestazioni esistenti vengono spostate per adattare l'elemento inserito. Le intestazioni vengono ordinate secondo il proprio indice e il primo indice disponibile è 0. È possibile usare i vari overload del metodo <xref:System.ServiceModel.Channels.MessageHeaders.CopyHeadersFrom%2A> per aggiungere intestazioni da una diversa istanza di un oggetto `Message` o `MessageHeaders`. Alcuni overload copiano una sola intestazione, mentre altri le copiano tutte. Il metodo <xref:System.ServiceModel.Channels.MessageHeaders.Clear%2A> rimuove tutte le intestazioni. Il metodo <xref:System.ServiceModel.Channels.MessageHeaders.RemoveAt%2A> rimuove un'intestazione all'altezza di un particolare indice, spostando tutte le intestazioni dopo di essa. Il metodo <xref:System.ServiceModel.Channels.MessageHeaders.RemoveAll%2A> rimuove tutte le intestazioni con un nome e un spazio dei nomi particolari.  
  
 Recuperare una particolare intestazione usando il metodo <xref:System.ServiceModel.Channels.MessageHeaders.FindHeader%2A>. Questo metodo accetta il nome e lo spazio dei nomi dell'intestazione da cercare e restituisce l'indice. Se l'intestazione ricorre più di una volta, verrà generata un'eccezione. Se l'intestazione non viene trovata, verrà restituito -1.  
  
 Nel modello di intestazione SOAP, le intestazioni possono avere un valore `Actor` che specifica il destinatario desiderato dell'intestazione. L'overload `FindHeader` più elementare ricerca solo le intestazioni indirizzate al destinatario finale del messaggio. Tuttavia, un altro overload consente di specificare quali valori `Actor` sono inclusi nella ricerca. Per ulteriori informazioni, vedere la specifica SOAP.  
  
 Viene fornito un metodo <xref:System.ServiceModel.Channels.MessageHeaders.CopyTo%28System.ServiceModel.Channels.MessageHeaderInfo%5B%5D%2CSystem.Int32%29> per copiare intestazioni da una raccolta <xref:System.ServiceModel.Channels.MessageHeaders> a una matrice di oggetti <xref:System.ServiceModel.Channels.MessageHeaderInfo>.  
  
 Per accedere ai dati XML in un'intestazione è possibile chiamare <xref:System.ServiceModel.Channels.MessageHeaders.GetReaderAtHeader%2A> e restituire un lettore XML per l'indice dell'intestazione specifico. Se si desidera deserializzare il contenuto dell'intestazione in un oggetto, usare <xref:System.ServiceModel.Channels.MessageHeaders.GetHeader%60%601%28System.Int32%29> o uno degli altri overload. Gli overload più elementari deserializzano le intestazioni tramite l'oggetto <xref:System.Runtime.Serialization.DataContractSerializer> configurato in modalità predefinita. Se si desidera usare un serializzatore diverso o una differente configurazione della classe `DataContractSerializer`, usare uno degli overload che accettano un `XmlObjectSerializer`. Esistono anche overload che accettano il nome e lo spazio dei nomi dell'intestazione e, facoltativamente, un elenco di valori `Actor` invece di un indice; si tratta di una combinazione di `FindHeader` e `GetHeader`.  
  
## <a name="working-with-properties"></a>Uso di proprietà  
 Un'istanza di `Message` può contenere un numero arbitrario di oggetti denominati di tipi arbitrari. Questa raccolta è accessibile tramite la proprietà `Properties` di tipo `MessageProperties`. La raccolta implementa l'interfaccia <xref:System.Collections.Generic.IDictionary%602> e agisce da mapping da <xref:System.String> a <xref:System.Object>. In genere, i valori delle proprietà non vengono mappati direttamente a una parte del messaggio in transito, ma forniscono diversi hint di elaborazione dei messaggi ai vari canali nello stack dei canali WCF o al <xref:System.ServiceModel.Channels.MessageHeaders.CopyTo%28System.ServiceModel.Channels.MessageHeaderInfo%5B%5D%2CSystem.Int32%29> Framework del servizio. Per un esempio, vedere [Cenni preliminari sull'architettura trasferimento dati](data-transfer-architectural-overview.md).  
  
## <a name="inheriting-from-the-message-class"></a>Eredità dalla classe Message  
 Se i tipi di messaggio incorporati creati usando `CreateMessage` non soddisfano i requisiti, creare una classe che deriva dalla classe `Message`.  
  
### <a name="defining-the-message-body-contents"></a>Definizione del contenuto del corpo del messaggio  
 Esistono tre tecniche principali per accedere ai dati all'interno del corpo di un messaggio: scrittura, lettura e copia in un buffer. Queste operazioni implicano, in ultima istanza, la chiamata dei metodi <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%2A>, <xref:System.ServiceModel.Channels.Message.OnGetReaderAtBodyContents%2A> e <xref:System.ServiceModel.Channels.Message.OnCreateBufferedCopy%2A>, rispettivamente, nella classe derivata di `Message`. La classe di base `Message` garantisce che venga chiamato uno solo di questi metodi, una sola volta, per ogni istanza di `Message` . La classe di base assicura inoltre che i metodi non vengano chiamati su un messaggio chiuso. Non c'è alcuna necessità di tenere traccia dello stato del messaggio nell'implementazione.  
  
 <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%2A> è un metodo astratto e deve essere implementato. L'uso di questo metodo è il modo più elementare per definire il contenuto del corpo del messaggio. Il messaggio seguente contiene, ad esempio, 100.000 numeri casuali da 1 a 20.  
  
 [!code-csharp[C_UsingTheMessageClass#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#9)]
 [!code-vb[C_UsingTheMessageClass#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#9)]  
  
 Per i metodi <xref:System.ServiceModel.Channels.Message.OnGetReaderAtBodyContents> e <xref:System.ServiceModel.Channels.Message.OnCreateBufferedCopy%2A> sono disponibili implementazioni predefinite che funzionano nella maggior parte dei casi. Le implementazioni predefinite chiamano <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%2A>, memorizzano i risultati nel buffer e usano il buffer prodotto. Tuttavia, in alcuni casi, questo potrebbe non essere sufficiente. Nell'esempio precedente, la lettura del messaggio comporta la memorizzazione nel buffer di 100.000 elementi XML, operazione che potrebbe non essere desiderabile. Potrebbe essere necessario eseguire l'override di <xref:System.ServiceModel.Channels.Message.OnGetReaderAtBodyContents> per restituire una classe derivata <xref:System.Xml.XmlDictionaryReader> personalizzata che fornisca numeri casuali. È quindi possibile eseguire l'override <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%2A> di per usare il lettore <xref:System.ServiceModel.Channels.Message.OnGetReaderAtBodyContents> restituito dal metodo, come illustrato nell'esempio seguente.  
  
 [!code-csharp[C_UsingTheMessageClass#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#10)]
 [!code-vb[C_UsingTheMessageClass#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#10)]  
  
 Allo stesso modo, potrebbe essere necessario eseguire l'override di `OnCreateBufferedCopy` per restituire la classe derivata `MessageBuffer` personalizzata.  
  
 Oltre a fornire il contenuto del corpo del messaggio, la classe derivata del messaggio deve anche eseguire l'override delle proprietà `Version`, `Headers` e `Properties`.  
  
 Si noti che se si crea una copia di un messaggio, la copia usa le intestazioni del messaggio dell'originale.  
  
### <a name="other-members-that-can-be-overridden"></a>Altri membri di cui è possibile eseguire l'override  
 È possibile eseguire l'override dei <xref:System.ServiceModel.Channels.Message.OnWriteStartEnvelope%2A> <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A> metodi, e <xref:System.ServiceModel.Channels.Message.OnWriteStartBody%2A> per specificare come vengono scritti la busta SOAP, le intestazioni SOAP e i tag di inizio dell'elemento del corpo SOAP. Normalmente corrispondono a `<soap:Envelope>` , `<soap:Header>` e `<soap:Body>` . In genere, questi metodi non scrivono alcun elemento se la proprietà <xref:System.ServiceModel.Channels.Message.Version> restituisce <xref:System.ServiceModel.Channels.MessageVersion.None>.  
  
> [!NOTE]
> L'implementazione predefinita di `OnGetReaderAtBodyContents` chiama `OnWriteStartEnvelope` e `OnWriteStartBody` prima di chiamare `OnWriteBodyContents` e memorizzare i risultati nel buffer. Le intestazioni non vengono scritte.  
  
 Eseguire l'override del metodo <xref:System.ServiceModel.Channels.Message.OnWriteMessage%2A> per modificare il modo in cui viene costruito l'intero messaggio dai diversi pezzi. Il metodo `OnWriteMessage` viene chiamato da <xref:System.ServiceModel.Channels.Message.WriteMessage%2A> e dall'implementazione di <xref:System.ServiceModel.Channels.Message.OnCreateBufferedCopy%2A> predefinita. Si noti che l'esecuzione dell'ovverride di <xref:System.ServiceModel.Channels.Message.WriteMessage%2A> non è una procedura consigliata. È preferibile eseguire l'override dei metodi `On` appropriati, ad esempio, <xref:System.ServiceModel.Channels.Message.OnWriteStartEnvelope%2A>, <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A> e <xref:System.ServiceModel.Channels.BodyWriter.OnWriteBodyContents%2A>.  
  
 Eseguire l'override di <xref:System.ServiceModel.Channels.Message.OnBodyToString%2A> per ignorare come viene rappresentato il corpo del messaggio durante il debug. L'impostazione predefinita consiste nel rappresentarlo come tre punti ("..."). Si noti che questo metodo può essere chiamato più volte, quando lo stato del messaggio è diverso da Chiuso. Un'implementazione di questo metodo non dovrebbe mai provocare un'azione che deve essere eseguita una sola volta, ad esempio la lettura da un flusso forward-only.  
  
 Eseguire l'override del metodo <xref:System.ServiceModel.Channels.Message.OnGetBodyAttribute%2A> per consentire l'accesso agli attributi sull'elemento corpo SOAP. Questo metodo può essere chiamato il numero di volte desiderato, ma il tipo `Message` di base garantisce che venga chiamato solo quando il messaggio si trova nello stato Creato. Non è necessario per controllare lo stato in un'implementazione. L'implementazione predefinita restituisce sempre `null`, per indicare che non sono presenti attributi sull'elemento corpo.  
  
 Se l'oggetto `Message` deve eseguire particolari operazioni di pulitura quando il corpo del messaggio non è più necessario, è possibile eseguire l'override di <xref:System.ServiceModel.Channels.Message.OnClose%2A>. L'implementazione predefinita non esegue alcuna operazione.  
  
 Le proprietà `IsEmpty` e `IsFault` possono essere sottoposte a override. Per impostazione predefinita, entrambe restituiscono `false`.

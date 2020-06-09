---
title: Architettura client
ms.date: 03/30/2017
ms.assetid: 02624403-0d77-41cb-9a86-ab55e98c7966
ms.openlocfilehash: c873368b82551312d203eb28d208eb6e3f50c89b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84587001"
---
# <a name="client-architecture"></a>Architettura client
Le applicazioni utilizzano oggetti client Windows Communication Foundation (WCF) per richiamare le operazioni del servizio. In questo argomento vengono illustrati gli oggetti client WCF, i canali client WCF e le relative relazioni con l'architettura del canale sottostante. Per una panoramica di base sugli oggetti client WCF, vedere [Cenni preliminari sul client WCF](../wcf-client-overview.md). Per ulteriori informazioni sul livello del canale, vedere [estensione del livello del canale](../extending/extending-the-channel-layer.md).  
  
## <a name="overview"></a>Panoramica  
 Il runtime del modello di servizio crea client WCF, che sono composti da quanto segue:  
  
- Un'implementazione client di un contratto di servizio generata automaticamente, che trasforma le chiamate del codice dell'applicazione in messaggi in uscita e i messaggi di risposta in parametri di output e valori restituiti che possono essere recuperati dall'applicazione.  
  
- Un'implementazione di un'interfaccia di controllo (<xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>), che raggruppa le varie interfacce e fornisce accesso alle funzionalità di controllo, tra cui la possibilità di chiudere la sessione client ed eliminare il canale.  
  
- Un canale client creato in base alle impostazioni di configurazione specificate dall'associazione utilizzata.  
  
 Le applicazioni possono creare tali client su richiesta, tramite <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> o creando un'istanza di una <xref:System.ServiceModel.ClientBase%601> classe derivata generata dallo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md). Queste classi client generate incapsulano e delegano a un'implementazione del canale client che viene costruita dinamicamente da una classe <xref:System.ServiceModel.ChannelFactory>. Il canale client e la channel factory che le producono costituiscono pertanto il punto centrale d'interesse di questo argomento.  
  
## <a name="client-objects-and-client-channels"></a>Oggetti client e canali client  
 L'interfaccia di base dei client WCF è l' <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> interfaccia, che espone la funzionalità client di base, nonché la funzionalità degli oggetti di comunicazione di base di <xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType> , la funzionalità di contesto di <xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType> e il comportamento estendibile di <xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType> .  
  
 L'interfaccia <xref:System.ServiceModel.IClientChannel>, tuttavia, non definisce contratti di servizio. Sono dichiarati dall'interfaccia del contratto di servizio (in genere generata dai metadati del servizio usando uno strumento come [ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)). I tipi di client WCF estendono sia <xref:System.ServiceModel.IClientChannel> che l'interfaccia del contratto di servizio di destinazione per consentire alle applicazioni di chiamare direttamente le operazioni e avere accesso alla funzionalità di run-time lato client. La creazione di un client WCF fornisce <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> oggetti WCF con le informazioni necessarie per creare un runtime in grado di connettersi e interagire con l'endpoint di servizio configurato.  
  
 Come indicato in precedenza, i due tipi di client WCF devono essere configurati prima di poterli utilizzare. I tipi di client WCF più semplici sono oggetti che derivano da <xref:System.ServiceModel.ClientBase%601> (o <xref:System.ServiceModel.DuplexClientBase%601> se il contratto di servizio è un contratto duplex). Per creare questi tipi, è possibile utilizzare un costruttore configurato a livello di codice o un file di configurazione che viene quindi chiamato direttamente per richiamare le operazioni del servizio. Per una panoramica di base degli <xref:System.ServiceModel.ClientBase%601> oggetti, vedere [Cenni preliminari sui client WCF](../wcf-client-overview.md).  
  
 Il secondo tipo di client è quello generato in fase di esecuzione da una chiamata al metodo <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>. Le applicazioni interessate con un controllo rigoroso delle specifiche di comunicazione usano in genere questo tipo di client, denominato *oggetto canale client*, perché consente un'interazione più diretta rispetto al sistema di canale e di runtime client sottostante.  
  
## <a name="channel-factories"></a>Channel factory  
 La classe responsabile della creazione del run-time sottostante che supporta le chiamate client è la classe <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>. Gli oggetti client WCF e gli oggetti canale client WCF utilizzano un <xref:System.ServiceModel.ChannelFactory%601> oggetto per creare istanze. l' <xref:System.ServiceModel.ClientBase%601> oggetto client derivato incapsula la gestione della channel factory, ma per diversi scenari è perfettamente ragionevole utilizzare direttamente la channel factory. Lo scenario più comune si ha quando si desidera creare ripetutamente nuovi canali client da una factory esistente. Se si utilizza un oggetto client, è possibile ottenere la channel factory sottostante da un oggetto client WCF chiamando la <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A?displayProperty=nameWithType> Proprietà.  
  
 La cosa importante da ricordare a proposito delle channel factory è che creano nuove istanze di canali client per la configurazione fornita loro prima di chiamare il metodo <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType>. Quando si chiama <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A> (o <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> , <xref:System.ServiceModel.ClientBase%601.CreateChannel%2A?displayProperty=nameWithType> o qualsiasi operazione su un oggetto client WCF), non è possibile modificare la channel factory e si prevede di ottenere i canali per istanze del servizio diverse, anche se si sta semplicemente modificando l'indirizzo dell'endpoint di destinazione. Se si desidera creare un oggetto client o un canale client con una configurazione diversa, è necessario prima creare una nuova channel factory.  
  
 Per ulteriori informazioni sui vari problemi di utilizzo degli oggetti client WCF e dei canali client WCF, vedere [accesso ai servizi tramite un client WCF](accessing-services-using-a-client.md).  
  
 Nelle due sezioni seguenti vengono descritte la creazione e l'utilizzo di oggetti canale client WCF.  
  
#### <a name="creating-a-new-wcf-client-channel-object"></a>Creazione di un nuovo oggetto canale client WCF  
 Per illustrare l'utilizzo di un canale client, si supponga che sia stato generato il contratto di servizio seguente.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Per eseguire la connessione a un servizio `ISampleService`, utilizzare direttamente l'interfaccia del contratto generata con una channel factory (<xref:System.ServiceModel.ChannelFactory%601>). Una volta creata e configurata una channel factory per un particolare contratto, è possibile chiamare il metodo <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A> per restituire oggetti canale client che possono essere utilizzati per comunicare con un servizio `ISampleService`.  
  
 Quando si usa la classe <xref:System.ServiceModel.ChannelFactory%601> con un'interfaccia del contratto del servizio, per aprire, chiudere o interrompere in modo esplicito il canale è necessario eseguire il cast all'interfaccia <xref:System.ServiceModel.IClientChannel> . Per semplificare l'uso, lo strumento Svcutil.exe genera inoltre un'interfaccia di supporto che implementa l'interfaccia del contratto del servizio e <xref:System.ServiceModel.IClientChannel> per consentire l'interazione con l'infrastruttura del canale client senza dovere eseguire il cast. Nel codice seguente viene illustrata la definizione di un canale client di supporto che implementa il contratto del servizio precedente.  
  
 [!code-csharp[C_GeneratedCodeFiles#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#13)]  
  
#### <a name="creating-a-new-wcf-client-channel-object"></a>Creazione di un nuovo oggetto canale client WCF  
 Per utilizzare un canale client per la connessione a un servizio `ISampleService`, è necessario utilizzare direttamente l'interfaccia del contratto generata (o la versione di supporto) con una channel factory, passando il tipo dell'interfaccia del contratto come parametro di tipo. Una volta creata e configurata una channel factory per un particolare contratto, è possibile chiamare il metodo <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> per restituire oggetti canale client che possono essere utilizzati per comunicare con un servizio `ISampleService`.  
  
 Quando vengono creati, gli oggetti canale client implementano <xref:System.ServiceModel.IClientChannel> e l'interfaccia del contratto. È pertanto possibile utilizzarli direttamente per chiamare operazioni che interagiscono con un servizio che supporta tale contratto.  
  
 La differenza tra l'utilizzo di oggetti client e di oggetti canale client consiste solo nel maggiore controllo e facilità di utilizzo da parte degli sviluppatori. Molti sviluppatori che hanno familiarità con gli oggetti e le classi preferiscono utilizzare l'oggetto client WCF anziché il canale client WCF.  
  
 Per un esempio, vedere [procedura: usare ChannelFactory](how-to-use-the-channelfactory.md).

---
title: Architettura client
ms.date: 03/30/2017
ms.assetid: 02624403-0d77-41cb-9a86-ab55e98c7966
ms.openlocfilehash: 4ced24f370e2ab54528c6adb2b3617d3d849e745
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="client-architecture"></a>Architettura client
Le applicazioni utilizzano oggetti client di Windows Communication Foundation (WCF) per richiamare operazioni del servizio. In questo argomento vengono illustrati gli oggetti client WCF, i canali client WCF e le relative relazioni con l'architettura del canale sottostante. Per una panoramica di base degli oggetti client WCF, vedere [panoramica dei Client WCF](../../../../docs/framework/wcf/wcf-client-overview.md). Per ulteriori informazioni sul livello di canale, vedere [estendendo il livello del canale](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md).  
  
## <a name="overview"></a>Panoramica  
 Il modello di servizio runtime crea client WCF, che sono costituiti da quanto segue:  
  
-   Un'implementazione client di un contratto di servizio generata automaticamente, che trasforma le chiamate del codice dell'applicazione in messaggi in uscita e i messaggi di risposta in parametri di output e valori restituiti che possono essere recuperati dall'applicazione.  
  
-   Un'implementazione di un'interfaccia di controllo (<xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>), che raggruppa le varie interfacce e fornisce accesso alle funzionalità di controllo, tra cui la possibilità di chiudere la sessione client ed eliminare il canale.  
  
-   Un canale client creato in base alle impostazioni di configurazione specificate dall'associazione utilizzata.  
  
 Applicazioni possono creare tali client su richiesta, tramite un <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> o creando un'istanza di un <xref:System.ServiceModel.ClientBase%601> classe derivata, viene generato dal [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Queste classi client generate incapsulano e delegano a un'implementazione del canale client che viene costruita dinamicamente da una classe <xref:System.ServiceModel.ChannelFactory>. Il canale client e la channel factory che le producono costituiscono pertanto il punto centrale d'interesse di questo argomento.  
  
## <a name="client-objects-and-client-channels"></a>Oggetti client e canali client  
 L'interfaccia di base di client WCF è il <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> interfaccia, che espone funzionalità client principale, nonché la funzionalità dell'oggetto di comunicazione di base <xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType>, la funzionalità del contesto di <xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType>e il comportamento estensibile di <xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType>.  
  
 L'interfaccia <xref:System.ServiceModel.IClientChannel>, tuttavia, non definisce contratti di servizio. Quelli dichiarati dall'interfaccia del contratto di servizio (in genere generato dai metadati del servizio utilizzando uno strumento come il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)). Tipi di client WCF estendono sia <xref:System.ServiceModel.IClientChannel> e l'interfaccia del contratto di servizio di destinazione per consentire alle applicazioni di chiamare operazioni direttamente e inoltre hanno accesso alla funzionalità di runtime lato client. La creazione di un client WCF fornisce WCF<xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> oggetti che possono connettersi e interagire con l'endpoint di servizio configurato con le informazioni necessarie per creare una fase di esecuzione.  
  
 Come accennato in precedenza, i due tipi di client WCF devono essere configurati prima di utilizzarli. I tipi di client WCF più semplici sono oggetti che derivano da <xref:System.ServiceModel.ClientBase%601> (o <xref:System.ServiceModel.DuplexClientBase%601> se il contratto di servizio è un contratto duplex). Per creare questi tipi, è possibile utilizzare un costruttore configurato a livello di codice o un file di configurazione che viene quindi chiamato direttamente per richiamare le operazioni del servizio. Per una panoramica di base di <xref:System.ServiceModel.ClientBase%601> degli oggetti, vedere [panoramica dei Client WCF](../../../../docs/framework/wcf/wcf-client-overview.md).  
  
 Il secondo tipo di client è quello generato in fase di esecuzione da una chiamata al metodo <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>. Nelle applicazioni interessate a livello di controllo delle specifiche di comunicazione in genere utilizzano questo tipo di client, chiamato un *oggetto canale client*, poiché consente un'interazione più diretta rispetto al valore sottostante client in fase di esecuzione e il canale System.  
  
## <a name="channel-factories"></a>Channel factory  
 La classe responsabile della creazione del run-time sottostante che supporta le chiamate client è la classe <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>. Utilizzo di oggetti del canale sia oggetti client WCF e client WCF un <xref:System.ServiceModel.ChannelFactory%601> oggetto per creare istanze; il <xref:System.ServiceModel.ClientBase%601> oggetto client derivato incapsula la gestione della channel factory, ma per il numero di scenari è possibile utilizzare il factory del canale direttamente. Lo scenario più comune si ha quando si desidera creare ripetutamente nuovi canali client da una factory esistente. Se si utilizza un oggetto client, è possibile ottenere la channel factory sottostante da un oggetto client WCF chiamando il <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A?displayProperty=nameWithType> proprietà.  
  
 La cosa importante da ricordare a proposito delle channel factory è che creano nuove istanze di canali client per la configurazione fornita loro prima di chiamare il metodo <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType>. Dopo aver chiamato <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A> (o <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.ClientBase%601.CreateChannel%2A?displayProperty=nameWithType>, oppure qualsiasi operazione su un oggetto client WCF), non è possibile modificare la channel factory e aspettarsi di ottenere canali per le istanze del servizio diversi, anche se si modifica soltanto l'indirizzo dell'endpoint di destinazione. Se si desidera creare un oggetto client o un canale client con una configurazione diversa, è necessario prima creare una nuova channel factory.  
  
 Per ulteriori informazioni sui vari problemi utilizzando oggetti del client WCF e canali client di WCF, vedere [accesso ai servizi tramite Client WCF](../../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md).  
  
 Due sezioni seguenti vengono descritti la creazione e utilizzo di oggetti canale client WCF.  
  
#### <a name="creating-a-new-wcf-client-channel-object"></a>Creazione di un nuovo oggetto canale client WCF  
 Per illustrare l'utilizzo di un canale client, si supponga che sia stato generato il contratto di servizio seguente.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Per eseguire la connessione a un servizio `ISampleService`, utilizzare direttamente l'interfaccia del contratto generata con una channel factory (<xref:System.ServiceModel.ChannelFactory%601>). Una volta creata e configurata una channel factory per un particolare contratto, è possibile chiamare il metodo <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A> per restituire oggetti canale client che possono essere utilizzati per comunicare con un servizio `ISampleService`.  
  
 Quando si usa la classe <xref:System.ServiceModel.ChannelFactory%601> con un'interfaccia del contratto del servizio, per aprire, chiudere o interrompere in modo esplicito il canale è necessario eseguire il cast all'interfaccia <xref:System.ServiceModel.IClientChannel>. Per semplificare l'uso, lo strumento Svcutil.exe genera inoltre un'interfaccia di supporto che implementa l'interfaccia del contratto del servizio e <xref:System.ServiceModel.IClientChannel> per consentire l'interazione con l'infrastruttura del canale client senza dovere eseguire il cast. Nel codice seguente viene illustrata la definizione di un canale client di supporto che implementa il contratto del servizio precedente.  
  
 [!code-csharp[C_GeneratedCodeFiles#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#13)]  
  
#### <a name="creating-a-new-wcf-client-channel-object"></a>Creazione di un nuovo oggetto canale client WCF  
 Per utilizzare un canale client per la connessione a un servizio `ISampleService`, è necessario utilizzare direttamente l'interfaccia del contratto generata (o la versione di supporto) con una channel factory, passando il tipo dell'interfaccia del contratto come parametro di tipo. Una volta creata e configurata una channel factory per un particolare contratto, è possibile chiamare il metodo <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> per restituire oggetti canale client che possono essere utilizzati per comunicare con un servizio `ISampleService`.  
  
 Quando vengono creati, gli oggetti canale client implementano <xref:System.ServiceModel.IClientChannel> e l'interfaccia del contratto. È pertanto possibile utilizzarli direttamente per chiamare operazioni che interagiscono con un servizio che supporta tale contratto.  
  
 La differenza tra l'utilizzo di oggetti client e di oggetti canale client consiste solo nel maggiore controllo e facilità di utilizzo da parte degli sviluppatori. Molti sviluppatori sono abituati a lavorare con le classi e gli oggetti preferiranno utilizzare l'oggetto client WCF anziché il canale client WCF.  
  
 Per un esempio, vedere [procedura: usare ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md).

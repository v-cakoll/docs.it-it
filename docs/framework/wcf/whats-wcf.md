---
title: Informazioni su Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation [WCF], technology overview
- technology overview [WCF]
- WCF [WCF], technology overview
ms.assetid: 40e1009d-ef15-450b-9848-62eabe5e5738
ms.openlocfilehash: e49b393b9dd09a513066a6cb3612ad9f938e9adb
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
---
# <a name="what-is-windows-communication-foundation"></a>Informazioni su Windows Communication Foundation
Windows Communication Foundation (WCF) è un framework per la compilazione di applicazioni orientate ai servizi. Utilizzo di WCF, è possibile inviare dati come messaggi asincroni da un endpoint del servizio a un altro. Un endpoint del servizio può appartenere a un servizio disponibile in modo continuo ospitato da IIS oppure essere un servizio ospitato in un'applicazione. Un endpoint può essere un client di un servizio che richiede dati da un endpoint del servizio. Il messaggio può essere semplice come una parola o come un singolo carattere inviato in formato XML o complesso come un flusso di dati binari. Di seguito vengono indicati alcuni scenari di esempio:  
  
-   Servizio protetto per elaborare le transazioni aziendali.  
  
-   Servizio che fornisce dati correnti ad altri, ad esempio un rapporto sul traffico o un altro servizio di monitoraggio.  
  
-   Servizio di chat che consente a due persone di comunicare o di scambiare dati in tempo reale.  
  
-   Applicazione dashboard che esegue il polling di uno o più servizi per i dati e che li visualizza in una presentazione logica.  
  
-   Esposizione di un flusso di lavoro implementato utilizzando Windows Workflow Foundation come servizio WCF.  
  
-   Applicazione Silverlight per eseguire il polling di un servizio per i feed di dati più recenti.  
  
 Durante la creazione di tali applicazioni possibile prima l'esistenza di WCF, WCF semplifica lo sviluppo degli endpoint senza precedenti. In sintesi, WCF è progettato per offrire un approccio gestibile alla creazione di servizi Web e i client del servizio Web.  
  
## <a name="features-of-wcf"></a>Funzionalità di WCF  
 WCF comprende il set di funzionalità seguente. Per altre informazioni, vedere [dettagli delle funzionalità di WCF](../../../docs/framework/wcf/feature-details/index.md).  
  
-   **Orientamento ai servizi**  
  
     Una conseguenza dell'utilizzo degli standard WS è che WCF consente di creare *orientata* applicazioni. Per architettura orientata ai servizi (SOA, Service-oriented architecture) si intende un'architettura che si basa sui servizi Web per inviare e ricevere dati. I servizi sono in genere caratterizzati dal vantaggio di essere ad accoppiamento debole anziché hardcoded da un'applicazione a un'altra. Una relazione ad accoppiamento debole implica che un client creato in una qualsiasi piattaforma possa connettersi a un servizio qualsiasi a condizione che vengano soddisfatti i contratti essenziali.  
  
-   **Interoperabilità**  
  
     WCF implementa moderni standard del settore per l'interoperabilità dei servizi Web. Per ulteriori informazioni sugli standard supportati, vedere [interoperabilità e integrazione](../../../docs/framework/wcf/feature-details/interoperability-and-integration.md).  
  
-   **Più modelli di messaggio**  
  
     Per scambiare i messaggi, sono disponibili più modelli. Il modello più comune è di tipo request/reply, in base al quale un endpoint richiede i dati a un altro endpoint che invia la risposta. Sono disponibili altri tipi di modelli in cui ad esempio un singolo endpoint invia un messaggio unidirezionale senza attendere una risposta. Un modello più complesso è costituito da un modello di scambio duplex in base al quale due endpoint stabiliscono una connessione e inviano i dati dall'uno all'altro in modo analogo a un'applicazione di messaggistica immediata. Per ulteriori informazioni sull'implementazione di scambio di messaggi diversi Vedere modelli che usano WCF [contratti](../../../docs/framework/wcf/feature-details/contracts.md).  
  
-   **Metadati del servizio**  
  
     WCF supporta la pubblicazione dei metadati di servizio tramite formati specificati in standard del settore, ad esempio WSDL, XML Schema e WS-Policy. Tali metadati possono essere utilizzati per generare e configurare i client per accedere ai servizi WCF automaticamente. I metadati possono inoltre essere pubblicati tramite protocolli HTTP e HTTPS oppure utilizzando lo standard WS-Metadata Exchange. Per altre informazioni, vedere [metadati](../../../docs/framework/wcf/feature-details/metadata.md).  
  
-   **Contratti dati**  
  
     Poiché WCF è stato compilato utilizzando la [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], include anche codice-metodi intuitivi per fornire i contratti da applicare. Uno dei tipi di contratti più generali è il contratto dati. In pratica, quando si crea il codice del servizio in Visual C# o Visual Basic, il modo più semplice di gestire i dati è costituito dalla creazione di classi che rappresentano un'entità dati con proprietà che appartengono all'entità stessa. WCF include un sistema completo per l'utilizzo di dati in questo modo facile. Dopo che sono state create le classi che rappresentano i dati, il servizio genera automaticamente i metadati che consentono ai client di essere conformi ai tipi di dati progettati. Per altre informazioni, vedere [utilizzando i contratti dati](../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
  
-   **Sicurezza**  
  
     È possibile crittografare i dati per proteggere la privacy nonché chiedere agli utenti di eseguire l'autenticazione prima che siano in grado di ricevere messaggi. La sicurezza può essere implementata utilizzando standard noti, ad esempio SSL o WS-SecureConversation. Per ulteriori informazioni, vedere [Sicurezza](../../../docs/framework/wcf/feature-details/security.md).  
  
-   **Più trasporti e codifiche**  
  
     Per inviare i messaggi, è possibile utilizzare uno dei numerosi protocolli di trasporto e codifiche predefiniti. La maggior parte delle comuni protocollo e la codifica è per l'invio di messaggi SOAP utilizzando il protocollo HTTP (HyperText Transfer) per l'utilizzo sul World Wide Web con codifica di testo. In alternativa, WCF consente di inviare messaggi tramite TCP, named pipe o MSMQ. Tali messaggi possono essere codificati come testo oppure utilizzando un formato binario ottimizzato.  I dati binari possono essere inviati in modo efficiente tramite lo standard MTOM. Se nessuna delle codifiche o nessuno dei trasporti forniti soddisfa le esigenze, è possibile creare una codifica o un trasporto personalizzato. Per ulteriori informazioni sui trasporti e codifiche supportati da WCF, vedere [trasporti](../../../docs/framework/wcf/feature-details/transports.md).  
  
-   **Messaggi in coda e affidabili**  
  
     WCF supporta lo scambio di messaggi affidabili affidabile a sessioni sicure implementate tramite WS-Reliable Messaging e MSMQ. Per ulteriori informazioni sul supporto di messaggistica in coda e affidabile in WCF, vedere [code e sessioni affidabili](../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).  
  
-   **Messaggi durevoli**  
  
     Per messaggio durevole si intende un messaggio che non viene mai perso a causa di un'interruzione della comunicazione. I messaggi presenti in un modello di questo tipo vengono sempre salvati in un database. Se si verifica un'interruzione, quando la connessione viene ripristinata è possibile riprendere lo scambio dei messaggi. È anche possibile creare un messaggio durevole utilizzando Windows Workflow Foundation (WF). Per altre informazioni, vedere [servizi flussi di lavoro](../../../docs/framework/wcf/feature-details/workflow-services.md).  
  
-   **Transazioni**  
  
     In WCF il supporto delle transazioni viene inoltre realizzato tramite uno dei tre modelli seguenti: WS-AtomicTtransactions, le interfacce API nello spazio dei nomi <xref:System.Transactions> e Microsoft Distributed Transaction Coordinator. Per ulteriori informazioni sulla transazione vedere supporto in WCF [transazioni](../../../docs/framework/wcf/feature-details/transactions-in-wcf.md).  
  
-   **Supporto AJAX e REST**  
  
     REST è un esempio di una tecnologia Web 2.0 in evoluzione. WCF può essere configurato per elaborare dati XML "semplici" che non sono incapsulati in una busta SOAP. WCF può anche essere estesa per supportare formati XML specifici, ad esempio ATOM (uno standard RSS diffuso) e anche formati di non XML, ad esempio JavaScript Object Notation (JSON).  
  
-   **Extensibility**  
  
     L'architettura WCF è un numero di punti di estendibilità. Se è necessaria ulteriore capacità, sono disponibili punti di ingresso che consentono di personalizzare il comportamento di un servizio. Per ulteriori informazioni sulle estendibilità disponibili vedere punti [estensione di WCF](../../../docs/framework/wcf/extending/index.md).  
  
## <a name="wcf-integration-with-other-microsoft-technologies"></a>Integrazione di WCF con altre tecnologie  
 WCF è una piattaforma estremamente flessibile. Grazie a questa notevole flessibilità, WCF viene usato anche in diversi altri prodotti Microsoft. Per comprendere le nozioni di base di WCF, si ha un vantaggio immediato se si utilizza anche uno di questi prodotti.  
  
 La prima tecnologia per l'associazione con WCF è stata Windows Workflow Foundation (WF). I flussi di lavoro semplificano lo sviluppo di applicazioni incapsulando i passaggi nel flusso di lavoro come "attività". Nella prima versione di Windows Workflow Foundation, lo sviluppatore doveva creare un host del flusso di lavoro. La prossima versione di Windows Workflow Foundation è stata integrata con WCF. Qualsiasi flusso di lavoro deve essere facilmente ospitato in un servizio WCF; è possibile farlo scegliendo automaticamente WF/WCF come tipo di progetto in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].  
  
 WCF viene inoltre utilizzato Microsoft BizTalk Server R2 come tecnologia di comunicazione. BizTalk è progettato per ricevere e trasformare i dati da un formato standardizzato in un altro. I messaggi devono essere recapitati nel MessageBox centrale di BizTalk in cui il messaggio può essere trasformato tramite un mapping rigoroso o tramite una delle funzionalità di BizTalk, ad esempio il motore del flusso di lavoro. BizTalk ora possibile utilizzare l'adapter WCF Line of Business (LOB) per recapitare i messaggi nel MessageBox.  
  
 Microsoft Silverlight è una piattaforma per la creazione di applicazioni Web interoperabili e potenti che consentono agli sviluppatori di realizzare siti Web con contenuto multimediale completo, ad esempio flusso video. Iniziare con la versione 2, Silverlight è stato incorporato WCF come tecnologia di comunicazione per connettere le applicazioni di Silverlight agli endpoint WCF.  
  
 Il [!INCLUDE[dublin](../../../includes/dublin-md.md)] server applicazioni è stato compilato appositamente per la distribuzione e la gestione delle applicazioni che utilizzano WCF per la comunicazione. Il [!INCLUDE[dublin2](../../../includes/dublin2-md.md)] sono disponibili le opzioni di configurazione e gli strumenti appositamente progettate per applicazioni basate su WCF.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel>  
 [Concetti fondamentali di Windows Communication Foundation](../../../docs/framework/wcf/fundamental-concepts.md)  
 [Architettura di Windows Communication Foundation](../../../docs/framework/wcf/architecture.md)  
 [Linee guida e procedure consigliate](../../../docs/framework/wcf/guidelines-and-best-practices.md)  
 [Esercitazione introduttiva](../../../docs/framework/wcf/getting-started-tutorial.md)  
 [Guida alla documentazione](../../../docs/framework/wcf/guide-to-the-documentation.md)  
 [Programmazione WCF di base](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [Esempi di Windows Communication Foundation](http://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)

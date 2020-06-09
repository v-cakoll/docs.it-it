---
title: Informazioni su Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation [WCF], technology overview
- technology overview [WCF]
- WCF [WCF], technology overview
ms.assetid: 40e1009d-ef15-450b-9848-62eabe5e5738
ms.openlocfilehash: fd78f2cd8266f94c577801623a84b56919c82973
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600854"
---
# <a name="what-is-windows-communication-foundation"></a>Informazioni su Windows Communication Foundation
Windows Communication Foundation (WCF) è un Framework per la compilazione di applicazioni orientate ai servizi. Con WCF è possibile inviare dati come messaggi asincroni da un endpoint del servizio a un altro. Un endpoint del servizio può appartenere a un servizio disponibile in modo continuo ospitato da IIS oppure essere un servizio ospitato in un'applicazione. Un endpoint può essere un client di un servizio che richiede dati da un endpoint del servizio. Il messaggio può essere semplice come una parola o come un singolo carattere inviato in formato XML o complesso come un flusso di dati binari. Di seguito vengono indicati alcuni scenari di esempio:

- Servizio protetto per elaborare le transazioni aziendali.

- Servizio che fornisce dati correnti ad altri, ad esempio un rapporto sul traffico o un altro servizio di monitoraggio.

- Servizio di chat che consente a due persone di comunicare o di scambiare dati in tempo reale.

- Applicazione dashboard che esegue il polling di uno o più servizi per i dati e che li visualizza in una presentazione logica.

- Esposizione di un flusso di lavoro implementato utilizzando Windows Workflow Foundation come servizio WCF.

- Applicazione Silverlight per eseguire il polling di un servizio per i feed di dati più recenti.

Sebbene la creazione di tali applicazioni fosse possibile prima dell'esistenza di WCF, WCF rende lo sviluppo degli endpoint più semplice che mai. In sintesi, WCF è progettato per offrire un approccio gestibile alla creazione di servizi Web e client di servizi Web.

## <a name="features-of-wcf"></a>Funzionalità di WCF

WCF include il set di funzionalità seguente. Per ulteriori informazioni, vedere la pagina relativa ai [Dettagli delle funzionalità WCF](./feature-details/index.md).

- **Orientamento ai servizi**

     Una conseguenza dell'utilizzo degli standard WS è che WCF consente di creare applicazioni *orientate ai servizi* . Per architettura orientata ai servizi (SOA, Service-oriented architecture) si intende un'architettura che si basa sui servizi Web per inviare e ricevere dati. I servizi sono in genere caratterizzati dal vantaggio di essere ad accoppiamento debole anziché hardcoded da un'applicazione a un'altra. Una relazione ad accoppiamento debole implica che un client creato in una qualsiasi piattaforma possa connettersi a un servizio qualsiasi a condizione che vengano soddisfatti i contratti essenziali.

- **Interoperabilità**

     WCF implementa standard di settore moderni per l'interoperabilità dei servizi Web. Per ulteriori informazioni sugli standard supportati, vedere [interoperabilità e integrazione](./feature-details/interoperability-and-integration.md).

- **Più modelli di messaggio**

     Per scambiare i messaggi, sono disponibili più modelli. Il modello più comune è di tipo request/reply, in base al quale un endpoint richiede i dati a un altro endpoint che invia la risposta. Sono disponibili altri tipi di modelli in cui ad esempio un singolo endpoint invia un messaggio unidirezionale senza attendere una risposta. Un modello più complesso è costituito da un modello di scambio duplex in base al quale due endpoint stabiliscono una connessione e inviano i dati dall'uno all'altro in modo analogo a un'applicazione di messaggistica immediata. Per ulteriori informazioni su come implementare modelli di scambio di messaggi diversi utilizzando WCF, vedere [contratti](./feature-details/contracts.md).

- **Metadati del servizio**

     WCF supporta la pubblicazione di metadati del servizio tramite formati specificati in standard del settore, ad esempio WSDL, XML Schema e WS-Policy. Questi metadati possono essere utilizzati per generare e configurare automaticamente i client per l'accesso ai servizi WCF. I metadati possono inoltre essere pubblicati tramite protocolli HTTP e HTTPS oppure utilizzando lo standard WS-Metadata Exchange. Per ulteriori informazioni, vedere [metadati](./feature-details/metadata.md).

- **Contratti dati**

     Poiché WCF viene compilato utilizzando la .NET Framework, include anche metodi descrittivi per fornire i contratti che si desidera applicare. Uno dei tipi di contratti più generali è il contratto dati. In pratica, quando si crea il codice del servizio in Visual C# o Visual Basic, il modo più semplice di gestire i dati è costituito dalla creazione di classi che rappresentano un'entità dati con proprietà che appartengono all'entità stessa. In WCF è incluso un sistema completo per l'utilizzo dei dati in modo semplice. Dopo che sono state create le classi che rappresentano i dati, il servizio genera automaticamente i metadati che consentono ai client di essere conformi ai tipi di dati progettati. Per ulteriori informazioni, vedere [utilizzo di contratti dati](feature-details/using-data-contracts.md).

- **Sicurezza**

     È possibile crittografare i dati per proteggere la privacy nonché chiedere agli utenti di eseguire l'autenticazione prima che siano in grado di ricevere messaggi. La sicurezza può essere implementata utilizzando standard noti, ad esempio SSL o WS-SecureConversation. Per altre informazioni, vedere [Sicurezza](./feature-details/security.md).

- **Più trasporti e codifiche**

     Per inviare i messaggi, è possibile utilizzare uno dei numerosi protocolli di trasporto e codifiche predefiniti. Il protocollo e la codifica più comuni sono l'invio di messaggi SOAP codificati tramite il protocollo HTTP (HyperText Transfer Protocol) da utilizzare nel World Wide Web. In alternativa, WCF consente di inviare messaggi tramite TCP, named pipe o MSMQ. Tali messaggi possono essere codificati come testo oppure utilizzando un formato binario ottimizzato.  I dati binari possono essere inviati in modo efficiente tramite lo standard MTOM. Se nessuna delle codifiche o nessuno dei trasporti forniti soddisfa le esigenze, è possibile creare una codifica o un trasporto personalizzato. Per ulteriori informazioni sui trasporti e le codifiche supportati da WCF, vedere [trasporti](./feature-details/transports.md).

- **Messaggi in coda e affidabili**

     WCF supporta lo scambio affidabile di messaggi tramite sessioni affidabili implementate tramite WS-Reliable Messaging e MSMQ. Per ulteriori informazioni sul supporto della messaggistica in coda e affidabile in WCF [, vedere Code e sessioni affidabili](./feature-details/queues-and-reliable-sessions.md).

- **Messaggi durevoli**

     Per messaggio durevole si intende un messaggio che non viene mai perso a causa di un'interruzione della comunicazione. I messaggi presenti in un modello di questo tipo vengono sempre salvati in un database. Se si verifica un'interruzione, quando la connessione viene ripristinata è possibile riprendere lo scambio dei messaggi. È inoltre possibile creare un messaggio durevole utilizzando il Windows Workflow Foundation (WF). Per ulteriori informazioni, vedere [servizi flusso di lavoro](./feature-details/workflow-services.md).

- **Transazioni**

     WCF supporta inoltre le transazioni che utilizzano uno dei tre modelli di transazione seguenti: WS-AtomicTransactions, le API nello <xref:System.Transactions> spazio dei nomi e Microsoft Distributed Transaction Coordinator. Per ulteriori informazioni sul supporto delle transazioni in WCF, vedere [transazioni](./feature-details/transactions-in-wcf.md).

- **Supporto AJAX e REST**

     REST è un esempio di una tecnologia Web 2.0 in evoluzione. WCF può essere configurato per elaborare dati XML "semplici" che non sono incapsulati in una busta SOAP. È anche possibile estendere WCF per supportare formati XML specifici, ad esempio ATOM (uno standard RSS diffuso) e anche formati non XML, ad esempio JavaScript Object Notation (JSON).

- **Estensibilità**

     L'architettura WCF dispone di un numero di punti di estensibilità. Se è necessaria ulteriore capacità, sono disponibili punti di ingresso che consentono di personalizzare il comportamento di un servizio. Per ulteriori informazioni sui punti di estendibilità disponibili, vedere [estensione di WCF](./extending/index.md).

## <a name="wcf-integration-with-other-microsoft-technologies"></a>Integrazione di WCF con altre tecnologie

WCF è una piattaforma flessibile. Grazie a questa estrema flessibilità, WCF viene usato anche in diversi altri prodotti Microsoft. Comprendendo le nozioni di base di WCF, si ha un vantaggio immediato se si utilizza anche uno di questi prodotti.

La prima tecnologia da associare a WCF è la Windows Workflow Foundation (WF). I flussi di lavoro semplificano lo sviluppo di applicazioni incapsulando i passaggi nel flusso di lavoro come "attività". Nella prima versione di Windows Workflow Foundation, uno sviluppatore doveva creare un host per il flusso di lavoro. La versione successiva di Windows Workflow Foundation è stata integrata con WCF. Ciò consentiva di ospitare facilmente un flusso di lavoro in un servizio WCF. Questa operazione può essere eseguita scegliendo automaticamente il tipo di progetto WF/WCF in Visual Studio 2012 o versione successiva.

Microsoft BizTalk Server R2 usa anche WCF come tecnologia di comunicazione. BizTalk è progettato per ricevere e trasformare i dati da un formato standardizzato in un altro. I messaggi devono essere recapitati nel MessageBox centrale di BizTalk in cui il messaggio può essere trasformato tramite un mapping rigoroso o tramite una delle funzionalità di BizTalk, ad esempio il motore del flusso di lavoro. BizTalk ora può utilizzare l'adapter line-of-business (LOB) WCF per recapitare i messaggi al MessageBox.

Microsoft Silverlight è una piattaforma per la creazione di applicazioni Web interoperabili e potenti che consentono agli sviluppatori di realizzare siti Web con contenuto multimediale completo, ad esempio flusso video. A partire dalla versione 2, Silverlight ha incorporato WCF come tecnologia di comunicazione per connettere le applicazioni Silverlight agli endpoint WCF.

Le funzionalità di hosting del server applicazioni di Windows Server AppFabric sono progettate in modo specifico per la distribuzione e la gestione di applicazioni che utilizzano WCF per la comunicazione. Le funzionalità di hosting includono strumenti avanzati e opzioni di configurazione progettate appositamente per le applicazioni abilitate per WCF.

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel>
- [Concetti fondamentali di Windows Communication Foundation](fundamental-concepts.md)
- [Architettura di Windows Communication Foundation](architecture.md)
- [Linee guida e procedure consigliate](guidelines-and-best-practices.md)
- [Esercitazione Introduzione](getting-started-tutorial.md)
- [Guida alla documentazione](guide-to-the-documentation.md)
- [Programmazione WCF di base](basic-wcf-programming.md)
- [Esempi di Windows Communication Foundation](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751514%28v=vs.90%29)

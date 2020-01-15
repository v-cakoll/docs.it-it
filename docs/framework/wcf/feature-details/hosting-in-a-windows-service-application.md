---
title: Hosting in un'applicazione di servizio Windows
ms.date: 03/30/2017
ms.assetid: f4199998-27f3-4dd9-aee4-0a4addfa9f24
ms.openlocfilehash: a07aade4619b644dadd1d5acdcb5252b305b94d0
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964482"
---
# <a name="hosting-in-a-windows-service-application"></a>Hosting in un'applicazione di servizio Windows
I servizi Windows, precedentemente noti come servizi Windows NT, offrono un modello di processo particolarmente adatto ad applicazioni che devono risiedere in un eseguibile a esecuzione prolungata e che non visualizzano alcuna forma di interfaccia utente. La durata del processo di un'applicazione di servizio Windows viene gestita da Gestione controllo servizi (SCM), che consente di avviare, interrompere e sospendere le applicazioni di servizio Windows. È possibile configurare un processo del servizio Windows per l'avvio automatico all'avvio del computer, rendendolo un ambiente host appropriato per le applicazioni "always on". Per ulteriori informazioni sulle applicazioni di servizio Windows, vedere [applicazioni di servizio Windows](https://go.microsoft.com/fwlink/?LinkId=89450).  
  
 Le applicazioni che ospitano servizi di Windows Communication Foundation a esecuzione prolungata (WCF) condividono molte caratteristiche con i servizi Windows. In particolare, i servizi WCF sono file eseguibili server con esecuzione prolungata che non interagiscono direttamente con l'utente e pertanto non implementano alcuna forma di interfaccia utente. Di conseguenza, l'hosting dei servizi WCF all'interno di un'applicazione di servizio Windows è un'opzione per la creazione di applicazioni WCF affidabili e a esecuzione prolungata.  
  
 Spesso gli sviluppatori WCF devono decidere se ospitare l'applicazione WCF all'interno di un'applicazione di servizio Windows o all'interno dell'ambiente di hosting di Internet Information Services (IIS) o del servizio Attivazione processo Windows (WAS). È consigliabile considerare l'uso di applicazioni di servizio Windows alle condizioni seguenti:  
  
- L'applicazione richiede l'attivazione esplicita. È, ad esempio, consigliabile usare servizi Windows quando l'applicazione deve essere avviata automaticamente all'avvio del server, invece di essere avviata dinamicamente in risposta al primo messaggio in ingresso.  
  
- Il processo che ospita l'applicazione deve restare in esecuzione una volta avviato. Una volta avviato, un processo di servizio Windows resta in esecuzione, a meno che non venga esplicitamente interrotto da un amministratore del server tramite Gestione controllo servizi. Le applicazioni ospitate in IIS o WAS possono essere avviate e interrotte dinamicamente, per usare le risorse di sistema in modo ottimale. Le applicazioni che richiedono il controllo esplicito sulla durata del processo host dovrebbero usare servizi Windows invece di IIS o WAS.  
  
- Il servizio WCF deve essere eseguito in Windows Server 2003 e utilizzare trasporti diversi da HTTP. In Windows Server 2003, l'ambiente di hosting di IIS 6,0 è limitato solo alla comunicazione HTTP. Le applicazioni di servizio Windows non sono soggette a questa restrizione e possono utilizzare qualsiasi trasporto supportato da WCF, tra cui NET. TCP, NET. pipe e NET. MSMQ.  
  
### <a name="to-host-wcf-inside-of-a-windows-service-application"></a>Per ospitare WCF in un'applicazione di servizio Windows  
  
1. Creare un'applicazione di servizio Windows. È possibile scrivere applicazioni di servizio Windows in codice gestito usando le classi nello spazio dei nomi <xref:System.ServiceProcess>. Questa applicazione deve includere una classe che eredita da <xref:System.ServiceProcess.ServiceBase>.  
  
2. Collegare la durata dei servizi WCF alla durata dell'applicazione di servizio Windows. In genere, si desidera che i servizi WCF ospitati in un'applicazione di servizio Windows diventino attivi all'avvio del servizio di hosting, interrompano l'ascolto dei messaggi quando il servizio di hosting viene arrestato e arrestano il processo di hosting quando il servizio WCF rileva un errore. Per ottenere questo risultato, è possibile procedere come segue:  
  
    - Eseguire l'override di <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> per aprire una o più istanze di <xref:System.ServiceModel.ServiceHost>. Una singola applicazione di servizio Windows può ospitare più servizi WCF che si avviano e si arrestano come gruppo.  
  
    - Eseguire l'override <xref:System.ServiceProcess.ServiceBase.OnStop%2A> per chiamare <xref:System.ServiceModel.Channels.CommunicationObject.Closed> sul <xref:System.ServiceModel.ServiceHost> tutti i servizi WCF in esecuzione avviati durante <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>.  
  
    - Eseguire la sottoscrizione all'evento <xref:System.ServiceModel.Channels.CommunicationObject.Faulted> di <xref:System.ServiceModel.ServiceHost> e usare la classe <xref:System.ServiceProcess.ServiceController> per arrestare l'applicazione di servizio Windows in caso di errore.  
  
     Le applicazioni di servizio Windows che ospitano servizi WCF vengono distribuite e gestite allo stesso modo delle applicazioni di servizio Windows che non utilizzano WCF.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceProcess>
- [Procedura dettagliata: creazione di un'applicazione di servizio Windows in Progettazione componenti](https://go.microsoft.com/fwlink/?LinkId=94875)
- [Procedura: Ospitare un servizio WCF in un servizio di Windows gestito](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)
- [Host del servizio Windows](../../../../docs/framework/wcf/samples/windows-service-host.md)
- [Architettura di programmazione delle applicazioni di servizio](https://go.microsoft.com/fwlink/?LinkId=94876)
- [Funzionalità di hosting di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))

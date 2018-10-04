---
title: Hosting in un'applicazione di servizio Windows
ms.date: 03/30/2017
ms.assetid: f4199998-27f3-4dd9-aee4-0a4addfa9f24
ms.openlocfilehash: 2b3935babec0c7cdc3ffca5dd11d693fdfee7a89
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48584130"
---
# <a name="hosting-in-a-windows-service-application"></a>Hosting in un'applicazione di servizio Windows
I servizi Windows, precedentemente noti come servizi Windows NT, offrono un modello di processo particolarmente adatto ad applicazioni che devono risiedere in un eseguibile a esecuzione prolungata e che non visualizzano alcuna forma di interfaccia utente. La durata del processo di un'applicazione di servizio Windows viene gestita da Gestione controllo servizi (SCM), che consente di avviare, interrompere e sospendere le applicazioni di servizio Windows. È possibile configurare un processo del servizio Windows per l'avvio automatico all'avvio del computer, rendendolo un ambiente host adatto per le applicazioni "always on". Per altre informazioni sulle applicazioni di servizio di Windows, vedere [le applicazioni del servizio Windows](https://go.microsoft.com/fwlink/?LinkId=89450).  
  
 Le applicazioni che ospitano servizi Windows Communication Foundation (WCF) a esecuzione prolungata condividono molte caratteristiche dei servizi di Windows. In particolare, i servizi WCF sono eseguibili server a esecuzione prolungata che non interagiscono direttamente con l'utente e non implementano quindi alcuna forma di interfaccia utente. Di conseguenza, l'hosting dei servizi WCF all'interno di un'applicazione del servizio Windows è un'opzione per la creazione di affidabili e a esecuzione prolungata, le applicazioni WCF.  
  
 Spesso, gli sviluppatori WCF necessario decidere se ospitare le applicazioni WCF all'interno di un'applicazione del servizio Windows o nell'ambiente di hosting Internet Information Services (IIS) o Windows Process Activation Service (WAS). È consigliabile considerare l'uso di applicazioni di servizio Windows alle condizioni seguenti:  
  
-   L'applicazione richiede l'attivazione esplicita. È, ad esempio, consigliabile usare servizi Windows quando l'applicazione deve essere avviata automaticamente all'avvio del server, invece di essere avviata dinamicamente in risposta al primo messaggio in ingresso.  
  
-   Il processo che ospita l'applicazione deve restare in esecuzione una volta avviato. Una volta avviato, un processo di servizio Windows resta in esecuzione, a meno che non venga esplicitamente interrotto da un amministratore del server tramite Gestione controllo servizi. Le applicazioni ospitate in IIS o WAS possono essere avviate e interrotte dinamicamente, per usare le risorse di sistema in modo ottimale. Le applicazioni che richiedono il controllo esplicito sulla durata del processo host dovrebbero usare servizi Windows invece di IIS o WAS.  
  
-   Il servizio WCF deve eseguire in Windows Server 2003 e usare trasporti diversi da HTTP. Su Windows Server 2003, l'ambiente host [!INCLUDE[iis601](../../../../includes/iis601-md.md)] è limitato alla sola comunicazione HTTP. Le applicazioni del servizio Windows non sono soggetti a questa restrizione e possono usare qualsiasi trasporto WCF supporta, inclusi NET. TCP, NET. pipe e NET. MSMQ.  
  
### <a name="to-host-wcf-inside-of-a-windows-service-application"></a>Per ospitare WCF in un'applicazione di servizio Windows  
  
1.  Creare un'applicazione di servizio Windows. È possibile scrivere applicazioni di servizio Windows in codice gestito usando le classi nello spazio dei nomi <xref:System.ServiceProcess>. Questa applicazione deve includere una classe che eredita da <xref:System.ServiceProcess.ServiceBase>.  
  
2.  Collegare la durata dei servizi WCF per la durata dell'applicazione del servizio Windows. In genere, è consigliabile servizi WCF ospitati in un'applicazione del servizio Windows divengano attivi quando viene avviato il servizio di hosting, interrompere l'ascolto dei messaggi quando viene arrestato, il servizio di hosting e arrestare il processo di hosting quando il servizio WCF incontra un errore. Per ottenere questo risultato, è possibile procedere come segue:  
  
    -   Eseguire l'override di <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> per aprire una o più istanze di <xref:System.ServiceModel.ServiceHost>. Una singola applicazione del servizio Windows può ospitare più servizi WCF che avviano e arrestano come gruppo.  
  
    -   Eseguire l'override <xref:System.ServiceProcess.ServiceBase.OnStop%2A> chiamare <xref:System.ServiceModel.Channels.CommunicationObject.Closed> nel <xref:System.ServiceModel.ServiceHost> tutti i servizi WCF in esecuzione avviati durante <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>.  
  
    -   Eseguire la sottoscrizione all'evento <xref:System.ServiceModel.Channels.CommunicationObject.Faulted> di <xref:System.ServiceModel.ServiceHost> e usare la classe <xref:System.ServiceProcess.ServiceController> per arrestare l'applicazione di servizio Windows in caso di errore.  
  
     Le applicazioni di servizio Windows che ospitano servizi WCF distribuite e gestite nello stesso modo come applicazioni di servizio Windows che non effettuano usano WCF.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceProcess>  
 [Procedura dettagliata: creazione di un'applicazione di servizio Windows in Progettazione componenti](https://go.microsoft.com/fwlink/?LinkId=94875)  
 [Procedura: Ospitare un servizio WCF in un servizio di Windows gestito](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)  
 [Host del servizio Windows](../../../../docs/framework/wcf/samples/windows-service-host.md)  
 [Architettura di programmazione delle applicazioni di servizio](https://go.microsoft.com/fwlink/?LinkId=94876)  
 [Windows Server AppFabric con funzionalità di Hosting](https://go.microsoft.com/fwlink/?LinkId=201276)

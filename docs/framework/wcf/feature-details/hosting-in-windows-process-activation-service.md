---
title: Hosting nel servizio di attivazione dei processi di Windows
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF], WAS
ms.assetid: d2b9d226-15b7-41fc-8c9a-cb651ac20ecd
ms.openlocfilehash: 5b234a00f3194fcf40a33d25302cff16d5999b05
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59082985"
---
# <a name="hosting-in-windows-process-activation-service"></a>Hosting nel servizio di attivazione dei processi di Windows
Il servizio di attivazione processo Windows (WAS) gestisce l'attivazione e la durata dei processi di lavoro che contengono applicazioni che servizi di Windows Communication Foundation (WCF) host. Il modello di processo WAS generalizza il modello di processo [!INCLUDE[iis601](../../../../includes/iis601-md.md)] per il server HTTP rimuovendo la dipendenza da HTTP. In questo modo i servizi WCF da usare HTTP e protocolli non HTTP, ad esempio NET. TCP, in un ambiente di hosting che supporta l'attivazione basata su messaggi e offre la possibilità di ospitare un numero elevato di applicazioni in un determinato computer.  
  
 Per altre informazioni sulla creazione di un servizio WCF che viene eseguito nell'ambiente di hosting di WAS, vedere [come: Ospitare un servizio WCF in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).  
  
 Il modello di processo WAS prevede diverse funzionalità che consentono una modalità di hosting delle applicazioni più efficace e gestibile e in cui le risorse vengono usate in maniera efficiente:  
  
-   L'attivazione basata su messaggi di applicazioni e applicazioni del processo di lavoro viene avviata e interrotta dinamicamente in risposta a elementi di lavoro in ingresso tramite protocolli di rete HTTP e non HTTP.  
  
-   Efficace riciclo di applicazioni e processi di lavoro per mantenere l'integrità delle applicazioni in esecuzione.  
  
-   Configurazione e gestione centralizzate delle applicazioni.  
  
-   Consente alle applicazioni di sfruttare il modello di processo IIS senza richiedere il footprint di distribuzione di un'installazione IIS completa.  
  
 Per altre informazioni sulle funzionalità WAS, vedere [IIS 7.0 Beta: Amministrazione di IIS 7.0 Web](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).  
  
 [Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=196496) funziona con [!INCLUDE[iisver](../../../../includes/iisver-md.md)] e Windows Process Activation Service (WAS) per fornire un ambiente per i servizi NET4 WCF e WF di hosting. Tali vantaggi includono la gestione del ciclo di vita del processo, il riciclo del processo, l'hosting condiviso, una rapida protezione dall'errore, la gestione dell'opzione orfano processo, l'attivazione su richiesta e il monitoraggio dello stato. Per informazioni dettagliate, vedere [funzionalità di Hosting di AppFabric](https://go.microsoft.com/fwlink/?LinkId=196494) e [concetti di Hosting](https://go.microsoft.com/fwlink/?LinkId=196495).  
  
## <a name="elements-of-the-was-addressing-model"></a>Elementi del modello di indirizzamento WAS  
 Le applicazioni hanno indirizzi URI (Uniform Resource Identifier), che sono le unità di codice la cui durata e il cui ambiente di esecuzione vengono gestiti dal server. Una singola istanza server WAS può accogliere numerose applicazioni diverse. I server organizzano le applicazioni in gruppi denominati *siti*. All'interno di un sito, le applicazioni vengono disposte in un ordine gerarchico che riflette la struttura degli URI che fungono da indirizzi esterni.  
  
 Gli indirizzi delle applicazioni sono composti di due parti: un prefisso URI di base e un indirizzo relativo specifico dell'applicazione (percorso), che, se uniti insieme, forniscono l'indirizzo esterno di un'applicazione. Il prefisso URI di base viene creato dall'associazione di sito e usato per tutte le applicazioni presenti nel sito. Gli indirizzi delle applicazioni vengono quindi creati aggiungendo frammenti del percorso specifico dell'applicazione (ad esempio, "/ formare") e li aggiunta al prefisso URI di base (ad esempio, "TCP: //localhost") per l'URI dell'applicazione completo.  
  
 Nella tabella seguente vengono illustrati diversi possibili scenari di indirizzamento per siti WAS con associazioni di sito HTTP e non HTTP.  
  
|Scenario|Associazioni di sito|Percorso dell'applicazione|URI dell'applicazione di base|  
|--------------|-------------------|----------------------|---------------------------|  
|Solo HTTP|http: *:80:\*|/appTwo|http://localhost/appTwo/|  
|HTTP e non HTTP|http: *:80:\*<br /><br /> net.tcp: 808:\*|/appTwo|http://localhost/appTwo/<br />net.tcp://localhost/appTwo/|  
|Solo non HTTP|net.pipe: *|/appThree|net.pipe://appThree/|  
  
 Possono essere indirizzati anche servizi e risorse all'interno di un'applicazione. All'interno di un'applicazione, le risorse dell'applicazione vengono indirizzate in relazione al percorso dell'applicazione di base. Ad esempio, si presupponga che un sito in un computer contoso.com abbia associazioni di sito per entrambi i protocolli HTTP e Net.TCP. Si presupponga inoltre che il sito contenga un'applicazione ubicata in /Billing, che espone un servizio in GetOrders.svc. Quindi, se il servizio GetOrders.svc espone un endpoint con un indirizzo relativo di SecureEndpoint, l'endpoint del servizio viene esposto nei due URI seguenti:  
  
- `http://contoso.com/Billing/GetOrders.svc/SecureEndpoint`
- `net.tcp://contoso.com/Billing/GetOrders.svc/SecureEndpoint`
  
## <a name="the-was-runtime"></a>Runtime WAS  
 Le applicazioni vengono organizzate in siti a scopo di indirizzamento e gestione. In fase di esecuzione, le applicazioni vengono inoltre raggruppate in pool. Un pool di applicazioni può contenere molte applicazioni diverse di molti siti diversi. Tutte le applicazioni in un pool di applicazioni condividono una serie comune di caratteristiche runtime. Ad esempio, vengono eseguite tutte nella stessa versione di Common Language Runtime (CLR) e tutte condividono un'identità di processo comune. Ogni pool di applicazioni corrisponde a un'istanza di un processo di lavoro (w3wp.exe). Ogni applicazione gestita in esecuzione in un pool di applicazioni condiviso è isolata dalle altre applicazioni da un AppDomain CLR.  
  
## <a name="see-also"></a>Vedere anche

- [Architettura di attivazione di WAS](../../../../docs/framework/wcf/feature-details/was-activation-architecture.md)
- [Configurazione di WAS per l'uso con WCF](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)
- [Procedura: Installare e configurare componenti di attivazione WCF](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)
- [Procedura: Ospitare un servizio WCF in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md)
- [Funzionalità di hosting di Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=201276)

---
title: Hosting nel servizio di attivazione dei processi di Windows
description: Informazioni su come gestisce l'attivazione e la durata dei processi di lavoro contenenti applicazioni che ospitano servizi WCF.
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF], WAS
ms.assetid: d2b9d226-15b7-41fc-8c9a-cb651ac20ecd
ms.openlocfilehash: 6b0b23c21762009341fd62c029431824dd26d6c3
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247260"
---
# <a name="hosting-in-windows-process-activation-service"></a>Hosting nel servizio di attivazione dei processi di Windows
Il servizio WAS (Windows Process Activation Service, Attivazione processo Windows) gestisce l'attivazione e la durata dei processi di lavoro contenenti le applicazioni che ospitano i servizi WCF (Windows Communication Foundation). Il modello di processo WAS consente di generalizzare il modello di processo IIS 6.0 per il server HTTP eliminando la dipendenza da HTTP. Questo consente ai servizi WCF di utilizzare sia protocolli HTTP che non HTTP, ad esempio NET. TCP, in un ambiente host che supporta l'attivazione basata su messaggi e offre la possibilità di ospitare un numero elevato di applicazioni in un determinato computer.  
  
 Per ulteriori informazioni sulla compilazione di un servizio WCF in esecuzione nell'ambiente di hosting WAS, vedere [procedura: ospitare un servizio WCF in was](how-to-host-a-wcf-service-in-was.md).  
  
 Il modello di processo WAS prevede diverse funzionalità che consentono una modalità di hosting delle applicazioni più efficace e gestibile e in cui le risorse vengono usate in maniera efficiente:  
  
- L'attivazione basata su messaggi di applicazioni e applicazioni del processo di lavoro viene avviata e interrotta dinamicamente in risposta a elementi di lavoro in ingresso tramite protocolli di rete HTTP e non HTTP.  
  
- Efficace riciclo di applicazioni e processi di lavoro per mantenere l'integrità delle applicazioni in esecuzione.  
  
- Configurazione e gestione centralizzate delle applicazioni.  
  
- Consente alle applicazioni di sfruttare il modello di processo IIS senza richiedere il footprint di distribuzione di un'installazione IIS completa.  
[Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff384253(v=azure.10)) funziona con IIS 7,0 e il servizio Attivazione processo Windows (was) per fornire un ambiente di hosting di applicazioni completo per i servizi WCF e WF NET4. Tali vantaggi includono la gestione del ciclo di vita del processo, il riciclo del processo, l'hosting condiviso, una rapida protezione dall'errore, la gestione dell'opzione orfano processo, l'attivazione su richiesta e il monitoraggio dello stato. Per informazioni dettagliate, vedere [funzionalità di hosting di AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10)) e [concetti di hosting di AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677371(v=azure.10)).  
  
## <a name="elements-of-the-was-addressing-model"></a>Elementi del modello di indirizzamento WAS  
 Le applicazioni hanno indirizzi URI (Uniform Resource Identifier), che sono le unità di codice la cui durata e il cui ambiente di esecuzione vengono gestiti dal server. Una singola istanza server WAS può accogliere numerose applicazioni diverse. I server organizzano le applicazioni in gruppi denominati *siti*. All'interno di un sito, le applicazioni vengono disposte in un ordine gerarchico che riflette la struttura degli URI che fungono da indirizzi esterni.  
  
 Gli indirizzi delle applicazioni sono composti di due parti: un prefisso URI di base e un indirizzo relativo specifico dell'applicazione (percorso), che, se uniti insieme, forniscono l'indirizzo esterno di un'applicazione. Il prefisso URI di base viene creato dall'associazione di sito e usato per tutte le applicazioni presenti nel sito. Gli indirizzi delle applicazioni vengono quindi costruiti prendendo i frammenti di percorso specifici dell'applicazione, ad esempio "/applicationOne", e aggiungendoli al prefisso URI di base (ad esempio, "NET. TCP://localhost") per arrivare all'URI completo dell'applicazione.  
  
 Nella tabella seguente vengono illustrati diversi possibili scenari di indirizzamento per siti WAS con associazioni di sito HTTP e non HTTP.  
  
|Scenario|Associazioni di sito|Percorso dell'applicazione|URI dell'applicazione di base|  
|--------------|-------------------|----------------------|---------------------------|  
|Solo HTTP|http: *: 80:\*|/appTwo|`http://localhost/appTwo/`|  
|HTTP e non HTTP|http: *: 80:\*<br /><br /> NET. TCP: 808:\*|/appTwo|`http://localhost/appTwo/`<br />`net.tcp://localhost/appTwo/`|  
|Solo non HTTP|net.pipe: *|/appThree|`net.pipe://appThree/`|  
  
 Possono essere indirizzati anche servizi e risorse all'interno di un'applicazione. All'interno di un'applicazione, le risorse dell'applicazione vengono indirizzate in relazione al percorso dell'applicazione di base. Ad esempio, si presupponga che un sito in un computer contoso.com abbia associazioni di sito per entrambi i protocolli HTTP e Net.TCP. Si presupponga inoltre che il sito contenga un'applicazione ubicata in /Billing, che espone un servizio in GetOrders.svc. Quindi, se il servizio GetOrders.svc espone un endpoint con un indirizzo relativo di SecureEndpoint, l'endpoint del servizio viene esposto nei due URI seguenti:  
  
- `http://contoso.com/Billing/GetOrders.svc/SecureEndpoint`
- `net.tcp://contoso.com/Billing/GetOrders.svc/SecureEndpoint`
  
## <a name="the-was-runtime"></a>Runtime WAS  
 Le applicazioni vengono organizzate in siti a scopo di indirizzamento e gestione. In fase di esecuzione, le applicazioni vengono inoltre raggruppate in pool. Un pool di applicazioni può contenere molte applicazioni diverse di molti siti diversi. Tutte le applicazioni in un pool di applicazioni condividono una serie comune di caratteristiche runtime. Ad esempio, vengono eseguite tutte nella stessa versione di Common Language Runtime (CLR) e tutte condividono un'identità di processo comune. Ogni pool di applicazioni corrisponde a un'istanza di un processo di lavoro (w3wp.exe). Ogni applicazione gestita in esecuzione in un pool di applicazioni condiviso è isolata dalle altre applicazioni da un AppDomain CLR.  
  
## <a name="see-also"></a>Vedere anche

- [Architettura di attivazione WAS](was-activation-architecture.md)
- [Configurazione di WAS per l'uso con WCF](configuring-the-wpa--service-for-use-with-wcf.md)
- [Procedura: installare e configurare componenti di attivazione WCF](how-to-install-and-configure-wcf-activation-components.md)
- [Procedura: ospitare un servizio WCF in WAS](how-to-host-a-wcf-service-in-was.md)
- [Funzionalità di hosting di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))

---
title: Servizi host
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF]
ms.assetid: 192be927-6be2-4fda-98f0-e513c4881acc
ms.openlocfilehash: 4342b3d6219f0c996264bb7ed190b1204338ba64
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051156"
---
# <a name="hosting-services"></a>Servizi host
Per diventare attivo, un servizio deve essere ospitato all'interno di un ambiente di runtime che lo crea e ne controlla il contesto e la durata. Servizi Windows Communication Foundation (WCF) sono progettati per l'esecuzione in qualsiasi processo Windows che supporta codice gestito.  
  
 WCF fornisce un modello di programmazione unificato per la creazione di applicazioni orientate ai servizi. Questo modello di programmazione rimane coerente ed è indipendente dall'ambiente di runtime nel quale viene distribuito il servizio. In pratica, ciò significa che il codice per i servizi interessati rimane praticamente invariato a prescindere dall'opzione di hosting.  
  
 Le opzioni di hosting vanno dall'esecuzione in una semplice applicazione console ad ambienti server come un servizio Windows in esecuzione in un processo di lavoro gestito da Internet Information Services (IIS) o dal servizio di attivazione dei processi di Windows (WAS). Gli sviluppatori scelgono l'ambiente host che soddisfa i requisiti di distribuzione del servizio. Questi requisiti potrebbero derivare dalla piattaforma sulla quale viene distribuita l'applicazione, il trasporto sul quale deve inviare e ricevere messaggi o sul tipo di riciclo del processo e gestione di altri processi richiesti per assicurare la disponibilità adeguata o su altri requisiti di gestione o affidabilità. Nella prossima sezione vengono fornite informazioni e istruzioni sulle opzioni di hosting.  
  
## <a name="hosting-options"></a>Opzioni di hosting  
  
#### <a name="self-hosting-in-a-managed-application"></a>Self-hosting in un'applicazione gestita  
 Servizi WCF possono essere ospitati in qualsiasi applicazione gestita. Questa è l'opzione più flessibile perché richiede la distribuzione di un'infrastruttura minima. Incorporare il codice per il servizio all'interno del codice dell'applicazione gestita, quindi creare e aprire un'istanza di <xref:System.ServiceModel.ServiceHost> per rendere il servizio disponibile. Per altre informazioni, vedere [Procedura: Ospitare un servizio WCF in un'applicazione gestita](../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).  
  
 Questa opzione consente due scenari comuni: Servizi WCF in esecuzione all'interno di applicazioni console e applicazioni rich client, ad esempio quelle basate su Windows Presentation Foundation (WPF) o Windows Form (WinForms). Hosting di un servizio WCF all'interno di un'applicazione console è in genere utile durante la fase di sviluppo dell'applicazione. Agevola infatti il debug, l'ottenimento di informazioni di traccia per scoprire cosa accadde all'interno dell'applicazione e lo spostamento copiandole in nuove posizioni. Questa opzione di hosting consente inoltre ad applicazioni rich client, quali quelle [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] e Windows Form, di comunicare più facilmente con l'esterno. Ad esempio, un client di collaborazione peer-to-peer che utilizza [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] come interfaccia utente e ospita anche un servizio WCF che consente ad altri client di connettersi e condividere informazioni.  
  
#### <a name="managed-windows-services"></a>Servizi Windows gestiti  
 Questa opzione di hosting consiste nella registrazione del dominio dell'applicazione (AppDomain) che ospita un servizio WCF come servizio Windows gestito (precedentemente noto come servizio NT) in modo che la durata del processo del servizio è controllata da Gestione controllo servizi (SCM) per Servizi di Windows. Analogamente all'opzione di self-hosting, questo tipo di ambiente host richiede che venga scritto codice di hosting come parte dell'applicazione. Il servizio viene implementato come un servizio Windows e come un servizio WCF facendo in modo che derivi dal <xref:System.ServiceProcess.ServiceBase> classe, così come l'interfaccia del contratto di servizio da un WCF. <xref:System.ServiceModel.ServiceHost> viene quindi creato e aperto all'interno di un metodo <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> sottoposto a override e chiuso all'interno di un metodo <xref:System.ServiceProcess.ServiceBase.OnStop> sottoposto a override. È inoltre necessario implementare una classe del programma di installazione che eredita da <xref:System.Configuration.Install.Installer> per consentire l'installazione del programma come servizio Windows tramite Installutil.exe. Per altre informazioni, vedere [Procedura: Ospitare un servizio WCF in un servizio Windows gestito](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md). Nello scenario abilitato dall'opzione di hosting del servizio Windows gestito è quello di un servizio WCF con esecuzione prolungata ospitato all'esterno di IIS in un ambiente protetto che non è attivata da messaggi. La durata del servizio è controllata invece dal sistema operativo. Questa opzione di hosting è disponibile in tutte le versioni di Windows.  
  
#### <a name="internet-information-services-iis"></a>Internet Information Services (IIS)  
 L'opzione di hosting di IIS è integrata con [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] e utilizza le funzionalità offerte da queste tecnologie, ad esempio riciclo del processo, chiusura per inattività, monitoraggio dell'integrità del processo e attivazione basata su messaggi. Nei sistemi operativi [!INCLUDE[wxp](../../../includes/wxp-md.md)] e [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] , questa è la soluzione preferita per ospitare applicazioni del servizio Web che devono essere estremamente disponibili ed estremamente scalabili. IIS offre inoltre la gestione integrata che i clienti si aspettano da un prodotto server aziendale. Questa opzione di hosting richiede che IIS sia configurato correttamente, ma non richiede la scrittura di codice di hosting come parte dell'applicazione. Per altre informazioni su come configurare IIS che ospita un servizio WCF, vedere [come: Ospitare un servizio WCF in IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
 Si noti che i servizi ospitati da IIS possono utilizzare solo il trasporto HTTP. L'implementazione in IIS 5.1 ha introdotto alcune limitazioni in [!INCLUDE[wxp](../../../includes/wxp-md.md)]. L'attivazione basata su messaggi fornita per un servizio WCF da IIS 5.1 su [!INCLUDE[wxp](../../../includes/wxp-md.md)] blocca qualsiasi altro servizio WCF self-hosted nello stesso computer di utilizzare la porta 80 per comunicare. Servizi WCF possono essere eseguiti nello stesso AppDomain/applicazione/Pool di lavoro processo altre applicazisui quando ospitate da [!INCLUDE[iis601](../../../includes/iis601-md.md)] su [!INCLUDE[ws2003](../../../includes/ws2003-md.md)]. Tuttavia, poiché WCF e [!INCLUDE[iis601](../../../includes/iis601-md.md)] utilizzano entrambi lo stack HTTP in modalità kernel (http. sys), [!INCLUDE[iis601](../../../includes/iis601-md.md)] possono condividere la porta 80 con altri servizi WCF self-hosted in esecuzione nello stesso computer, a differenza di IIS 5.1.  
  
#### <a name="windows-process-activation-service-was"></a>Servizio di attivazione dei processi di Windows (WAS, Windows Process Activation Service)  
 Il servizio di attivazione dei processi di Windows (WAS, Windows Process Activation Service) è il nuovo meccanismo di attivazione del processo per [!INCLUDE[lserver](../../../includes/lserver-md.md)] disponibile anche su [!INCLUDE[wv](../../../includes/wv-md.md)]. Mantiene il modello di processo (pool di applicazioni e attivazione del processo basata su messaggi) e le funzionalità di hosting (ad esempio protezione rapida da errori, monitoraggio dell'integrità e riciclo) classiche di [!INCLUDE[iis601](../../../includes/iis601-md.md)] , ma rimuove la dipendenza da HTTP dall'architettura di attivazione. [!INCLUDE[iisver](../../../includes/iisver-md.md)] utilizza WAS per eseguire l'attivazione basata su messaggi su HTTP. Componenti aggiuntivi di WCF anche collegano a WAS per fornire l'attivazione basata su messaggi su altri protocolli supportati da WCF, ad esempio TCP, MSMQ e named pipe. Ciò consente alle applicazioni che utilizzano protocolli di comunicazione di utilizzare funzionalità IIS quali il riciclo del processo, la protezione rapida da errori e il sistema di configurazione comune che erano disponibili solo per applicazioni basate su HTTP.  
  
 Questa opzione di hosting richiede che WAS sia configurato correttamente, ma non richiede la scrittura di codice di hosting come parte dell'applicazione. Per altre informazioni su come configurare l'hosting di WAS, vedere [come: Ospitare un servizio WCF in WAS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).  
  
## <a name="choosing-a-hosting-environment"></a>Scelta di un ambiente host  
 Nella tabella seguente vengono riepilogati alcuni dei vantaggi e degli scenari principali associati a ogni opzione di hosting.  
  
|Ambiente host|Scenari comuni|Vantaggi e limitazioni principali|  
|-------------------------|----------------------|----------------------------------|  
|Applicazione gestita ("indipendente")|-Applicazioni console utilizzate durante lo sviluppo.<br />-Rich WinForm e [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] applicazioni client l'accesso ai servizi.|-Flessibile.<br />-Facile da distribuire.<br />-Non una soluzione aziendale per i servizi.|  
|Servizi Windows (precedentemente noti come servizi NT)|-Un servizio WCF con esecuzione prolungata ospitato all'esterno di IIS.|-Durata processo servizio controllata dal sistema operativo, non attivata da messaggi.<br />-Supportato da tutte le versioni di Windows.<br />-Ambiente sicuro.|  
|IIS 5.1, [!INCLUDE[iis601](../../../includes/iis601-md.md)]|-Esecuzione di un WCF service side-by-side con [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] contenuto su Internet utilizzando il protocollo HTTP.|-Riciclo del processo.<br />-Arresto inattivo.<br />-Elaborare il monitoraggio dell'integrità.<br />-Attivazione basata su messaggi.<br />-Solo HTTP.|  
|Servizio di attivazione dei processi di Windows (WAS, Windows Process Activation Service)|-Esecuzione di un servizio WCF senza installare IIS su Internet utilizzando vari protocolli di trasporto.|-IIS non è obbligatorio.<br />-Riciclo del processo.<br />-Arresto inattivo.<br />-Elaborare il monitoraggio dell'integrità.<br />-Attivazione basata su messaggi.<br />-È compatibile con HTTP, TCP, named pipe e MSMQ.|  
|IIS 7.0|-Esecuzione di un WCF service con [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] contenuto.<br />-Un servizio WCF in esecuzione su Internet utilizzando vari protocolli di trasporto.|-È stato vantaggi.<br />-Integrata con [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] e contenuto IIS.|  
  
 La scelta di un ambiente host dipende dalla versione di Windows sulla quale è distribuito, dal trasporto necessario per inviare i messaggi e dai requisiti per il tipo di riciclo del dominio dell'applicazione e del processo. Nella tabella seguente sono riepilogati i dati relativi a tali requisiti.  
  
|Ambiente host|Disponibilità della piattaforma|Trasporti supportati|Riciclo di processo e AppDomain|  
|-------------------------|---------------------------|--------------------------|-------------------------------------|  
|Applicazioni gestite ("indipendenti")|[!INCLUDE[wxp](../../../includes/wxp-md.md)], [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], [!INCLUDE[wv](../../../includes/wv-md.md)],<br /><br /> [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|No|  
|Servizi Windows (precedentemente noti come servizi NT)|[!INCLUDE[wxp](../../../includes/wxp-md.md)], [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], [!INCLUDE[wv](../../../includes/wv-md.md)],<br /><br /> [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|No|  
|IIS 5,1|[!INCLUDE[wxp](../../../includes/wxp-md.md)]|HTTP|Yes|  
|[!INCLUDE[iis601](../../../includes/iis601-md.md)]|[!INCLUDE[ws2003](../../../includes/ws2003-md.md)]|HTTP|Yes|  
|Servizio di attivazione dei processi di Windows (WAS, Windows Process Activation Service)|[!INCLUDE[wv](../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|Yes|  
  
 È importante notare che l'esecuzione di un servizio o di una qualsiasi estensione da un host non attendibile compromette la sicurezza. Si noti inoltre che quando si apre un <xref:System.ServiceModel.ServiceHost> in caso di utilizzo della rappresentazione, un'applicazione deve controllare che l'utente non si sia disconnesso, ad esempio memorizzando nella cache l'elemento <xref:System.Security.Principal.WindowsIdentity> dell'utente.  
  
## <a name="see-also"></a>Vedere anche

- [Requisiti di sistema](../../../docs/framework/wcf/wcf-system-requirements.md)
- [Ciclo di vita della programmazione di base](../../../docs/framework/wcf/basic-programming-lifecycle.md)
- [Implementazione dei contratti di servizio](../../../docs/framework/wcf/implementing-service-contracts.md)
- [Procedura: Ospitare un servizio WCF in IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)
- [Procedura: Ospitare un servizio WCF in WAS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md)
- [Procedura: Ospitare un servizio WCF in un servizio Windows gestito](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)
- [Procedura: Ospitare un servizio WCF in un'applicazione gestita](../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)

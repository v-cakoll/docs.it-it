---
title: Servizi host
description: Informazioni sulle opzioni di hosting per un servizio WCF. Un servizio deve essere ospitato in un ambiente di runtime che lo crea e ne controlla il contesto e la durata.
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF]
ms.assetid: 192be927-6be2-4fda-98f0-e513c4881acc
ms.openlocfilehash: 86ce392bb76b22e2b6a65fa1d005ed8e9589af15
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246383"
---
# <a name="hosting-services"></a>Servizi di hosting

Per diventare attivo, un servizio deve essere ospitato all'interno di un ambiente di runtime che lo crea e ne controlla il contesto e la durata. I servizi Windows Communication Foundation (WCF) sono progettati per essere eseguiti in qualsiasi processo di Windows che supporta codice gestito.

WCF fornisce un modello di programmazione unificato per la compilazione di applicazioni orientate ai servizi. Questo modello di programmazione rimane coerente ed è indipendente dall'ambiente di runtime nel quale viene distribuito il servizio. In pratica, ciò significa che il codice per i servizi interessati rimane praticamente invariato a prescindere dall'opzione di hosting.

Le opzioni di hosting vanno dall'esecuzione in una semplice applicazione console ad ambienti server come un servizio Windows in esecuzione in un processo di lavoro gestito da Internet Information Services (IIS) o dal servizio di attivazione dei processi di Windows (WAS). Gli sviluppatori scelgono l'ambiente host che soddisfa i requisiti di distribuzione del servizio. Questi requisiti potrebbero derivare dalla piattaforma sulla quale viene distribuita l'applicazione, il trasporto sul quale deve inviare e ricevere messaggi o sul tipo di riciclo del processo e gestione di altri processi richiesti per assicurare la disponibilità adeguata o su altri requisiti di gestione o affidabilità. Nella prossima sezione vengono fornite informazioni e istruzioni sulle opzioni di hosting.

## <a name="hosting-options"></a>Opzioni di hosting

### <a name="self-host-in-a-managed-application"></a>Self-host in un'applicazione gestita
 I servizi WCF possono essere ospitati in qualsiasi applicazione gestita. Questa è l'opzione più flessibile perché richiede la distribuzione di un'infrastruttura minima. Incorporare il codice per il servizio all'interno del codice dell'applicazione gestita, quindi creare e aprire un'istanza di <xref:System.ServiceModel.ServiceHost> per rendere il servizio disponibile. Per altre informazioni, vedere [procedura: ospitare un servizio WCF in un'applicazione gestita](how-to-host-a-wcf-service-in-a-managed-application.md).

 Questa opzione consente due scenari comuni: i servizi WCF in esecuzione all'interno di applicazioni console e applicazioni rich client come quelle basate su Windows Presentation Foundation (WPF) o Windows Forms (WinForms). L'hosting di un servizio WCF all'interno di un'applicazione console è in genere utile durante la fase di sviluppo dell'applicazione. Agevola infatti il debug, l'ottenimento di informazioni di traccia per scoprire cosa accadde all'interno dell'applicazione e lo spostamento copiandole in nuove posizioni. Questa opzione di hosting semplifica inoltre la comunicazione tra le applicazioni rich client, ad esempio le applicazioni WPF e Windows Form con il mondo esterno. Ad esempio, un client di collaborazione peer-to-peer che utilizza WPF per la relativa interfaccia utente e ospita anche un servizio WCF che consente ad altri client di connettersi ad esso e condividere le informazioni.

### <a name="managed-windows-services"></a>Servizi Windows gestiti

Questa opzione di hosting consiste nella registrazione del dominio applicazione (AppDomain) che ospita un servizio WCF come servizio Windows gestito (precedentemente noto come servizio NT), in modo che la durata del processo del servizio sia controllata da Gestione controllo servizi (SCM) per i servizi Windows. Analogamente all'opzione di self-hosting, questo tipo di ambiente host richiede che venga scritto codice di hosting come parte dell'applicazione. Il servizio viene implementato sia come servizio Windows che come servizio WCF, facendo in modo che erediti dalla <xref:System.ServiceProcess.ServiceBase> classe, oltre che da un'interfaccia del contratto di servizio WCF. <xref:System.ServiceModel.ServiceHost> viene quindi creato e aperto all'interno di un metodo <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> sottoposto a override e chiuso all'interno di un metodo <xref:System.ServiceProcess.ServiceBase.OnStop> sottoposto a override. È inoltre necessario implementare una classe del programma di installazione che eredita da <xref:System.Configuration.Install.Installer> per consentire l'installazione del programma come servizio Windows tramite Installutil.exe. Per ulteriori informazioni, vedere [procedura: ospitare un servizio WCF in un servizio Windows gestito](./feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md). Lo scenario abilitato dall'opzione di hosting del servizio Windows gestito è quello di un servizio WCF con esecuzione prolungata ospitato all'esterno di IIS in un ambiente protetto non attivato dal messaggio. La durata del servizio è controllata invece dal sistema operativo. Questa opzione di hosting è disponibile in tutte le versioni di Windows.

### <a name="internet-information-services-iis"></a>Internet Information Services (IIS)

L'opzione di hosting di IIS è integrata con ASP.NET e utilizza le funzionalità offerte da queste tecnologie, ad esempio il riciclo dei processi, l'arresto inattivo, il monitoraggio dell'integrità dei processi e l'attivazione basata su messaggi. Nei sistemi operativi Windows XP e Windows Server 2003 questa è la soluzione preferita per l'hosting di applicazioni di servizi Web che devono essere a disponibilità elevata e altamente scalabili. IIS offre inoltre la gestione integrata che i clienti si aspettano da un prodotto server aziendale. Questa opzione di hosting richiede che IIS sia configurato correttamente, ma non richiede la scrittura di codice di hosting come parte dell'applicazione. Per ulteriori informazioni su come configurare l'hosting di IIS per un servizio WCF, vedere [procedura: ospitare un servizio WCF in IIS](./feature-details/how-to-host-a-wcf-service-in-iis.md).

 I servizi ospitati in IIS possono utilizzare solo il trasporto HTTP. La relativa implementazione in IIS 5,1 ha introdotto alcune limitazioni in Windows XP. L'attivazione basata su messaggi fornita per un servizio WCF da IIS 5,1 in Windows XP impedisce a tutti gli altri servizi WCF indipendenti nello stesso computer di utilizzare la porta 80 per la comunicazione. I servizi WCF possono essere eseguiti nello stesso AppDomain/pool di applicazioni/processo di lavoro di altre applicazioni quando sono ospitati da IIS 6,0 in Windows Server 2003. Tuttavia, poiché WCF e IIS 6,0 utilizzano entrambi lo stack HTTP in modalità kernel (HTTP.sys), IIS 6,0 può condividere la porta 80 con altri servizi WCF indipendenti in esecuzione nello stesso computer, a differenza di IIS 5,1.

### <a name="windows-process-activation-service-was"></a>Servizio di attivazione dei processi di Windows (WAS, Windows Process Activation Service)

Il servizio Attivazione processo Windows (WAS) è il nuovo meccanismo di attivazione del processo per Windows Server 2008, disponibile anche in Windows Vista. Mantiene il modello di processo IIS 6,0 (pool di applicazioni e attivazione del processo basata su messaggi) e le funzionalità di hosting (ad esempio protezione rapida da errori, monitoraggio dell'integrità e riciclo), ma rimuove la dipendenza da HTTP dall'architettura di attivazione. IIS 7,0 utilizza WAS per eseguire l'attivazione basata su messaggi su HTTP. Inoltre, i componenti aggiuntivi di WCF si collegano a WAS per fornire l'attivazione basata su messaggi sugli altri protocolli supportati da WCF, ad esempio TCP, MSMQ e named pipe. Ciò consente alle applicazioni che utilizzano protocolli di comunicazione di utilizzare funzionalità IIS quali il riciclo del processo, la protezione rapida da errori e il sistema di configurazione comune che erano disponibili solo per applicazioni basate su HTTP.

 Questa opzione di hosting richiede che WAS sia configurato correttamente, ma non richiede la scrittura di codice di hosting come parte dell'applicazione. Per ulteriori informazioni su come configurare l'hosting di WAS, vedere [procedura: ospitare un servizio WCF in was](./feature-details/how-to-host-a-wcf-service-in-was.md).

## <a name="choose-a-hosting-environment"></a>Scegliere un ambiente host
 Nella tabella seguente vengono riepilogati alcuni dei vantaggi e degli scenari principali associati a ogni opzione di hosting.

|Ambiente host|Scenari comuni|Vantaggi e limitazioni principali|
|-------------------------|----------------------|----------------------------------|
|Applicazione gestita ("indipendente")|-Applicazioni console utilizzate durante lo sviluppo.<br />-Applicazioni client WinForm e WPF complete che accedono ai servizi.|Flessibile.<br />-Facile da distribuire.<br />-Non è una soluzione aziendale per i servizi.|
|Servizi Windows (precedentemente noti come servizi NT)|-Servizio WCF con esecuzione prolungata ospitato all'esterno di IIS.|-Durata del processo del servizio controllata dal sistema operativo, non attivata dal messaggio.<br />-Supportato da tutte le versioni di Windows.<br />-Ambiente protetto.|
|IIS 5,1, IIS 6,0|-Esecuzione di un servizio WCF affiancato con contenuto ASP.NET su Internet tramite il protocollo HTTP.|-Riciclo del processo.<br />-Arresto inattivo.<br />-Monitoraggio dell'integrità del processo.<br />-Attivazione basata su messaggi.<br />-Solo HTTP.|
|Servizio di attivazione dei processi di Windows (WAS, Windows Process Activation Service)|-Esecuzione di un servizio WCF senza installare IIS in Internet utilizzando vari protocolli di trasporto.|-IIS non è obbligatorio.<br />-Riciclo del processo.<br />-Arresto inattivo.<br />-Monitoraggio dell'integrità del processo.<br />-Attivazione basata su messaggi.<br />-Funziona con HTTP, TCP, named pipe e MSMQ.|
|IIS 7.0|-Esecuzione di un servizio WCF con contenuto ASP.NET.<br />-Esecuzione di un servizio WCF in Internet utilizzando vari protocolli di trasporto.|-Vantaggi.<br />-Integrato con ASP.NET e il contenuto IIS.|

 La scelta di un ambiente host dipende dalla versione di Windows sulla quale è distribuito, dal trasporto necessario per inviare i messaggi e dai requisiti per il tipo di riciclo del dominio dell'applicazione e del processo. Nella tabella seguente sono riepilogati i dati relativi a tali requisiti.

|Ambiente host|Disponibilità della piattaforma|Trasporti supportati|Riciclo di processo e AppDomain|
|-------------------------|---------------------------|--------------------------|-------------------------------------|
|Applicazioni gestite ("indipendenti")|Windows XP, Windows Server 2003, Windows Vista,<br /><br /> Windows Server 2008|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|No|
|Servizi Windows (precedentemente noti come servizi NT)|Windows XP, Windows Server 2003, Windows Vista,<br /><br /> Windows Server 2008|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|No|
|IIS 5,1|Windows XP|HTTP|Sì|
|IIS 6.0|Windows Server 2003|HTTP|Sì|
|Servizio di attivazione dei processi di Windows (WAS, Windows Process Activation Service)|Windows Vista, Windows Server 2008|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|Sì|

 È importante notare che l'esecuzione di un servizio o di una qualsiasi estensione da un host non attendibile compromette la sicurezza. Inoltre, quando si apre un oggetto <xref:System.ServiceModel.ServiceHost> in una rappresentazione, un'applicazione deve assicurarsi che l'utente non sia disconnesso, ad esempio memorizzando nella cache l'oggetto <xref:System.Security.Principal.WindowsIdentity> dell'utente.

## <a name="see-also"></a>Vedere anche

- [Ciclo di vita della programmazione di base](basic-programming-lifecycle.md)
- [Implementazione dei contratti di servizio](implementing-service-contracts.md)
- [Procedura: ospitare un servizio WCF in IIS](./feature-details/how-to-host-a-wcf-service-in-iis.md)
- [Procedura: ospitare un servizio WCF in WAS](./feature-details/how-to-host-a-wcf-service-in-was.md)
- [Procedura: ospitare un servizio WCF in un servizio Windows gestito](./feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)
- [Procedura: ospitare un servizio WCF in un'applicazione gestita](how-to-host-a-wcf-service-in-a-managed-application.md)

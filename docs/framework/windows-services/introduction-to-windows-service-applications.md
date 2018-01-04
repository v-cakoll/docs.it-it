---
title: Introduzione alle applicazioni di servizio Windows
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ServiceController
helpviewer_keywords:
- Windows Service applications, deploying
- OnStop method
- OnPause method
- services, about services
- Service class, Windows Service applications
- framework services, creating services
- ServiceController components, about Windows services
- Win32OwnProcess service type
- services, lifetime
- OnContinue method
- Windows Service applications, about Windows Service applications
- services, states
- service states
- WaitForStatus method
- Win32ShareProcess service type
- Windows Service applications, lifetime
ms.assetid: 1b1b5e67-3ff3-40c0-8154-322cfd6ef0ae
caps.latest.revision: "17"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 613107a13820ad71b854dcba93f21c41f2a5fa5f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="introduction-to-windows-service-applications"></a>Introduzione alle applicazioni di servizio Windows
Servizi di Microsoft Windows, precedentemente noti come servizi NT, consentono di creare applicazioni eseguibili con esecuzione prolungata che eseguono le proprie sessioni di Windows. Questi servizi possono essere avviati automaticamente all'avvio del computer, può essere sospeso e riavviato e non visualizzare alcuna interfaccia utente. Queste funzionalità rendono i servizi ideale per l'utilizzo in un server o ogni volta che necessaria la funzionalità di esecuzione prolungata che non interferisca con altri utenti che lavorano nello stesso computer. È anche possibile eseguire servizi nel contesto di sicurezza di un account utente specifico che è diverso da parte dell'utente connesso o l'account computer predefinito. Per ulteriori informazioni sui servizi e le sessioni di Windows, vedere la documentazione di Windows SDK.  
  
 È possibile creare facilmente servizi creando un'applicazione che viene installata come un servizio. Si supponga, ad esempio monitorare i dati dei contatori delle prestazioni e reagire a valori di soglia. È possibile scrivere un'applicazione di servizio Windows che ascolta i dati del contatore delle prestazioni, distribuire l'applicazione e iniziare la raccolta e analisi dei dati.  
  
 Il servizio come progetto di Microsoft Visual Studio viene creato, definendo il codice interno che controlla quali comandi possono essere inviati al servizio e quali operazioni devono essere eseguite quando vengono ricevuti i comandi. I comandi che possono essere inviati a un servizio includono l'avvio, sospensione, ripresa e l'arresto del servizio; è anche possibile eseguire i comandi personalizzati.  
  
 Dopo aver creato e compilare l'applicazione, è possibile installarlo eseguendo l'utilità della riga di comando di InstallUtil.exe e passare il percorso del file eseguibile del servizio. È quindi possibile utilizzare il **Gestione controllo servizi** per avviare, arrestare, sospendere, riprendere e configurare il servizio. È inoltre possibile eseguire molte di queste attività nel **servizi** nodo **Esplora Server** o utilizzando il <xref:System.ServiceProcess.ServiceController> classe.  
  
## <a name="service-applications-vs-other-visual-studio-applications"></a>Applicazioni di servizio e. Altre applicazioni di Visual Studio  
 Funzione di applicazioni di servizio in modo diverso da molti altri tipi di progetto in diversi modi:  
  
-   Il file eseguibile compilato che crea un progetto di applicazione di servizio deve installato nel server prima che il progetto possa funzionare in modo significativo. È possibile eseguire il debug o eseguire un'applicazione di servizio premendo F5 o F11. è possibile eseguire immediatamente un servizio o un passaggio al relativo codice. In alternativa, è necessario installare e avviare il servizio e quindi collegare un debugger al processo del servizio. Per ulteriori informazioni, vedere [procedura: eseguire il Debug di applicazioni di servizio Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md).  
  
-   A differenza di alcuni tipi di progetti, è necessario creare componenti di installazione per le applicazioni di servizio. I componenti di installazione di installare e registrare il servizio sul server e creare una voce per il servizio con Windows **Gestione controllo servizi**. Per ulteriori informazioni, vedere [procedura: aggiungere programmi di installazione per l'applicazione di servizio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
-   Il `Main` metodo per l'applicazione di servizio deve eseguire il comando di esecuzione per i servizi del progetto contiene. Il `Run` metodo carica i servizi nel **Gestione controllo servizi** sul server appropriato. Se si utilizza il **servizi Windows** modello di progetto, questo metodo viene creato automaticamente. Si noti che il caricamento di un servizio non equivale all'avvio del servizio. "Servizio Lifetime" riportata di seguito per ulteriori informazioni, vedere.  
  
-   Applicazioni di servizio Windows eseguite in una stazione diversa finestra interattivo dell'utente connesso. Una stazione di finestra è un oggetto sicura che contiene un blocco per Appunti, un set di atomi globali e un gruppo di oggetti desktop. Poiché la stazione del servizio Windows non è interattivo, finestre di dialogo generata da un'applicazione di servizio non saranno visibili e può causare il blocco del programma di Windows. Analogamente, i messaggi di errore devono essere registrati nel registro eventi di Windows anziché generati nell'interfaccia utente.  
  
     Le classi del servizio Windows supportate da .NET Framework non supportano l'interazione con le stazioni interattive, ovvero l'utente connesso. Inoltre, .NET Framework non include classi che rappresentano le stazioni e desktop. Se il servizio Windows deve interagire con altre stazioni, è necessario accedere all'API Windows non gestito. Per ulteriori informazioni, vedere la documentazione di Windows SDK.  
  
     L'interazione delle finestre del servizio con l'utente o altre stazioni deve essere progettata attentamente per includere pari al numero di tali scenari che nessun utente connesso o l'utente con un set di oggetti desktop non previsto. In alcuni casi, potrebbe essere più opportuno scrivere un'applicazione Windows che viene eseguito sotto il controllo dell'utente.  
  
-   Applicazioni di servizio Windows eseguito nel proprio contesto di sicurezza e vengono avviate prima che l'utente accede al computer Windows in cui sono installati. È necessario pianificare attentamente quali account utente per eseguire il servizio all'interno; un servizio in esecuzione con l'account di sistema dispone di altre autorizzazioni e i privilegi rispetto a un account utente.  
  
## <a name="service-lifetime"></a>Durata del servizio  
 Un servizio passa attraverso diversi stati interni della durata. In primo luogo, il servizio è installato nel sistema in cui verrà eseguito. Questo processo esegue i programmi di installazione per il progetto di servizio e carica il servizio nel **Gestione controllo servizi** per tale computer. Il **Gestione controllo servizi** è l'utilità centrale fornita da Windows per amministrare i servizi.  
  
 Il servizio è stato caricato, deve essere avviato. Avvio del servizio consente per consentirne il funzionamento. È possibile avviare un servizio di **Gestione controllo servizi**, da **Esplora Server**, o da codice chiamando il <xref:System.ServiceProcess.ServiceController.Start%2A> (metodo). Il <xref:System.ServiceProcess.ServiceController.Start%2A> metodo passa l'elaborazione dell'applicazione <xref:System.ServiceProcess.ServiceBase.OnStart%2A> metodo ed elabora qualsiasi codice vi è stato definito.  
  
 Per un periodo illimitato fino a quando viene arrestato o sospeso o arresto del computer, in questo stato può esistere un servizio in esecuzione. Un servizio può rimanere in uno dei tre stati di base: <xref:System.ServiceProcess.ServiceControllerStatus.Running>, <xref:System.ServiceProcess.ServiceControllerStatus.Paused>, o <xref:System.ServiceProcess.ServiceControllerStatus.Stopped>. Il servizio può inoltre segnalare lo stato di un comando in sospeso: <xref:System.ServiceProcess.ServiceControllerStatus.ContinuePending>, <xref:System.ServiceProcess.ServiceControllerStatus.PausePending>, <xref:System.ServiceProcess.ServiceControllerStatus.StartPending>, o <xref:System.ServiceProcess.ServiceControllerStatus.StopPending>. Questi stati indicano che un comando è stato eseguito, ad esempio un comando per sospendere un servizio in esecuzione, ma non effettuato ancora. È possibile eseguire una query di <xref:System.ServiceProcess.ServiceController.Status%2A> per determinare lo stato è un servizio oppure utilizzare il <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A> per eseguire un'azione quando uno di questi stati si verifica.  
  
 È possibile sospendere, arrestare o riprendere un servizio dal **Gestione controllo servizi**, da **Esplora Server**, oppure chiamando i metodi nel codice. Ognuna di queste azioni può chiamare una routine associata nel servizio (<xref:System.ServiceProcess.ServiceBase.OnStop%2A>, <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, o <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>), in cui è possibile definire un'ulteriore elaborazione da eseguire quando il servizio di modifica stato.  
  
## <a name="types-of-services"></a>Tipi di servizi  
 Esistono due tipi di servizi che è possibile creare in Visual Studio con .NET Framework. Il tipo viene assegnato ai servizi che sono l'unico servizio in un processo <xref:System.ServiceProcess.ServiceType.Win32OwnProcess>. Il tipo viene assegnato ai servizi che condividono un processo con un altro servizio <xref:System.ServiceProcess.ServiceType.Win32ShareProcess>. È possibile recuperare il tipo di servizio eseguendo una query di <xref:System.ServiceProcess.ServiceController.ServiceType%2A> proprietà.  
  
 Se si esegue una query servizi esistenti che non sono stati creati in Visual Studio, è possibile riscontrare altri tipi di servizio. Per ulteriori informazioni, vedere il <xref:System.ServiceProcess.ServiceType>.  
  
## <a name="services-and-the-servicecontroller-component"></a>Servizi e il componente ServiceController  
 Il <xref:System.ServiceProcess.ServiceController> componente viene utilizzato per connettersi a un servizio installato e per modificarne lo stato; utilizzando un <xref:System.ServiceProcess.ServiceController> componente, è possibile avviare e arrestare un servizio, sospendere e riprenderne l'esecuzione e inviare comandi personalizzati a un servizio. Tuttavia, non è necessario utilizzare un <xref:System.ServiceProcess.ServiceController> componente quando si crea un'applicazione di servizio. In effetti, nella maggior parte dei casi il <xref:System.ServiceProcess.ServiceController> componente deve essere presente in un'applicazione distinta dall'applicazione del servizio Windows che definisce il servizio.  
  
 Per altre informazioni, vedere <xref:System.ServiceProcess.ServiceController>.  
  
## <a name="requirements"></a>Requisiti  
  
-   I servizi devono essere creati un **servizio Windows** progetto di applicazione o un altro progetto supportato da .NET Framework che crea un file .exe quando compilato ed eredita il <xref:System.ServiceProcess.ServiceBase> classe.  
  
-   I progetti contenenti i servizi Windows devono disporre dei componenti di installazione per il progetto e i relativi servizi. Questo può essere effettuato facilmente tramite il **proprietà** finestra. Per ulteriori informazioni, vedere [procedura: aggiungere programmi di installazione per l'applicazione di servizio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Applicazioni di servizi Windows](../../../docs/framework/windows-services/index.md)  
 [Architettura di programmazione delle applicazioni di servizio](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 [Procedura: creare servizi Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [Procedura: installare e disinstallare servizi](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [Procedura: avviare servizi](../../../docs/framework/windows-services/how-to-start-services.md)  
 [Procedura: eseguire il debug di applicazioni di servizio per Windows](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [Procedura dettagliata: creazione di un'applicazione di servizio Windows in Progettazione componenti](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 [Procedura: aggiungere programmi di installazione all'applicazione di servizio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)

---
title: Introduzione alle applicazioni di servizio Windows
description: Leggi un'introduzione alle applicazioni di servizio Windows. I servizi consentono di creare applicazioni eseguibili con esecuzione prolungata che vengono eseguite nelle proprie sessioni di Windows.
ms.date: 03/30/2017
f1_keywords:
- ServiceController
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
author: ghogen
ms.openlocfilehash: 13bd1f42776ac76a43a83667465ac0ca277e3452
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925670"
---
# <a name="introduction-to-windows-service-applications"></a>Introduzione alle applicazioni di servizio Windows
I servizi Microsoft Windows, noti in precedenza come servizi NT, consentono di creare applicazioni eseguibili di lunga durata in esecuzione in sessioni Windows dedicate. Questi servizi possono essere avviati automaticamente all'avvio del computer, possono essere sospesi e riavviati e non visualizzano alcuna interfaccia utente. Queste funzionalità rendono i servizi ideali per l'uso in un server o per fornire funzionalità di lunga durata che non interferiscono con gli altri utenti che lavorano sullo stesso computer. È anche possibile eseguire i servizi nel contesto di sicurezza di un account utente specifico diverso dall'utente connesso o dall'account computer predefinito. Per altre informazioni sui servizi e le sessioni di Windows, vedere la documentazione di Windows SDK.  
  
 È possibile creare facilmente servizi mediante la creazione di un'applicazione installata come servizio. Si supponga, ad esempio, di voler monitorare i dati dei contatori delle prestazioni e reagire ai valori di soglia. È possibile scrivere un'applicazione Servizio Windows che rimane in ascolto dei dati del contatore delle prestazioni, distribuisce l'applicazione e iniziare la raccolta e l'analisi dei dati.  
  
 Il servizio viene creato come progetto di Microsoft Visual Studio definendo il codice al suo interno che controlla i comandi che possono essere inviati al servizio e le azioni che devono essere eseguite alla ricezione di tali comandi. I comandi che possono essere inviati a un servizio includono avvio, sospensione, ripresa e arresto del servizio. Si possono anche creare comandi personalizzati.  
  
 Dopo aver creato e compilato l'applicazione, è possibile installarla eseguendo l'utilità della riga di comando InstallUtil.exe e passando il percorso al file eseguibile del servizio. È quindi possibile usare **Gestione controllo servizi** per avviare, arrestare, sospendere, riprendere e configurare il servizio. Si possono anche eseguire molte delle stesse attività nel nodo **Servizi** in **Esplora server** o tramite la classe <xref:System.ServiceProcess.ServiceController>.  
  
## <a name="service-applications-vs-other-visual-studio-applications"></a>Applicazioni di servizio rispetto ad altre applicazioni di Visual Studio  
 Le applicazioni di servizio funzionano in modo diverso rispetto a molti altri tipi di progetto per vari aspetti:  
  
- Il file eseguibile compilato creato da un progetto di applicazione di servizio deve essere installato nel server prima che il progetto possa funzionare in modo significativo. Non è possibile eseguire il debug o eseguire un'applicazione di servizio premendo F5 o F11. Non è possibile eseguire immediatamente un servizio o eseguirne il codice istruzione per istruzione. È invece necessario installare e avviare il servizio, quindi collegare un debugger al processo del servizio. Per altre informazioni, vedere [Procedura: Eseguire il debug di applicazioni di servizio per Windows](how-to-debug-windows-service-applications.md).  
  
- A differenza di alcuni tipi di progetti, è necessario creare i componenti di installazione per le applicazioni di servizio. I componenti di installazione installano e registrano il servizio nel server e creano una voce per il servizio con **Gestione controllo servizi** di Windows. Per altre informazioni, vedere [Procedura: Aggiungere programmi di installazione all'applicazione di servizio](how-to-add-installers-to-your-service-application.md).  
  
- Il metodo `Main` per l'applicazione di servizio deve eseguire il comando Esegui per i servizi contenuti nel progetto. Il metodo `Run` carica i servizi in **Gestione controllo servizi** nel server appropriato. Se si usa il modello di progetto **Servizio Windows**, questo metodo viene creato automaticamente. Si noti che il caricamento di un servizio non equivale all'avvio del servizio. Vedere "Ciclo di vita del servizio" di seguito per altre informazioni.  
  
- Le applicazioni di servizio Windows vengono eseguite in un oggetto finestra diverso rispetto all'oggetto interattivo dell'utente connesso. Un oggetto finestra è un oggetto sicuro che contiene gli Appunti, un set di atom globali e un gruppo di oggetti desktop. Dato che l'oggetto del servizio Windows non è interattivo, le finestre di dialogo generate da un'applicazione di servizio Windows non saranno visibili e potrebbero causare il blocco del programma. Analogamente, i messaggi di errore devono essere registrati nel registro eventi di Windows anziché essere generati nell'interfaccia utente.  
  
     Le classi del servizio Windows supportate da .NET Framework non supportano l'interazione con gli oggetti interattivi, ovvero l'utente connesso. Inoltre, .NET Framework non include classi che rappresentano oggetti e desktop. Se il servizio Windows deve interagire con altri oggetti, sarà necessario accedere all'API di Windows non gestita. Per altre informazioni, vedere la documentazione di Windows SDK.  
  
     L'interazione del servizio Windows con l'utente o altri oggetti deve essere progettata attentamente per includere scenari come l'assenza di un utente connesso o un utente con un set di oggetti desktop imprevisto. In alcuni casi, potrebbe essere più opportuno scrivere un'applicazione Windows eseguita sotto il controllo dell'utente.  
  
- Le applicazioni di servizio Windows vengono eseguite all'interno di un contesto di sicurezza proprio e avviate prima che l'utente acceda al computer Windows in cui sono installate. È necessario pianificare attentamente l'account utente nell'ambito del quale eseguire il servizio. Un servizio in esecuzione con l'account di sistema ha più autorizzazioni e privilegi rispetto al contesto di un account utente.  
  
## <a name="service-lifetime"></a>Ciclo di vita del servizio  
 Un servizio passa attraverso diversi stati interni durante il ciclo di vita. In primo luogo, il servizio viene installato nel sistema in cui verrà eseguito. Questo processo esegue i programmi di installazione per il progetto di servizio e carica il servizio in **Gestione controllo servizi** per tale computer. **Gestione controllo servizi** è l'utilità centrale fornita da Windows per amministrare i servizi.  
  
 Dopo il caricamento, il servizio deve essere avviato. L'avvio del servizio ne consente il funzionamento. È possibile avviare un servizio da **Gestione controllo servizi**, da **Esplora server** o dal codice chiamando il metodo <xref:System.ServiceProcess.ServiceController.Start%2A>. Il metodo <xref:System.ServiceProcess.ServiceController.Start%2A> passa l'elaborazione al metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> dell'applicazione ed elabora qualsiasi codice definito in tale metodo.  
  
 Un servizio in esecuzione può rimanere in questo stato per un periodo illimitato fino a quando non viene arrestato o sospeso o fino alla chiusura del computer. Un servizio può esistere in uno di tre stati di base: <xref:System.ServiceProcess.ServiceControllerStatus.Running>, <xref:System.ServiceProcess.ServiceControllerStatus.Paused> o <xref:System.ServiceProcess.ServiceControllerStatus.Stopped>. Il servizio può anche segnalare lo stato di un comando in sospeso: <xref:System.ServiceProcess.ServiceControllerStatus.ContinuePending>, <xref:System.ServiceProcess.ServiceControllerStatus.PausePending>, <xref:System.ServiceProcess.ServiceControllerStatus.StartPending> o <xref:System.ServiceProcess.ServiceControllerStatus.StopPending>. Questi stati indicano che è stato inviato un comando, ad esempio un comando per sospendere un servizio in esecuzione, ma che il comando non è ancora stato eseguito. È possibile eseguire una query su <xref:System.ServiceProcess.ServiceController.Status%2A> per determinare lo stato di un servizio oppure usare <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A> per eseguire un'azione quando si verifica uno di questi stati.  
  
 È possibile sospendere, arrestare o riprendere un servizio da **Gestione controllo servizi**, da **Esplora server** oppure chiamando metodi nel codice. Ognuna di queste azioni può chiamare una routine associata nel servizio (<xref:System.ServiceProcess.ServiceBase.OnStop%2A>, <xref:System.ServiceProcess.ServiceBase.OnPause%2A> o <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>), in cui è possibile definire un'ulteriore elaborazione da eseguire quando il servizio cambia stato.  
  
## <a name="types-of-services"></a>Tipi di servizi  
 Esistono due tipi di servizi che è possibile creare in Visual Studio con .NET Framework. Ai servizi che sono l'unico servizio in un processo viene assegnato il tipo <xref:System.ServiceProcess.ServiceType.Win32OwnProcess>. Ai servizi che condividono un processo con un altro servizio viene assegnato il tipo <xref:System.ServiceProcess.ServiceType.Win32ShareProcess>. È possibile recuperare il tipo di servizio eseguendo una query sulla proprietà <xref:System.ServiceProcess.ServiceController.ServiceType%2A>.  
  
 Se si eseguono query su servizi esistenti che non sono stati creati in Visual Studio, è possibile riscontrare altri tipi di servizio. Per altre informazioni in merito, vedere <xref:System.ServiceProcess.ServiceType>.  
  
## <a name="services-and-the-servicecontroller-component"></a>Servizi e componente ServiceController  
 Il componente <xref:System.ServiceProcess.ServiceController> viene usato per connettersi a un servizio installato e per modificarne lo stato. Con un componente <xref:System.ServiceProcess.ServiceController> è possibile avviare e arrestare un servizio, sospendere e riprenderne l'esecuzione e inviare comandi personalizzati a un servizio. Tuttavia, non è necessario usare un componente <xref:System.ServiceProcess.ServiceController> quando si crea un'applicazione di servizio. In effetti, nella maggior parte dei casi il componente <xref:System.ServiceProcess.ServiceController> deve esistere in un'applicazione distinta dall'applicazione di servizio Windows che definisce il servizio.  
  
 Per altre informazioni, vedere <xref:System.ServiceProcess.ServiceController>.  
  
## <a name="requirements"></a>Requisiti  
  
- I servizi devono essere creati in un progetto di applicazione **Servizio Windows** o in un altro progetto abilitato per .NET Framework, che viene compilato come file EXE ed eredita dalla classe <xref:System.ServiceProcess.ServiceBase>.  
  
- I progetti contenenti servizi Windows devono avere componenti di installazione per il progetto e i relativi servizi. È possibile ottenere facilmente questo risultato dalla finestra **Proprietà**. Per altre informazioni, vedere [Procedura: Aggiungere programmi di installazione all'applicazione di servizio](how-to-add-installers-to-your-service-application.md).  
  
## <a name="see-also"></a>Vedere anche

- [Applicazioni di servizio di Windows](index.md)
- [Architettura di programmazione delle applicazioni di servizio](service-application-programming-architecture.md)
- [Procedura: Creare servizi Windows](how-to-create-windows-services.md)
- [Procedura: installare e disinstallare servizi](how-to-install-and-uninstall-services.md)
- [Procedura: Avviare servizi](how-to-start-services.md)
- [Procedura: Eseguire il debug di applicazioni di servizio di Windows](how-to-debug-windows-service-applications.md)
- [Procedura dettagliata: creazione di un'applicazione di servizio Windows in Progettazione componenti](walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
- [Procedura: Aggiungere programmi di installazione all'applicazione di servizio](how-to-add-installers-to-your-service-application.md)

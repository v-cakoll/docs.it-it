---
title: Modelli di Visual Studio WCF
ms.date: 03/30/2017
ms.assetid: 6a608575-3535-4190-89da-911e24c8374f
ms.openlocfilehash: ec73036921632bc855e79239f1fc578587de7ca3
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802355"
---
# <a name="wcf-visual-studio-templates"></a>Modelli di Visual Studio WCF
I modelli di Visual Studio Windows Communication Foundation (WCF) sono modelli di progetto e di elemento predefiniti che è possibile usare in Visual Studio per compilare rapidamente i servizi WCF e le applicazioni circostanti.  
  
## <a name="using-the-wcf-templates"></a>Utilizzo dei modelli di WCF  
 I modelli di Visual Studio WCF forniscono una struttura di classe di base per lo sviluppo del servizio. In particolare, questi modelli forniscono le definizioni di base per il contratto di servizio, contratto dati, implementazione del servizio e configurazione. È possibile utilizzare questi modelli per creare un semplice servizio con interazione di codice minima e come blocco predefinito per servizi più avanzati.  
  
### <a name="wcf-service-library-project-template"></a>Modello di progetto della libreria di servizi WCF  
 Il modello di progetto libreria di servizi WCF è disponibile nella finestra di dialogo nuovo progetto in **Visual C#\WCF** e **Visual Basic\WCF**.  
  
 Quando si crea un nuovo progetto utilizzando il modello di **servizio WCF** , il nuovo progetto include automaticamente i tre file seguenti:  
  
- File di contratto del servizio (IService1.cs o IService1.vb). Il file del contratto di servizio è un'interfaccia con attributi del servizio WCF applicati. Questo file fornisce una definizione di un semplice servizio per indicare come definire i servizi e include operazioni basate su parametri e un semplice esempio di contratto dati. Si tratta del file predefinito visualizzato nell'editor del codice dopo la creazione di un progetto di servizio WCF.  
  
- File di implementazione del servizio (Service1.cs o Service1.vb). Il file di implementazione del servizio implementa il contratto definito nel file del contratto di servizio.  
  
- File di configurazione dell'applicazione (App.config). Il file di configurazione fornisce gli elementi di base di un modello di servizio WCF con un'associazione HTTP protetta. Include anche un endpoint per il servizio e abilita scambio di metadati.  
  
> [!NOTE]
> Visual Studio è configurato per riconoscere il file app. config come file di configurazione per il progetto quando viene eseguito tramite l' [host del servizio WCF (WcfSvcHost. exe)](wcf-service-host-wcfsvchost-exe.md), che è la configurazione predefinita. Se la libreria di servizi viene inserita in un eseguibile, è necessario spostare il codice di configurazione nel file di configurazione dell'eseguibile, in quanto i file di configurazione per le DLL non sono validi.  
  
### <a name="wcf-service-application-template"></a>Modello Applicazione di servizio WCF  
 Il modello applicazione di servizio WCF è disponibile nella finestra di dialogo nuovo progetto **in C#Visual \WCF** e **Visual Basic\WCF**.  
  
 Quando si crea un nuovo progetto utilizzando il modello di **servizio applicazione Web WCF** , il progetto include i quattro file seguenti:  
  
- File host del servizio (service1.svc).  
  
- File di contratto del servizio (IService1.cs o IService1.vb).  
  
- File di implementazione del servizio (Service1.svc.cs o Service1.svc.vb).  
  
- File di configurazione Web (Web.config).  
  
 Il modello crea automaticamente un sito Web (da distribuire in una directory virtuale) e funge da host di un servizio.  
  
### <a name="wcf-web-site-template"></a>Modello sito Web del servizio WCF  
 Il modello di sito Web WCF è disponibile nella finestra di dialogo nuovo progetto **in C#Visual \Web Site\WCF Service** e **Visual Basic\Web Site\WCF Service**. In questo modo vengono creati gli stessi file del modello Applicazione di servizio WCF che viene però organizzato come se fosse un sito Web ASP.NET. Vengono create le cartelle App_Data e App_Code.  
  
### <a name="wcf-service-item-template"></a>Modello di elemento del servizio WCF  
 Il modello di elemento del servizio WCF è un modello personalizzato che fornisce un modo rapido per aggiungere servizi WCF ai progetti di Visual Studio esistenti.  
  
 Per usare questo modello, passare al riquadro **Esplora soluzioni** , fare clic con il pulsante destro del mouse sul nome del progetto, scegliere **Aggiungi**, quindi fare clic su **nuovo elemento** per aprire la finestra di dialogo **Aggiungi nuovo elemento** .  
  
 L'interfaccia del servizio e file di implementazione vengono inseriti nella cartella radice del progetto.  
  
 Il modello tenterà di unire la sezione di configurazione del nuovo servizio con il file di configurazione esistente, nel caso siano compatibili.  
  
 Se il progetto esistente è un progetto Web viene creato anche un file del host del servizio (service1.svc).  
  
### <a name="wcf-wf-service-project-and-item-template"></a>Modello di elemento e progetto di servizio WF WCF.  
 Questi modelli creano servizi WCF che ospitano un servizio del flusso di lavoro, ovvero un flusso di lavoro a cui è possibile accedere come un servizio Web. Sono disponibili modelli separati per XAML o modelli di programmazione imperativi. Mediante i modelli, è possibile creare un flusso di lavoro sequenziale o di macchina a stati. Per ulteriori informazioni su questi tipi di flusso di lavoro, vedere [procedura: creare un flusso di lavoro](../windows-workflow-foundation/how-to-create-a-workflow.md). Per ulteriori informazioni sulla creazione di progetti flusso di lavoro, vedere [creazione di progetti flusso di lavoro legacy](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer).  
  
 La finestra di progettazione di Visual Studio è più rispondente quando vengono usati flussi di lavoro di tipo XOML anziché quelli basati sul codice. XOML è il tipo di flusso predefinito che viene creato.  
  
### <a name="wcf-syndication-service-library-template"></a>Modello Libreria di servizi di diffusione WCF  
 Questo modello consente di esporre il feed in formato RSS o ATOM come servizio WCF. Per ulteriori informazioni, vedere la pagina relativa alla [diffusione WCF](./feature-details/wcf-syndication.md).  
  
#### <a name="changing-the-address-of-the-feed"></a>Modifica dell'indirizzo del feed  
 Il modello di pubblicazione utilizza Internet Explorer durante l'esecuzione. Quando si fa clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** in Visual Studio, selezionare **Proprietà**, quindi selezionare la scheda **debug** ed è possibile visualizzare l'indirizzo predefinito del modello. Internet Explorer tenterà di aprire il feed a questo indirizzo.  
  
 Se si modifica l'indirizzo del feed, è necessario modificare anche l'indirizzo nella scheda **debug** . In caso contrario, Internet Explorer tenterà di aprire il feed all'indirizzo predefinito e avrà esito negativo.  
  
### <a name="ajax-enabled-wcf-service-item-template"></a>Modello di elemento del servizio WCF con supporto AJAX  
 Questo modello espone un controllo AJAX come servizio WCF. Per ulteriori informazioni sui controlli AJAX, vedere la [documentazione del controllo AJAX](https://docs.microsoft.com/aspnet/ajax/).  
  
### <a name="silverlight-enabled-wcf-service-item-template"></a>Modello di elemento del servizio WCF con supporto Silverlight  
 Questo modello consente di creare un servizio Web che fornisce dati a un client Silverlight o front-end. Il modello può essere aggiunto a un sito Web o a un progetto di applicazione Web per creare un servizio WCF, che include il codice e la configurazione del servizio che supportano la comunicazione con un client Silverlight. È quindi possibile utilizzare **Aggiungi riferimento al servizio** per aggiungere un proxy client del servizio al client e scambiare i dati tra il client Silverlight e il servizio WCF abilitato per Silverlight.  
  
 Per accedere a questo modello, fare clic con il pulsante destro del mouse su un sito Web o un progetto di applicazione Web in **Esplora soluzioni**, scegliere **Aggiungi un nuovo elemento**e fare clic su **servizio WCF abilitato per Silverlight**.  
  
> [!NOTE]
> Il servizio WCF con supporto Silverlight espone un endpoint `basicHttpBinding` senza abilitare alcuna impostazione di sicurezza. Le informazioni sul servizio possono pertanto essere recuperate da tutti i client che si connettono a questo servizio. I messaggi scambiati tra il servizio e il client non sono inoltre firmati o crittografati. Per proteggere l'endpoint in modo appropriato, è necessario utilizzare l'autenticazione ASP.NET, HTTPS o altri meccanismi.  
  
## <a name="see-also"></a>Vedere anche

- [Host del servizio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
- [Client di prova WCF (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)

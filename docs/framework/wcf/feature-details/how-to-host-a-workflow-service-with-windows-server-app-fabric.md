---
title: 'Procedura: ospitare un servizio flusso di lavoro con Windows Server AppFabric'
ms.date: 03/30/2017
ms.assetid: 83b62cce-5fc2-4c6d-b27c-5742ba3bac73
ms.openlocfilehash: 2c1e4e8763ad9bd65099173c75d272965ac8caa8
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2018
ms.locfileid: "48840627"
---
# <a name="how-to-host-a-workflow-service-with-windows-server-app-fabric"></a>Procedura: ospitare un servizio flusso di lavoro con Windows Server AppFabric
L'hosting di servizi di flusso di lavoro in AppFabric è simile all'hosting in IIS/WAS. L'unica differenza consiste nel fatto che tramite gli strumenti di AppFabric sono garantiti la distribuzione, il monitoraggio e la gestione dei servizi di flusso di lavoro. Questo argomento viene utilizzato il servizio del flusso di lavoro creato nel [creazione di un servizio del flusso di lavoro a esecuzione prolungata](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md). in cui viene presentata la procedura dettagliata per la creazione di un servizio di flusso di lavoro. In questo argomento verrà invece illustrato come ospitare il servizio di flusso di lavoro mediante AppFabric. Per altre informazioni su Windows Server AppFabric, vedere [Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=193037&clcid=0x409). Prima di completare i passaggi seguenti, assicurarsi di aver installato Windows Server AppFabric.  Per questo scopo, aprire Internet Information Services (inetmgr.exe), fare clic sul nome del server nella **connessioni** consente di visualizzare, fare clic su siti e fare clic su **sito Web predefinito**. Nel lato destro dello schermo viene visualizzato una sezione intitolata **AppFabric**. Se tale sezione non viene visualizzata (controllare nella parte superiore del riquadro di destra), AppFabric non è installato. Per altre informazioni sull'installazione di Windows Server AppFabric, vedere [installazione di Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=193136).  
  
### <a name="creating-a-simple-workflow-service"></a>Creazione di un servizio di flusso di lavoro semplice  
  
1.  Aprire Visual Studio 2012 e caricare la soluzione OrderProcessing creata nel [creazione di un servizio del flusso di lavoro a esecuzione prolungata](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md) argomento.  
  
2.  Fare clic il **OrderService** del progetto e selezionare **delle proprietà** e selezionare il **Web** scheda.  
  
3.  Nel **azione di avvio** sezione della pagina delle proprietà selezionate **pagina specifica** e digitare Service1.xamlx nella casella di modifica.  
  
4.  Nel **i server** sezione della pagina delle proprietà selezionate **Usa Server Web IIS locale** e digitare l'URL seguente: `http://localhost/OrderService`.  
  
5.  Scegliere il **crea Directory virtuale** pulsante. In questo modo verrà creata una nuova directory virtuale e verrà configurato il progetto per copiare i file necessari nella directory virtuale quando il progetto viene compilato.  In alternativa, è possibile copiare manualmente il file con estensione xamlx, il file web.config e qualsiasi DLL necessaria per la directory virtuale.  
  
### <a name="configuring-a-workflow-service-hosted-in-windows-server-app-fabric"></a>Configurazione di un servizio di flusso di lavoro ospitato in Windows Server AppFabric  
  
1.  Aprire Gestione Internet Information Services (inetmgr.exe).  
  
2.  Passare alla directory virtuale OrderService nel **connessioni** riquadro.  
  
3.  Fare clic con il pulsante destro OrderService e selezionare **Gestisci servizi WCF e WF**, **Configura...** . Il **Configura WCF e WF per l'applicazione** verrà visualizzata la finestra di dialogo.  
  
4.  Selezionare il **generale** scheda per visualizzare informazioni generali sull'applicazione, come illustrato nella schermata riportata di seguito.  
  
     ![Scheda Generale della finestra di dialogo di configurazione App Fabric](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-general.gif "AppFabricConfiguration-generale")  
  
5.  Selezionare il **Monitoring** scheda. In questo modo verranno visualizzate diverse impostazioni di monitoraggio come mostrato nella schermata seguente.  
  
     ![Scheda monitoraggio della configurazione dell'infrastruttura di app](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-monitoring.gif "AppFabricConfiguration-monitoraggio")  
  
     Per altre informazioni sulla configurazione del servizio del flusso di lavoro monitoraggio in AppFabric vedere [configurazione del monitoraggio con AppFabric](https://go.microsoft.com/fwlink/?LinkId=193153).  
  
6.  Selezionare il **persistenza del flusso di lavoro** scheda. In questo modo è possibile configurare l'applicazione per utilizzare il provider di salvataggio permanente predefinito di AppFabric come mostrato nella schermata seguente.  
  
     ![Configurazione App Fabric &#45; persistenza](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-persistence.gif "AppFabricConfiguration-persistenza")  
  
     Per altre informazioni sulla configurazione della persistenza del flusso di lavoro in Windows Server AppFabric, vedere [configurazione di persistenza del flusso di lavoro in AppFabric](https://go.microsoft.com/fwlink/?LinkId=193148).  
  
7.  Selezionare il **gestione Host flusso di lavoro** scheda. In questo modo è possibile specificare il momento in cui le istanze del servizio di flusso di lavoro inattive devono essere scaricate e salvate in modo permanente come mostrato nella schermata seguente.  
  
     ![Gestione Host flusso di lavoro della configurazione AppFabric](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-management.gif "AppFabricConfiguration-Management")  
  
     Per altre informazioni sulla configurazione di gestione host flusso di lavoro, vedere [configurazione della gestione Host flusso di lavoro in AppFabric](https://go.microsoft.com/fwlink/?LinkId=193151).  
  
8.  Selezionare il **avvio automatico** scheda. In questo modo è possibile specificare impostazioni di avvio automatico per i servizi di flusso di lavoro nell'applicazione come mostrato nella schermata seguente.  
  
     ![App Fabric automatica&#45;Avvia configurazione](../../../../docs/framework/wcf/feature-details/media/appfabricconfigurationautostart.gif "AppFabricConfigurationAutostart")  
  
     Per altre informazioni sulla configurazione di avvio automatico, vedere [configurazione dell'avvio automatico con AppFabric](https://go.microsoft.com/fwlink/?LinkId=193150).  
  
9. Selezionare il **limitazione** scheda. In questo modo è possibile configurare impostazioni di limitazione per il servizio di flusso di lavoro come mostrato nella schermata seguente.  
  
     ![La limitazione delle richieste di configurazione App Fabric](../../../../docs/framework/wcf/feature-details/media/appfabricconfigurationthrottling.gif "AppFabricConfigurationThrottling")  
  
     Per altre informazioni sulla configurazione di limitazione delle richieste, vedere [configurazione della limitazione](https://go.microsoft.com/fwlink/?LinkId=193149).  
  
10. Selezionare il **sicurezza** scheda. In questo modo è possibile configurare impostazioni di sicurezza per l'applicazione come mostrato nella schermata seguente.  
  
     ![Configurazione della sicurezza AppFabric](../../../../docs/framework/wcf/feature-details/media/appfabricconfiguration-security.gif "AppFabricConfiguration-sicurezza")  
  
     Per altre informazioni sulla configurazione della protezione con Windows Server AppFabric, vedere [configurazione della protezione con AppFabric](https://go.microsoft.com/fwlink/?LinkId=193152).  
  
### <a name="using-windows-server-app-fabric"></a>Utilizzo di Windows Server AppFabric  
  
1.  Compilare la soluzione per copiare i file necessari nella directory virtuale.  
  
2.  Fare clic con il pulsante destro del progetto OrderClient e selezionare **Debug**, **Avvia nuova istanza** per avviare l'applicazione client.  
  
3.  Verrà eseguito il client e Visual Studio verrà visualizzata un' **avviso di sicurezza connessione** finestra di dialogo, fare clic sul **non collegare** pulsante. In questo modo non viene effettuata la connessione di Visual Studio al processo IIS per l'esecuzione del debug.  
  
4.  L'applicazione client consentirà di chiamare immediatamente il servizio di flusso di lavoro e successivamente si verificherà un periodo di attesa. Il servizio di flusso di lavoro diventerà inattivo e sarà salvato in modo permanente. Tale condizione può essere verificata avviando Internet Information Services (inetmgr.exe), passando a OrderService nel riquadro Connessioni e selezionandolo. Successivamente, fare clic sull'icona del dashboard di AppFabric nel riquadro di destra. In Istanze WF permanenti si osserverà la presenza di un'istanza del servizio di flusso di lavoro salvato in modo permanente come mostrato nella schermata seguente.  
  
     ![Dashboard di AppFabric](../../../../docs/framework/wcf/feature-details/media/appfabricdashboard.gif "AppFabricDashboard")  
  
     Il **cronologia istanze WF** Elenca le informazioni relative al servizio del flusso di lavoro, ad esempio il numero di attivazioni del servizio del flusso di lavoro, il numero di completamenti dell'istanza del servizio del flusso di lavoro e il numero di istanze del flusso di lavoro con errori. In Istanze attive o inattive viene visualizzato un collegamento; facendo clic su di esso verranno visualizzate ulteriori informazioni sulle istanze del flusso di lavoro inattive come mostrato nella schermata seguente.  
  
     ![Dettagli dell'istanza del flusso di lavoro persistente](../../../../docs/framework/wcf/feature-details/media/persisteddetail.gif "PersistedDetail")  
  
     Per altre informazioni su Windows Server AppFabric vedere le funzionalità e come usarli [funzionalità di Hosting di Windows Server App Fabric](https://go.microsoft.com/fwlink/?LinkID=193143&clcid=0x409)  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione di un servizio flusso di lavoro a esecuzione prolungata](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md)  
 [Windows Server AppFabric con funzionalità di Hosting](https://go.microsoft.com/fwlink/?LinkId=193143)  
 [Installazione di Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=193136)  
 [Documentazione di Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=193037&clcid=0x409)

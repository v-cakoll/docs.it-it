---
title: 'Procedura: ospitare un servizio flusso di lavoro con Windows Server AppFabric'
ms.date: 03/30/2017
ms.assetid: 83b62cce-5fc2-4c6d-b27c-5742ba3bac73
ms.openlocfilehash: 519c76e3e46e01b5e8c696234e39fefbb9f8ad06
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593308"
---
# <a name="how-to-host-a-workflow-service-with-windows-server-app-fabric"></a>Procedura: ospitare un servizio flusso di lavoro con Windows Server AppFabric

L'hosting di servizi di flusso di lavoro in AppFabric è simile all'hosting in IIS/WAS. L'unica differenza consiste nel fatto che tramite gli strumenti di AppFabric sono garantiti la distribuzione, il monitoraggio e la gestione dei servizi di flusso di lavoro. In questo argomento viene utilizzato il servizio del flusso di lavoro creato in [creazione di un servizio flusso di lavoro a esecuzione prolungata](creating-a-long-running-workflow-service.md). in cui viene presentata la procedura dettagliata per la creazione di un servizio di flusso di lavoro. In questo argomento verrà invece illustrato come ospitare il servizio di flusso di lavoro mediante AppFabric. Per ulteriori informazioni su Windows Server AppFabric, vedere la [documentazione di Windows Server](https://docs.microsoft.com/previous-versions/appfabric/ff384253(v=azure.10))AppFabric. Prima di completare i passaggi seguenti, assicurarsi di aver installato Windows Server AppFabric.  A tale scopo, aprire Internet Information Services (inetmgr. exe), fare clic sul nome del server nella visualizzazione **connessioni** , fare clic su siti e quindi su **sito Web predefinito**. Sul lato destro dello schermo dovrebbe essere visualizzata una sezione denominata **infrastruttura dell'app**. Se tale sezione non viene visualizzata (controllare nella parte superiore del riquadro di destra), AppFabric non è installato. Per altre informazioni sull'installazione di Windows Server AppFabric, vedere [installazione di Windows Server](https://docs.microsoft.com/previous-versions/appfabric/ee790960(v=azure.10))AppFabric.  
  
### <a name="creating-a-simple-workflow-service"></a>Creazione di un servizio di flusso di lavoro semplice  
  
1. Aprire Visual Studio 2012 e caricare la soluzione OrderProcessing creata nell'argomento [creazione di un servizio di flusso di lavoro a esecuzione prolungata](creating-a-long-running-workflow-service.md) .  
  
2. Fare clic con il pulsante destro del mouse sul progetto **OrderService** e selezionare **Proprietà** e selezionare la scheda **Web** .  
  
3. Nella sezione **azione di avvio** della pagina delle proprietà selezionare una **pagina specifica** e digitare Service1. xamlx nella casella di modifica.  
  
4. Nella sezione **Server** della pagina delle proprietà selezionare **Usa server Web IIS locale** e digitare l'URL seguente: `http://localhost/OrderService` .  
  
5. Fare clic sul pulsante **Crea directory virtuale** . In questo modo verrà creata una nuova directory virtuale e verrà configurato il progetto per copiare i file necessari nella directory virtuale quando il progetto viene compilato.  In alternativa, è possibile copiare manualmente il file con estensione xamlx, il file web.config e qualsiasi DLL necessaria per la directory virtuale.  
  
### <a name="configuring-a-workflow-service-hosted-in-windows-server-app-fabric"></a>Configurazione di un servizio di flusso di lavoro ospitato in Windows Server AppFabric  
  
1. Aprire Gestione Internet Information Services (inetmgr.exe).  
  
2. Passare alla directory virtuale OrderService nel riquadro **connessioni** .  
  
3. Fare clic con il pulsante destro del mouse su OrderService e scegliere **Gestisci servizi WCF e WF**, **Configura...**. Viene visualizzata la finestra **di dialogo Configura WCF e WF per l'applicazione** .  
  
4. Selezionare la scheda **generale** per visualizzare informazioni generali sull'applicazione, come illustrato nello screenshot seguente.  
  
     ![Scheda generale della finestra di dialogo per configurazione di App Fabric](media/appfabricconfiguration-general.gif "AppFabricConfiguration-generale")  
  
5. Selezionare la scheda **monitoraggio** . Vengono visualizzate diverse impostazioni di monitoraggio, come illustrato nella schermata seguente.  
  
     ![Configurazione App Fabric - Scheda monitoraggio](media/appfabricconfiguration-monitoring.gif "AppFabricConfiguration-monitoraggio")  
  
     Per altre informazioni sulla configurazione del monitoraggio dei servizi del flusso di lavoro in AppFabric, vedere [configurazione del monitoraggio con l'infrastruttura di app](https://docs.microsoft.com/previous-versions/appfabric/ee677384(v=azure.10)).  
  
6. Selezionare la scheda **persistenza del flusso di lavoro** . In questo modo è possibile configurare l'applicazione per l'uso del provider di persistenza predefinito di App Fabric, come illustrato nello screenshot seguente.  
  
     ![Configurazione di App Fabric &#45; persistenza](media/appfabricconfiguration-persistence.gif "AppFabricConfiguration-persistenza")  
  
     Per altre informazioni sulla configurazione della persistenza del flusso di lavoro in Windows Server AppFabric, vedere [configurazione della persistenza del flusso di lavoro in infrastruttura di app](https://docs.microsoft.com/previous-versions/appfabric/ee677353(v=azure.10))  
  
7. Selezionare la scheda **Gestione host del flusso di lavoro** . In questo modo è possibile specificare quando le istanze del servizio flusso di lavoro inattivo devono essere scaricate e rese permanente come illustrato nello screenshot seguente.  
  
     ![Gestione host flusso di lavoro configurazione di App Fabric](media/appfabricconfiguration-management.gif "AppFabricConfiguration-gestione")  
  
     Per altre informazioni sulla configurazione di gestione host del flusso di lavoro, vedere [configurazione della gestione host del flusso di lavoro in infrastruttura di app](https://docs.microsoft.com/previous-versions/appfabric/ff383424(v=azure.10))  
  
8. Selezionare la scheda **avvio automatico** . Ciò consente di specificare le impostazioni di avvio automatico per i servizi del flusso di lavoro nell'applicazione, come illustrato nello screenshot seguente.  
  
     ![Screenshot che mostra la configurazione di avvio automatico&#45;dell'infrastruttura di app.](./media/how-to-host-a-workflow-service-with-windows-server-app-fabric/app-fabric-auto-start-configuration.gif)  
  
     Per altre informazioni sulla configurazione dell'avvio automatico, vedere [configurazione dell'avvio automatico con l'infrastruttura di app](https://docs.microsoft.com/previous-versions/appfabric/ee677261(v=azure.10)).  
  
9. Selezionare la scheda **limitazione** . In questo modo è possibile configurare le impostazioni di limitazione per il servizio del flusso di lavoro, come illustrato nella schermata seguente.  
  
     ![Screenshot che mostra la configurazione della limitazione dell'infrastruttura dell'app.](./media/how-to-host-a-workflow-service-with-windows-server-app-fabric/app-fabric-throttling-configuration.gif)  
  
     Per altre informazioni sulla configurazione della limitazione, vedere [configurazione della limitazione con l'infrastruttura di app](https://docs.microsoft.com/previous-versions/appfabric/ee677261(v=azure.10)).  
  
10. Selezionare la scheda **sicurezza** . In questo modo è possibile configurare le impostazioni di sicurezza per l'applicazione, come illustrato nello screenshot seguente.  
  
     ![Configurazione App Fabric - Sicurezza](media/appfabricconfiguration-security.gif "AppFabricConfiguration-sicurezza")  
  
     Per altre informazioni sulla configurazione della sicurezza con Windows Server AppFabric, vedere [configurazione della sicurezza con l'infrastruttura di app](https://docs.microsoft.com/previous-versions/appfabric/ee677278(v=azure.10)).  
  
### <a name="using-windows-server-app-fabric"></a>Utilizzo di Windows Server AppFabric  
  
1. Compilare la soluzione per copiare i file necessari nella directory virtuale.  
  
2. Fare clic con il pulsante destro del mouse sul progetto OrderClient e selezionare **debug**, **Avvia nuova istanza** per avviare l'applicazione client.  
  
3. Il client verrà eseguito e in Visual Studio verrà visualizzata la finestra di dialogo **Connetti avviso di sicurezza** , quindi fare clic sul pulsante **non alleghi** . In questo modo non viene effettuata la connessione di Visual Studio al processo IIS per l'esecuzione del debug.  
  
4. L'applicazione client consentirà di chiamare immediatamente il servizio di flusso di lavoro e successivamente si verificherà un periodo di attesa. Il servizio di flusso di lavoro diventerà inattivo e sarà salvato in modo permanente. Tale condizione può essere verificata avviando Internet Information Services (inetmgr.exe), passando a OrderService nel riquadro Connessioni e selezionandolo. Successivamente, fare clic sull'icona del dashboard di AppFabric nel riquadro di destra. In istanze WF salvate verrà visualizzata una sola istanza del servizio flusso di lavoro permanente, come illustrato nella schermata seguente.  
  
     ![Screenshot che mostra il dashboard di App Fabric.](./media/how-to-host-a-workflow-service-with-windows-server-app-fabric/app-fabric-dashboard.gif)  
  
     La **cronologia dell'istanza di WF** elenca le informazioni relative al servizio del flusso di lavoro, ad esempio il numero di attivazioni del servizio del flusso di lavoro, il numero di completamenti dell'istanza del servizio flusso di lavoro e il numero di istanze del flusso di lavoro In istanze attive o inattive verrà visualizzato un collegamento. Se si fa clic sul collegamento, verranno visualizzate altre informazioni sulle istanze del flusso di lavoro inattivo, come illustrato nello screenshot seguente.  
  
     ![Screenshot che mostra i dettagli dell'istanza del flusso di lavoro permanente.](./media/how-to-host-a-workflow-service-with-windows-server-app-fabric/persisted-workflow-instance-detail.gif)  
  
     Per altre informazioni sulle funzionalità di Windows Server AppFabric e su come usarle, vedere [funzionalità di hosting di Windows Server](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10)) AppFabric  
  
## <a name="see-also"></a>Vedere anche

- [Creazione di un servizio flusso di lavoro a esecuzione prolungata](creating-a-long-running-workflow-service.md)
- [Funzionalità di hosting di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
- [Installazione di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee790960(v=azure.10))
- [Documentazione di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff384253(v=azure.10))

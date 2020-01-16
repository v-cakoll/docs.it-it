---
title: Hosting di servizi flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 2d55217e-8697-4113-94ce-10b60863342e
ms.openlocfilehash: 21e24853229d09e3f1af719573f47bb12c8fddb6
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75963735"
---
# <a name="hosting-workflow-services"></a>Hosting di servizi flusso di lavoro

Per poter rispondere ai messaggi in arrivo, un servizio flusso di lavoro deve essere ospitato. I servizi flusso di lavoro utilizzano l'infrastruttura di messaggistica WCF e sono quindi ospitati in modi analoghi. Analogamente ai servizi WCF, i servizi flusso di lavoro possono essere ospitati in qualsiasi applicazione gestita, in Internet Information Services (IIS) o in servizi di attivazione dei processi di Windows (WAS). Inoltre, i servizi flusso di lavoro possono essere ospitati in Windows Server AppFabric. Per altre informazioni su Windows Server App Fabric, vedere la [documentazione di Windows Server](https://docs.microsoft.com/previous-versions/appfabric/ff384253(v=azure.10))AppFabric, le [funzionalità di hosting di AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))e i concetti di hosting di [AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677371(v=azure.10)). Per ulteriori informazioni sui vari modi per ospitare i servizi WCF, vedere [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).

## <a name="hosting-in-a-managed-application"></a>Hosting in un'applicazione gestita
 Per ospitare un servizio flusso di lavoro in un'applicazione gestita, utilizzare la classe <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Il costruttore <xref:System.ServiceModel.Activities.WorkflowServiceHost> consente di specificare un'istanza di servizio flusso di lavoro singleton, una definizione del servizio flusso di lavoro o un'attività che utilizza le attività di messaggistica del flusso di lavoro. La chiamata a <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> fa in modo che il servizio avvii l'ascolto di messaggi in ingresso.

## <a name="hosting-under-iis-or-was"></a>Hosting in IIS o WAS
 L'hosting di un servizio flusso di lavoro in IIS o WAS prevede la creazione di una directory virtuale e il posizionamento dei file nella directory virtuale che definiscono il servizio e il relativo comportamento. Quando si ospita un servizio flusso di lavoro in IIS o WAS esistono diverse possibilità:

- Posizionare un file con estensione xamlx che definisce il servizio flusso di lavoro in una directory virtuale IIS/WAS insieme a un file Web.config che specifica i comportamenti del servizio, gli endpoint e altri elementi di configurazione.

- Posizionare un file con estensione xamlx che definisce il servizio flusso di lavoro in una directory virtuale IIS/WAS. Il file con estensione xamlx specifica gli endpoint da esporre. Gli endpoint sono specificati in un elemento `WorkflowService.Endpoints`, come indicato nell'esempio seguente.

    ```xml
    <WorkflowService xmlns="http://schemas.microsoft.com/netfx/2009/xaml/servicemodel"  xmlns:p1="http://schemas.microsoft.com/netfx/2009/xaml/activities" xmlns:sad="clr-namespace:System.Activities.Debugger;assembly=System.Activities" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
      <WorkflowService.Endpoints>
        <Endpoint ServiceContractName="IWorkFlowEchoService" AddressUri="">
          <Endpoint.Binding>
            <BasicHttpBinding />
          </Endpoint.Binding>
        </Endpoint>
      </WorkflowService.Endpoints>
    <!-- ... -->
    </WorkflowService>
    ```

    > [!NOTE]
    > Non è possibile specificare i comportamenti in un file con estensione xamlx, pertanto è richiesto un file Web.config se è necessario specificare impostazioni relative al comportamento.

- Posizionare un file con estensione xamlx che definisce il servizio flusso di lavoro in una directory virtuale IIS/WAS. Posizionare inoltre un file con estensione svc nella directory virtuale. Il file con estensione svc consente di specificare una factory di host di servizio Web personalizzata, applicare il comportamento personalizzato o caricare la configurazione da un percorso personalizzato.

- Posizionare un assembly nella directory virtuale IIS/WAS che contiene un'attività che utilizza le attività di messaggistica di WCF.

 Un file con estensione xamlx che definisce un servizio del flusso di lavoro deve contenere un <`Service`> elemento radice o un elemento radice che contiene qualsiasi tipo derivato da <xref:System.Workflow.ComponentModel.Activity>. Quando si usa il modello di attività di Visual Studio, viene creato un file con estensione xamlx. Quando si utilizza il modello di servizio del flusso di lavoro WCF, viene creato un file con estensione xamlx.

## <a name="hosting-workflow-services-under-windows-server-app-fabric"></a>Hosting di servizi flusso di lavoro in Windows Server AppFabric
 L'hosting di un servizio flusso di lavoro in Windows Server AppFabric è simile all'hosting in IIS/WAS. L'unica differenza consiste nel fatto che Windows Server App Fabric viene installato. In Windows Server AppFabric vengono forniti gli strumenti aggiunti a Gestione Internet Information Services, nonché i cmdlet PowerShell. Tali strumenti semplificano la distribuzione, la gestione e il rilevamento dei servizi flusso di lavoro e dei servizi WCF.

## <a name="referencing-custom-activities"></a>Riferimento ad attività personalizzate
 È necessario aggiungere riferimenti alle attività personalizzate alla sezione <`Assemblies`> in <`System.Web.Compilation`>, in modo che vengano caricati nel dominio dell'applicazione e che il deserializzatore XAML sia in grado di individuare i tipi. È possibile configurare queste impostazioni a livello dell'applicazione o nel file Web.config radice, se tali impostazioni devono essere applicate a tutte le applicazioni nel computer.

## <a name="deployment"></a>Distribuzione
 Lo strumento Distribuzione Web è stato creato per agevolare il processo di distribuzione. Lo strumento consente di eseguire la migrazione delle applicazioni tra IIS 6.0 e IIS 7.0, sincronizzare server farm e inserire in pacchetti, archiviare e distribuire applicazioni Web. Per ulteriori informazioni, vedere [MS Deployment Tool](https://go.microsoft.com/fwlink/?LinkId=178690).

## <a name="see-also"></a>Vedere anche

- [Elementi interni dell'host dei servizi flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)
- [Configurazione di WorkflowServiceHost](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)

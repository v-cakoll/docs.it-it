---
title: Gestione di più versioni in WorkflowServiceHost
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 60887eed-df40-4412-b812-41e1dd329d15
ms.openlocfilehash: bc662e51c96a06737e1bd6fd78d5f70f3922d080
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184465"
---
# <a name="side-by-side-versioning-in-workflowservicehost"></a><span data-ttu-id="588a0-102">Gestione di più versioni in WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="588a0-102">Side by Side Versioning in WorkflowServiceHost</span></span>
<span data-ttu-id="588a0-103">Il <xref:System.ServiceModel.Activities.WorkflowServiceHost> controllo delle versioni side-by-side introdotto in .NET Framework 4.5.NET Framework 4.5 offre la possibilità di ospitare più versioni di un servizio flusso di lavoro in un singolo endpoint.</span><span class="sxs-lookup"><span data-stu-id="588a0-103">The <xref:System.ServiceModel.Activities.WorkflowServiceHost> side-by-side versioning introduced in .NET Framework 4.5 provides the capability to host multiple versions of a workflow service on a single endpoint.</span></span> <span data-ttu-id="588a0-104">La funzionalità side-by-side consente di configurare un servizio di flusso di lavoro in modo che le sue nuove istanze vengano create con la nuova definizione del flusso di lavoro, mentre le istanze in esecuzione vengono completate con la definizione esistente.</span><span class="sxs-lookup"><span data-stu-id="588a0-104">The side-by-side functionality provided allows a workflow service to be configured so that new instances of the workflow service are created using the new workflow definition, while running instances complete using the existing definition.</span></span> <span data-ttu-id="588a0-105">In questo argomento viene fornita una panoramica dell'esecuzione side-by-side del servizio di flusso di lavoro usando <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="588a0-105">This topic provides an overview of workflow service side-by-side execution using <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="588a0-106">Per scaricare un esempio e guardare una procedura dettagliata video del controllo delle versioni side-by-side del servizio flusso di lavoro, vedere [Controllo delle versioni side-by-side con un servizio flusso di lavoro Xamlx ospitato](https://go.microsoft.com/fwlink/?LinkId=393746)sul Web .</span><span class="sxs-lookup"><span data-stu-id="588a0-106">To download a sample and watch a video walkthrough of workflow service side-by-side versioning, see [Side by Side Versioning with a Web-Hosted Xamlx Workflow Service](https://go.microsoft.com/fwlink/?LinkId=393746).</span></span>  
  
## <a name="hosting-multiple-versions-in-a-workflow-service"></a><span data-ttu-id="588a0-107">Hosting di più versioni in un servizio di flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="588a0-107">Hosting Multiple Versions in a Workflow Service</span></span>  
 <span data-ttu-id="588a0-108"><xref:System.ServiceModel.Activities.WorkflowServiceHost> contiene due proprietà che possono essere configurate per consentire l'esecuzione side-by-side di più versioni di un flusso di lavoro: <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> e <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.</span><span class="sxs-lookup"><span data-stu-id="588a0-108"><xref:System.ServiceModel.Activities.WorkflowServiceHost> contains two properties that can be configured to allow multiple versions of a workflow to execute side-by-side: <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> and <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.</span></span> <span data-ttu-id="588a0-109">La proprietà <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> contiene le versioni supportate del servizio di flusso di lavoro e la proprietà <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> viene usata per identificare in modo univoco ogni servizio di flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="588a0-109"><xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> contains the supported versions of the workflow service, and <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is used to uniquely identify each workflow service.</span></span> <span data-ttu-id="588a0-110">Questa operazione viene effettuata associando un oggetto <xref:System.Activities.WorkflowIdentity> al servizio di flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="588a0-110">This is done by associating a <xref:System.Activities.WorkflowIdentity> with the workflow service.</span></span> <span data-ttu-id="588a0-111"><xref:System.Activities.WorkflowIdentity> contiene tre informazioni di identificazione.</span><span class="sxs-lookup"><span data-stu-id="588a0-111">A <xref:System.Activities.WorkflowIdentity> contains three identifying pieces of information.</span></span> <span data-ttu-id="588a0-112">Le proprietà <xref:System.Activities.WorkflowIdentity.Name%2A> e <xref:System.Activities.WorkflowIdentity.Version%2A> contengono un nome e un oggetto <xref:System.Version> e sono obbligatorie, mentre la proprietà <xref:System.Activities.WorkflowIdentity.Package%2A> è facoltativa e può essere usata per specificare una stringa aggiuntiva che contiene informazioni quali il nome dell'assembly o altre informazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="588a0-112"><xref:System.Activities.WorkflowIdentity.Name%2A> and <xref:System.Activities.WorkflowIdentity.Version%2A> contain a name and a <xref:System.Version> and are required, and <xref:System.Activities.WorkflowIdentity.Package%2A> is optional and can be used to specify an additional string containing information such as assembly name or other desired information.</span></span> <span data-ttu-id="588a0-113">A ogni servizio di flusso di lavoro contenuto nella raccolta <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> deve essere associato un oggetto <xref:System.Activities.WorkflowIdentity> univoco.</span><span class="sxs-lookup"><span data-stu-id="588a0-113">Each workflow service contained in the <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> collection must have a unique <xref:System.Activities.WorkflowIdentity>.</span></span> <span data-ttu-id="588a0-114">Un oggetto <xref:System.Activities.WorkflowIdentity> è univoco se una qualsiasi delle tre relative proprietà è diversa da un altro oggetto <xref:System.Activities.WorkflowIdentity>.</span><span class="sxs-lookup"><span data-stu-id="588a0-114">A <xref:System.Activities.WorkflowIdentity> is unique if any of its three properties are different from another <xref:System.Activities.WorkflowIdentity>.</span></span> <span data-ttu-id="588a0-115">Un `null` <xref:System.Activities.WorkflowIdentity> è un valore <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>consentito per , ma solo una `null` <xref:System.Activities.WorkflowIdentity>versione precedente di un servizio flusso di lavoro può avere un estensione .</span><span class="sxs-lookup"><span data-stu-id="588a0-115">A `null` <xref:System.Activities.WorkflowIdentity> is an allowable value for <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, but only one previous version of a workflow service may have a `null` <xref:System.Activities.WorkflowIdentity>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="588a0-116"><xref:System.Activities.WorkflowIdentity> non deve contenere eventuali informazioni identificabili personalmente (PII).</span><span class="sxs-lookup"><span data-stu-id="588a0-116">A <xref:System.Activities.WorkflowIdentity> should not contain any personally identifiable information (PII).</span></span> <span data-ttu-id="588a0-117"><xref:System.Activities.WorkflowIdentity> si compone di tre parti: <xref:System.Activities.WorkflowIdentity.Name%2A> (<xref:System.String>), <xref:System.Activities.WorkflowIdentity.Version%2A> (<xref:System.Version>) e <xref:System.Activities.WorkflowIdentity.Package%2A> (<xref:System.String>).</span><span class="sxs-lookup"><span data-stu-id="588a0-117"><xref:System.Activities.WorkflowIdentity> is composed of three parts: a <xref:System.Activities.WorkflowIdentity.Name%2A> (<xref:System.String>), a <xref:System.Activities.WorkflowIdentity.Version%2A> (<xref:System.Version>), and a <xref:System.Activities.WorkflowIdentity.Package%2A> (<xref:System.String>).</span></span> <span data-ttu-id="588a0-118">Le informazioni su <xref:System.Activities.WorkflowIdentity> usate per creare un'istanza vengono generate a tutti i servizi di rilevamento configurati in vari punti del ciclo di vita di attività dal runtime.</span><span class="sxs-lookup"><span data-stu-id="588a0-118">Information about the <xref:System.Activities.WorkflowIdentity> used to create an instance is emitted to any configured tracking services at several different points of the activity life-cycle by the runtime.</span></span> <span data-ttu-id="588a0-119">La verifica di WF non ha alcun meccanismo per nascondere i PII (dati riservati dell'utente).</span><span class="sxs-lookup"><span data-stu-id="588a0-119">WF Tracking does not have any mechanism to hide PII (sensitive user data).</span></span> <span data-ttu-id="588a0-120">Di conseguenza, un'istanza di <xref:System.Activities.WorkflowIdentity> non deve contenere dati di PII poiché verrebbe generata dal runtime nei record di rilevamento e può essere visibile agli utenti con accesso alla visualizzazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="588a0-120">Therefore, a <xref:System.Activities.WorkflowIdentity> instance should not contain any PII data as it will be emitted by the runtime in tracking records and may be visible to anyone with access to view the tracking records.</span></span>  
  
### <a name="rules-for-hosting-multiple-versions-of-a-workflow-service"></a><span data-ttu-id="588a0-121">Regole per l'hosting di più versioni di un servizio di flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="588a0-121">Rules for Hosting Multiple Versions of a Workflow Service</span></span>  
 <span data-ttu-id="588a0-122">Quando un utente aggiunge un'ulteriore versione a <xref:System.ServiceModel.Activities.WorkflowServiceHost>, è necessario soddisfare diverse condizioni affinché un servizio di flusso di lavoro possa essere ospitato con lo stesso set di endpoint e la medesima descrizione.</span><span class="sxs-lookup"><span data-stu-id="588a0-122">When a user adds an additional version to the <xref:System.ServiceModel.Activities.WorkflowServiceHost>, there are several conditions that must be met in order for a workflow service to be hosted with the same set of endpoints and description.</span></span> <span data-ttu-id="588a0-123">Se una delle versioni aggiuntive non soddisfa queste condizioni, <xref:System.ServiceModel.Activities.WorkflowServiceHost> genera un'eccezione quando viene chiamato `Open`.</span><span class="sxs-lookup"><span data-stu-id="588a0-123">If any of the additional versions fail to meet these conditions, the <xref:System.ServiceModel.Activities.WorkflowServiceHost> throws an exception when `Open` is called.</span></span> <span data-ttu-id="588a0-124">Ogni definizione di flusso di lavoro fornita all'host come versione aggiuntiva deve soddisfare i requisiti seguenti (dove la versione principale è la definizione del servizio di flusso di lavoro fornita al costruttore host).</span><span class="sxs-lookup"><span data-stu-id="588a0-124">Each workflow definition provided to the host as an additional version must meet the following requirements (where the primary version is the workflow service definition that is provided to the host constructor).</span></span> <span data-ttu-id="588a0-125">La versione aggiuntiva del flusso di lavoro deve soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="588a0-125">The additional workflow version must:</span></span>  
  
- <span data-ttu-id="588a0-126">Disporre della stessa proprietà <xref:System.ServiceModel.Activities.WorkflowService.Name%2A> della versione principale del servizio di flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="588a0-126">Have the same the <xref:System.ServiceModel.Activities.WorkflowService.Name%2A> as the primary version of the workflow service.</span></span>  
  
- <span data-ttu-id="588a0-127">Non disporre di alcuna attività <xref:System.ServiceModel.Activities.Receive> o <xref:System.ServiceModel.Activities.SendReply> in <xref:System.ServiceModel.Activities.WorkflowService.Body%2A> che non sia presente anche nella versione principale e, nel caso, tali attività devono corrispondere al contratto dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="588a0-127">Must not have any <xref:System.ServiceModel.Activities.Receive> or <xref:System.ServiceModel.Activities.SendReply> activities in its <xref:System.ServiceModel.Activities.WorkflowService.Body%2A> that are not in the primary version, and they must match the operation contract.</span></span>  
  
- <span data-ttu-id="588a0-128">Disporre di una proprietà <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> univoca.</span><span class="sxs-lookup"><span data-stu-id="588a0-128">Have a unique <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.</span></span> <span data-ttu-id="588a0-129">Una sola definizione di flusso di lavoro può avere `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.</span><span class="sxs-lookup"><span data-stu-id="588a0-129">One and only one workflow definition may have a `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.</span></span>  
  
 <span data-ttu-id="588a0-130">Alcune modifiche sono consentite.</span><span class="sxs-lookup"><span data-stu-id="588a0-130">Some changes are permitted.</span></span> <span data-ttu-id="588a0-131">Gli elementi seguenti possono essere diversi tra una versione e l'altra:</span><span class="sxs-lookup"><span data-stu-id="588a0-131">The following items may be different between the versions:</span></span>  
  
- <span data-ttu-id="588a0-132"><xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> può avere un nome e un pacchetto diversi rispetto alla versione principale.</span><span class="sxs-lookup"><span data-stu-id="588a0-132">The <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> may have a different Name and Package than the primary version.</span></span>  
  
- <span data-ttu-id="588a0-133">Il valore di <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> può essere diverso rispetto alla versione principale.</span><span class="sxs-lookup"><span data-stu-id="588a0-133">The <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> value may be different than the primary version.</span></span>  
  
- <span data-ttu-id="588a0-134">Il valore di <xref:System.ServiceModel.Activities.WorkflowService.ConfigurationName%2A> può essere diverso rispetto alla versione principale.</span><span class="sxs-lookup"><span data-stu-id="588a0-134">The <xref:System.ServiceModel.Activities.WorkflowService.ConfigurationName%2A> may be different than the primary version.</span></span>  
  
- <span data-ttu-id="588a0-135">Il valore di <xref:System.ServiceModel.Activities.WorkflowService.ImplementedContracts%2A> può essere diverso rispetto alla versione principale.</span><span class="sxs-lookup"><span data-stu-id="588a0-135">The <xref:System.ServiceModel.Activities.WorkflowService.ImplementedContracts%2A> may be different than the primary version.</span></span>  
  
### <a name="configuring-the-definitionidentity"></a><span data-ttu-id="588a0-136">Configurazione di DefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="588a0-136">Configuring the DefinitionIdentity</span></span>  
 <span data-ttu-id="588a0-137">Quando un servizio flusso di lavoro <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> viene creato utilizzando la finestra di progettazione del flusso di lavoro, l'oggetto viene impostato utilizzando la finestra **Proprietà.When** a workflow service is created using the workflow designer, the is set using the Properties window.</span><span class="sxs-lookup"><span data-stu-id="588a0-137">When a workflow service is created using the workflow designer, the <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is set using the **Properties** window.</span></span> <span data-ttu-id="588a0-138">Fare clic all'esterno dell'attività radice del servizio nella finestra di progettazione per selezionare il servizio flusso di lavoro e scegliere **Finestra Proprietà** dal menu **Visualizza.**</span><span class="sxs-lookup"><span data-stu-id="588a0-138">Click outside of the service’s root activity in the designer to select the workflow service, and choose **Properties Window** from the **View** menu.</span></span> <span data-ttu-id="588a0-139">Selezionare **WorkflowIdentity** dall'elenco a discesa visualizzato accanto alla proprietà **DefinitionIdentity,** quindi espandere e specificare le proprietà desiderate. <xref:System.Activities.WorkflowIdentity></span><span class="sxs-lookup"><span data-stu-id="588a0-139">Select **WorkflowIdentity** from the drop-down list that appears beside the **DefinitionIdentity** property, and then expand and specify the desired <xref:System.Activities.WorkflowIdentity> properties.</span></span> <span data-ttu-id="588a0-140">Nell'esempio riportato di seguito l'oggetto <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> è configurato con <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` il e un <xref:System.Activities.WorkflowIdentity.Version%2A> di `1.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="588a0-140">In the following example the <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is configured with the <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` and a <xref:System.Activities.WorkflowIdentity.Version%2A> of `1.0.0.0`.</span></span> <span data-ttu-id="588a0-141">La proprietà <xref:System.Activities.WorkflowIdentity.Package%2A> è facoltativa e in questo esempio è `null`.</span><span class="sxs-lookup"><span data-stu-id="588a0-141"><xref:System.Activities.WorkflowIdentity.Package%2A> is optional and in this example is `null`.</span></span>  
  
 ![Screenshot che mostra la proprietà DefinitionIdentity.](./media/side-by-side-versioning-in-workflowservicehost/definitionidentity-property.bmp)  
  
 <span data-ttu-id="588a0-143">Quando un servizio di flusso di lavoro è self-hosted, la proprietà <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> viene configurata quando il servizio di flusso di lavoro viene costruito.</span><span class="sxs-lookup"><span data-stu-id="588a0-143">When a workflow service is self-hosted, the <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is configured when the workflow service is constructed.</span></span> <span data-ttu-id="588a0-144">Nell'esempio riportato <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> di seguito, l'oggetto è configurato <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` con <xref:System.Activities.WorkflowIdentity.Name%2A> `1.0.0.0`gli stessi valori dell'esempio precedente, con il oggetto e un di .</span><span class="sxs-lookup"><span data-stu-id="588a0-144">In the following example, the <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is configured with the same values as the previous example, with the <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` and a <xref:System.Activities.WorkflowIdentity.Name%2A> of `1.0.0.0`.</span></span>  
  
```csharp  
WorkflowService service = new WorkflowService  
{  
    Name = "MortgageWorkflowService",  
    Body = new MortgageWorkflow(),  
    DefinitionIdentity = new WorkflowIdentity  
    {  
        Name = "MortgageWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    }  
};  
```  
  
```vb  
Dim service As New WorkflowService  
With service  
    .Name = "MortgageWorkflowService"  
    .Body = New MortgageWorkflow  
    .DefinitionIdentity = New WorkflowIdentity With _  
    { _  
        .Name = "MortgageWorkflow", _  
        .Version = New Version(1, 0, 0, 0) _  
    }  
End With  
```  
  
 <span data-ttu-id="588a0-145">Un <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> oggetto non è obbligatorio, anche se solo una versione del servizio flusso di lavoro può avere un **valore null.**<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A></span><span class="sxs-lookup"><span data-stu-id="588a0-145">A <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is not required, although only one version of the workflow service may have a **null**<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="588a0-146">Questa condizione è utile se il servizio è stato distribuito inizialmente senza una proprietà <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> configurata e, successivamente, viene creata una versione aggiornata.</span><span class="sxs-lookup"><span data-stu-id="588a0-146">This is useful if the service was deployed initially without a <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> configured, and then an updated version is created.</span></span>  
  
### <a name="adding-a-new-version-to-a-web-hosted-workflow-service"></a><span data-ttu-id="588a0-147">Aggiunta di una nuova versione a un servizio di flusso di lavoro ospitato sul Web</span><span class="sxs-lookup"><span data-stu-id="588a0-147">Adding a New Version to a Web-hosted Workflow Service</span></span>  
 <span data-ttu-id="588a0-148">Il primo passaggio della configurazione di una nuova versione di un servizio di flusso di lavoro in un servizio ospitato sul Web consiste nel creare una nuova cartella nella cartella `App_Code`, denominandola come il file del servizio.</span><span class="sxs-lookup"><span data-stu-id="588a0-148">The first step in configuring a new version of a workflow service in a web-hosted service is to create a new folder in the `App_Code` folder that has the same name as the service file.</span></span> <span data-ttu-id="588a0-149">Se il file `xamlx` del servizio è denominato `MortgageWorkflow.xamlx`, la cartella deve essere denominata `MortgageWorkflow`.</span><span class="sxs-lookup"><span data-stu-id="588a0-149">If the service’s `xamlx` file is named `MortgageWorkflow.xamlx`, then the folder must be named `MortgageWorkflow`.</span></span> <span data-ttu-id="588a0-150">Inserire una copia del file `xamlx` del servizio originale in questa cartella e assegnarle un nuovo nome, ad esempio `MortgageWorkflowV1.xamlx`.</span><span class="sxs-lookup"><span data-stu-id="588a0-150">Place a copy of the original service’s `xamlx` file into this folder and rename it to a new name, such as `MortgageWorkflowV1.xamlx`.</span></span> <span data-ttu-id="588a0-151">Apportare le modifiche desiderate al servizio principale, aggiornare la relativa proprietà <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, quindi distribuire il servizio.</span><span class="sxs-lookup"><span data-stu-id="588a0-151">Make the desired changes to the primary service, update its <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, and then deploy the service.</span></span> <span data-ttu-id="588a0-152">Nell'esempio seguente, la proprietà <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> è stata aggiornata con la proprietà <xref:System.Activities.WorkflowIdentity.Name%2A>`MortgageWorkflow` e la proprietà <xref:System.Activities.WorkflowIdentity.Version%2A>`2.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="588a0-152">In the following example the <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> has been updated with a <xref:System.Activities.WorkflowIdentity.Name%2A> of `MortgageWorkflow` and a <xref:System.Activities.WorkflowIdentity.Version%2A> of `2.0.0.0`.</span></span>  
  
 ![Screenshot that shows DefinitionIdentity of WorkflowIdentity.](./media/side-by-side-versioning-in-workflowservicehost/definitionidentity-workflowidentity.bmp)  
  
 <span data-ttu-id="588a0-154">Quando il servizio viene riavviato, la versione precedente verrà aggiunta automaticamente alla raccolta <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> poiché si trova nella sottocartella `App_Code` designata.</span><span class="sxs-lookup"><span data-stu-id="588a0-154">When the service restarts, the previous version will automatically be added to the <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> collection because it is located in the designated `App_Code` subfolder.</span></span> <span data-ttu-id="588a0-155">Si noti che se la versione `null` <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> principale del servizio flusso di lavoro ha le versioni precedenti non verrà aggiunto.</span><span class="sxs-lookup"><span data-stu-id="588a0-155">Note that if the primary version of the workflow service has a `null` <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> the previous versions will not be added.</span></span> <span data-ttu-id="588a0-156">Una versione può avere una proprietà `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, tuttavia se sono presenti più versioni, la versione principale non deve essere quella con la proprietà `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, altrimenti le versioni precedenti non verranno aggiunte alla raccolta <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>.</span><span class="sxs-lookup"><span data-stu-id="588a0-156">One version may have a `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, but if there are multiple versions the primary version must not be the one with the `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> or else the previous versions will not be added to the <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> collection.</span></span>  
  
### <a name="adding-a-new-version-to-a-self-hosted-workflow-service"></a><span data-ttu-id="588a0-157">Aggiunta di una nuova versione a un servizio di flusso di lavoro self-hosted</span><span class="sxs-lookup"><span data-stu-id="588a0-157">Adding a New Version to a Self-hosted Workflow Service</span></span>  
 <span data-ttu-id="588a0-158">Quando si aggiunge una nuova versione a un servizio di flusso di lavoro self-hosted, l'oggetto <xref:System.ServiceModel.Activities.WorkflowServiceHost> viene configurato con la versione principale del servizio di flusso di lavoro e le versioni precedenti devono essere aggiunte in modo esplicito alla raccolta <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>.</span><span class="sxs-lookup"><span data-stu-id="588a0-158">When adding a new version to a self-hosted workflow service, the <xref:System.ServiceModel.Activities.WorkflowServiceHost> is configured with the primary version of the workflow service, and previous versions must be explicitly added to the <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> collection.</span></span> <span data-ttu-id="588a0-159">Nell'esempio seguente un oggetto <xref:System.ServiceModel.Activities.WorkflowServiceHost> viene configurato con un servizio di flusso di lavoro principale che usa una definizione del flusso di lavoro `MortgageWorkflowV2` e un servizio di flusso di lavoro configurato con una definizione del flusso di lavoro `MortgageWorkflowV1` viene aggiunto alla raccolta <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>.</span><span class="sxs-lookup"><span data-stu-id="588a0-159">In the following example, a <xref:System.ServiceModel.Activities.WorkflowServiceHost> is configured with a primary workflow service that uses a `MortgageWorkflowV2` workflow definition, and a workflow service configured with a `MortgageWorkflowV1` workflow definition is added to the <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> collection.</span></span> <span data-ttu-id="588a0-160">Ogni servizio di flusso di lavoro è configurato con una proprietà <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> univoca che riflette la versione della definizione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="588a0-160">Each workflow service is configured with a unique <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> that reflects the version of the workflow definition.</span></span>  
  
```csharp  
// Create the primary version of the workflow service.  
WorkflowService serviceV2 = new WorkflowService  
{  
    Name = "MortgageWorkflowService",  
    Body = new MortgageWorkflowV2(),  
    DefinitionIdentity = new WorkflowIdentity  
    {  
        Name = "MortgageWorkflow",  
        Version = new Version(2, 0, 0, 0)  
    }  
};  
  
// Configure the WorkflowServiceHost with the current version  
// of the workflow service. This code requires Administrator  
// privileges to function correctly. If running from Visual  
// Studio, Visual Studio must be run with Administrator privileges.  
WorkflowServiceHost host = new WorkflowServiceHost(serviceV2,
    new Uri("http://localhost:8080/MortgageWorkflowService"));  
  
// Create the previous version of the workflow service.  
WorkflowService serviceV1 = new WorkflowService  
{  
    Name = "MortgageWorkflowService",  
    Body = new MortgageWorkflowV1(),  
    DefinitionIdentity = new WorkflowIdentity  
    {  
        Name = "MortgageWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    }  
};  
  
// Add the previous version of the service to the SupportedVersions collection.  
host.SupportedVersions.Add(serviceV1);  
```  
  
```vb  
'Create the primary version of the workflow service  
Dim serviceV2 As New WorkflowService  
With serviceV2  
    .Name = "MortgageWorkflowService"  
    .Body = New MortgageWorkflowV2  
    .DefinitionIdentity = New WorkflowIdentity With _  
    { _  
        .Name = "MortgageWorkflow", _  
        .Version = New Version(2, 0, 0, 0) _  
    }  
End With  
  
'Configure the WorkflowServiceHost with the current version  
'of the workflow service. This code requires Administrator  
'privileges to function correctly. If running from Visual  
'Studio, Visual Studio must be run with Administrator privileges.  
  
Dim host As New WorkflowServiceHost(serviceV2, _  
    New Uri("http://localhost:8080/MortgageWorkflowService"))  
  
'Create the previous version of the workflow service.  
Dim serviceV1 As New WorkflowService  
With serviceV1  
    .Name = "MortgageWorkflowService"  
    .Body = New MortgageWorkflowV1  
    .DefinitionIdentity = New WorkflowIdentity With _  
    { _  
        .Name = "MortgageWorkflow", _  
        .Version = New Version(1, 0, 0, 0) _  
    }  
End With  
  
'Add the previous version of the service to the SupportedVersions collection.  
host.SupportedVersions.Add(serviceV1)  
```

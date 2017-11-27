---
title: 'Procedura: ospitare un flusso di lavoro non di servizio in IIS'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f362562c-767d-401b-8257-916616568fd4
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 892875fb8340220dc152f91ab2239257c7b96fb8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-host-a-non-service-workflow-in-iis"></a><span data-ttu-id="d8ff7-102">Procedura: ospitare un flusso di lavoro non di servizio in IIS</span><span class="sxs-lookup"><span data-stu-id="d8ff7-102">How to: Host a non-service workflow in IIS</span></span>
<span data-ttu-id="d8ff7-103">I flussi di lavoro che non sono servizi flusso di lavoro possono essere ospitati in IIS/WAS.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-103">Workflows that are not workflow services can be hosted under IIS/WAS.</span></span> <span data-ttu-id="d8ff7-104">Tale possibilità si rivela utile quando è necessario ospitare un flusso di lavoro scritto da un altro utente,</span><span class="sxs-lookup"><span data-stu-id="d8ff7-104">This is useful when you need to host a workflow written by somebody else.</span></span> <span data-ttu-id="d8ff7-105">ad esempio se si ospita di nuovo Progettazione flussi di lavoro e si consente agli utenti di creare flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-105">For example, if you rehost the workflow designer and allow users to create their own workflows.</span></span>  <span data-ttu-id="d8ff7-106">L'host di flussi di lavoro non di servizio in IIS fornisce supporto per caratteristiche quali il riciclo dei processi, la chiusura per inattività, il monitoraggio dell'integrità dei processi e l'attivazione basata su messaggi.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-106">Hosting non-service workflows in IIS provides support for features like process recycling, idle shutdown, process health monitoring, and message-based activation.</span></span> <span data-ttu-id="d8ff7-107">I servizi flusso di lavoro ospitati in IIS includono le attività <xref:System.ServiceModel.Activities.Receive> e vengono attivati quando un messaggio viene ricevuto da IIS.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-107">Workflow services hosted in IIS contain <xref:System.ServiceModel.Activities.Receive> activities and are activated when a message is received by IIS.</span></span> <span data-ttu-id="d8ff7-108">Nei flussi di lavoro non di servizio non sono contenute attività di messaggistica e, per impostazione predefinita, non possono essere attivati inviando un messaggio.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-108">Non-service workflows do not contain messaging activities, and by default cannot be activated by sending a message.</span></span>  <span data-ttu-id="d8ff7-109">È necessario derivare una classe dall'oggetto <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> e definire un contratto di servizio contenente le operazioni per creare un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-109">You must derive a class from <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> and define a service contract that contains operations to create an instance of the workflow.</span></span> <span data-ttu-id="d8ff7-110">Questo argomento viene descritta la creazione di un flusso di lavoro semplice, definendo un contratto di servizio, un client può utilizzare per attivare il flusso di lavoro e derivando una classe dal <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> che utilizza il contratto di servizio in ascolto di richieste di creazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-110">This topic will walk you through creating a simple workflow, defining a service contract a client can use to activate the workflow, and deriving a class from <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> which uses the service contract to listen for workflow creating requests.</span></span>  
  
### <a name="create-a-simple-workflow"></a><span data-ttu-id="d8ff7-111">Creare un flusso di lavoro semplice</span><span class="sxs-lookup"><span data-stu-id="d8ff7-111">Create a simple workflow</span></span>  
  
1.  <span data-ttu-id="d8ff7-112">Creare una nuova soluzione [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] vuota chiamata `CreationEndpointTest`.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-112">Create a new [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] empty solution called `CreationEndpointTest`.</span></span>  
  
2.  <span data-ttu-id="d8ff7-113">Aggiungere un nuovo progetto Applicazione di servizi flusso di lavoro WCF denominato `SimpleWorkflow` alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-113">Add a new WCF Workflow Service Application project called `SimpleWorkflow` to the solution.</span></span> <span data-ttu-id="d8ff7-114">Verrà aperta Progettazione flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-114">The workflow designer will open.</span></span>  
  
3.  <span data-ttu-id="d8ff7-115">Eliminare le attività ReceiveRequest e SendResponse.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-115">Delete the ReceiveRequest and SendResponse activities.</span></span> <span data-ttu-id="d8ff7-116">Un flusso di lavoro diventa un servizio flusso di lavoro grazie a queste attività.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-116">These activities are what makes a workflow a workflow service.</span></span> <span data-ttu-id="d8ff7-117">Poiché in questo momento non si intende usare un servizio flusso di lavoro, tali attività non sono più necessarie.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-117">Since we are not working with a workflow service, we no longer need them.</span></span>  
  
4.  <span data-ttu-id="d8ff7-118">Impostare DisplayName per l'attività sequence su "Flusso di lavoro sequenziale".</span><span class="sxs-lookup"><span data-stu-id="d8ff7-118">Set the DisplayName for the sequence activity to "Sequential Workflow".</span></span>  
  
5.  <span data-ttu-id="d8ff7-119">Rinominare Service1.xamlx con Workflow1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-119">Rename Service1.xamlx to Workflow1.xamlx.</span></span>  
  
6.  <span data-ttu-id="d8ff7-120">Fare clic sulla finestra di progettazione all'esterno di attività sequence e impostare le proprietà Name e ConfigurationName su "Workflow1"</span><span class="sxs-lookup"><span data-stu-id="d8ff7-120">Click the designer outside of the sequence activity, and set the Name and ConfigurationName properties to "Workflow1"</span></span>  
  
7.  <span data-ttu-id="d8ff7-121">Trascinare un'attività <xref:System.Activities.Statements.WriteLine> nell'oggetto <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-121">Drag a <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence>.</span></span> <span data-ttu-id="d8ff7-122">Il <xref:System.Activities.Statements.WriteLine> attività, vedere il **primitive** sezione della casella degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-122">The <xref:System.Activities.Statements.WriteLine> activity can be found in the **Primitives** section of the toolbox.</span></span> <span data-ttu-id="d8ff7-123">Impostare il <xref:System.Activities.Statements.WriteLine.Text%2A> proprietà del <xref:System.Activities.Statements.WriteLine> attività "Hello, world".</span><span class="sxs-lookup"><span data-stu-id="d8ff7-123">Set the <xref:System.Activities.Statements.WriteLine.Text%2A> property of the <xref:System.Activities.Statements.WriteLine> activity to "Hello, world".</span></span>  
  
     <span data-ttu-id="d8ff7-124">A questo punto, l'aspetto del flusso di lavoro deve essere simile al diagramma seguente.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-124">The workflow should now look like the following diagram.</span></span>  
  
     <span data-ttu-id="d8ff7-125">![Un semplice flusso di lavoro](../../../../docs/framework/wcf/feature-details/media/simpleworkflow.png "SimpleWorkflow")</span><span class="sxs-lookup"><span data-stu-id="d8ff7-125">![A simple workflow](../../../../docs/framework/wcf/feature-details/media/simpleworkflow.png "SimpleWorkflow")</span></span>  
  
### <a name="create-the-workflow-creation-service-contract"></a><span data-ttu-id="d8ff7-126">Creare un contratto di servizio di creazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="d8ff7-126">Create the workflow creation service contract</span></span>  
  
1.  <span data-ttu-id="d8ff7-127">Aggiungere un nuovo progetto Libreria di classi denominato `Shared` alla soluzione `CreationEndpointTest`.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-127">Add a new class library project called `Shared` to the `CreationEndpointTest` solution.</span></span>  
  
2.  <span data-ttu-id="d8ff7-128">Aggiungere un riferimento a System.ServiceModel.dll, System.Configuration e System.ServiceModel.Activities al progetto `Shared`.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-128">Add a reference to System.ServiceModel.dll, System.Configuration, and System.ServiceModel.Activities to the `Shared` project.</span></span>  
  
3.  <span data-ttu-id="d8ff7-129">Rinominare il file Class1.cs con IWorkflowCreation.cs e il codice seguente in base al file.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-129">Rename the Class1.cs file to IWorkflowCreation.cs and the following code to the file.</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.ServiceModel;  
  
    namespace Shared  
    {  
        //service contract exposed from the endpoint  
        [ServiceContract(Name = "IWorkflowCreation")]  
        public interface IWorkflowCreation  
        {  
            [OperationContract(Name = "Create")]  
            Guid Create(IDictionary<string, object> inputs);  
  
            [OperationContract(Name = "CreateWithInstanceId", IsOneWay = true)]  
            void CreateWithInstanceId(IDictionary<string, object> inputs, Guid instanceId);  
        }  
    }  
    ```  
  
     <span data-ttu-id="d8ff7-130">Questo contratto consente di definire due operazioni che permettono entrambe di creare una nuova istanza del flusso di lavoro non di servizio appena creato.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-130">This contract defines two operations both create a new instance of the non-service workflow you just created.</span></span> <span data-ttu-id="d8ff7-131">Una consente di creare una nuova istanza con un ID istanza generato e l'altra di specificare l'ID istanza per la nuova istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-131">One creates a new instance with a generated instance ID and the other allows you to specify the instance ID for the new workflow instance.</span></span>  <span data-ttu-id="d8ff7-132">Entrambi i metodi consentono di passare parametri alla nuova istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-132">Both methods allow you to pass in parameters to the new workflow instance.</span></span> <span data-ttu-id="d8ff7-133">Questo contratto verrà esposto dal <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> per consentire ai client di creare nuove istanze del flusso di lavoro non di servizio.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-133">This contract will be exposed by the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> to allow clients to create new instances of a non-service workflow.</span></span>  
  
### <a name="derive-a-class-from-workflowhostingendpoint"></a><span data-ttu-id="d8ff7-134">Derivare una classe da WorkflowHostingEndpoint</span><span class="sxs-lookup"><span data-stu-id="d8ff7-134">Derive a class from WorkflowHostingEndpoint</span></span>  
  
1.  <span data-ttu-id="d8ff7-135">Aggiungere una nuova classe denominata `CreationEndpoint` derivato da <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> per il `Shared` progetto.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-135">Add a new class called `CreationEndpoint` derived from <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> to the `Shared` project.</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Diagnostics;  
    using System.Globalization;  
    using System.ServiceModel;  
    using System.ServiceModel.Activities;  
    using System.ServiceModel.Channels;  
  
    namespace Shared  
    {  
        public class CreationEndpoint : WorkflowHostingEndpoint  
        {  
        }  
    }  
    ```  
  
2.  <span data-ttu-id="d8ff7-136">Aggiungere una variabile locale statica <xref:System.Uri> denominata `defaultBaseUri` alla classe `CreationEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-136">Add a local static <xref:System.Uri> variable called `defaultBaseUri` to the `CreationEndpoint` class.</span></span>  
  
    ```  
    public class CreationEndpoint : WorkflowHostingEndpoint  
    {  
        static Uri defaultBaseUri;  
    }  
    ```  
  
3.  <span data-ttu-id="d8ff7-137">Aggiungere il costruttore seguente alla classe `CreationEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-137">Add the following constructor to the `CreationEndpoint` class.</span></span> <span data-ttu-id="d8ff7-138">Si noti che il contratto di servizio `IWorkflowCreation` viene specificato nella chiamata al costruttore base.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-138">Notice we specify the `IWorkflowCreation` service contract in the call to the base constructor.</span></span>  
  
    ```  
    public CreationEndpoint(Binding binding, EndpointAddress address)  
       : base(typeof(IWorkflowCreation), binding, address)  
       {  
       }  
    ```  
  
4.  <span data-ttu-id="d8ff7-139">Aggiungere il seguente costruttore predefinito alla classe `CreationEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-139">Add the following default constructor to the `CreationEndpoint` class.</span></span>  
  
    ```  
    public CreationEndpoint()  
       : this(GetDefaultBinding(),  
       new EndpointAddress(new Uri(DefaultBaseUri, new Uri(Guid.NewGuid().ToString(), UriKind.Relative))))  
       {  
       }  
    ```  
  
5.  <span data-ttu-id="d8ff7-140">Aggiungere una proprietà statica `DefaultBaseUri` alla classe `CreationEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-140">Add a static `DefaultBaseUri` property to the `CreationEndpoint` class.</span></span> <span data-ttu-id="d8ff7-141">Questa proprietà sarà usata per includere un URI di base predefinito, se non ne viene fornito uno.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-141">This property will be used to hold a default base URI if one is not provided.</span></span>  
  
    ```  
    static Uri DefaultBaseUri  
    {  
       get  
       {  
          if (defaultBaseUri == null)  
          {  
             defaultBaseUri = new Uri(string.Format(CultureInfo.InvariantCulture, "net.pipe://localhost/workflowCreationEndpoint/{0}/{1}",  
                Process.GetCurrentProcess().Id,  
                AppDomain.CurrentDomain.Id));  
          }  
          return defaultBaseUri;  
       }  
     }  
    ```  
  
6.  <span data-ttu-id="d8ff7-142">Creare il metodo seguente per ottenere il binding predefinito da usare per l'endpoint di creazione.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-142">Create the following method to get the default binding to use for the creation endpoint.</span></span>  
  
    ```  
    //defaults to NetNamedPipeBinding  
    public static Binding GetDefaultBinding()  
    {  
       return new NetNamedPipeBinding(NetNamedPipeSecurityMode.None) { TransactionFlow = true };  
    }  
    ```  
  
7.  <span data-ttu-id="d8ff7-143">Eseguire l'override del metodo <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetInstanceId%2A> per restituire l'ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-143">Override the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetInstanceId%2A> method to return the workflow instance ID.</span></span> <span data-ttu-id="d8ff7-144">Se il `Action` intestazione termina con "Create" restituisce un GUID vuoto, se il `Action` intestazione termina con "createwithinstanceid, viene" restituito il GUID passato al metodo.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-144">If the `Action` header ends with "Create" return an empty GUID, if the `Action` header ends with "CreateWithInstanceId" return the GUID passed into the method.</span></span> <span data-ttu-id="d8ff7-145">In caso contrario, viene generata un'eccezione <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-145">Otherwise, throw an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="d8ff7-146">Queste intestazioni `Action` corrispondono alle due operazioni definite nel contratto di servizio `IWorkflowCreation`.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-146">These `Action` headers correspond to the two operations defined in the `IWorkflowCreation` service contract.</span></span>  
  
    ```  
    protected override Guid OnGetInstanceId(object[] inputs, OperationContext operationContext)  
    {  
       //Create was called by client  
       if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create"))  
       {  
          return Guid.Empty;  
       }  
       //CreateWithInstanceId was called by client  
       else if (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId"))  
       {  
          return (Guid)inputs[1];  
       }  
       else  
       {  
          throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
       }  
    }  
    ```  
  
8.  <span data-ttu-id="d8ff7-147">Eseguire l'override del metodo <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetCreationContext%2A> per creare un oggetto <xref:System.ServiceModel.Activities.WorkflowCreationContext>, aggiungere qualsiasi argomento per il flusso di lavoro, inviare l'ID istanza al client e restituire l'oggetto <xref:System.ServiceModel.Activities.WorkflowCreationContext>.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-147">Override the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint.OnGetCreationContext%2A> method to create a <xref:System.ServiceModel.Activities.WorkflowCreationContext> and add any arguments for the workflow, send the instance ID to the client, and then return the <xref:System.ServiceModel.Activities.WorkflowCreationContext>.</span></span>  
  
    ```  
    protected override WorkflowCreationContext OnGetCreationContext(object[] inputs, OperationContext operationContext, Guid instanceId, WorkflowHostingResponseContext responseContext)  
    {  
       WorkflowCreationContext creationContext = new WorkflowCreationContext();  
       if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create") || (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId")))  
       {  
          Dictionary<string, object> arguments = (Dictionary<string, object>)inputs[0];  
          if (arguments != null && arguments.Count > 0)  
          {  
             foreach (KeyValuePair<string, object> pair in arguments)  
             {  
                //arguments to pass to the workflow  
                creationContext.WorkflowArguments.Add(pair.Key, pair.Value);  
             }  
          }  
          //reply to client with instanceId  
          responseContext.SendResponse(instanceId, null);  
       }  
       else  
       {  
          throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
       }  
       return creationContext;  
    }  
    ```  
  
### <a name="create-a-standard-endpoint-element-to-allow-you-to-configure-the-workflowcreationendpoint"></a><span data-ttu-id="d8ff7-148">Creare un elemento endpoint standard per consentire la configurazione di WorkflowCreationEndpoint</span><span class="sxs-lookup"><span data-stu-id="d8ff7-148">Create a standard endpoint element to allow you to configure the WorkflowCreationEndpoint</span></span>  
  
1.  <span data-ttu-id="d8ff7-149">Aggiungere un riferimento a Shared nel progetto `CreationEndpoint`</span><span class="sxs-lookup"><span data-stu-id="d8ff7-149">Add a reference to Shared in the `CreationEndpoint` project</span></span>  
  
2.  <span data-ttu-id="d8ff7-150">Aggiungere una nuova classe denominata `CreationEndpointElement`, derivata dall'oggetto <xref:System.ServiceModel.Configuration.StandardEndpointElement> al progetto `CreationEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-150">Add a new class called `CreationEndpointElement`, derived from <xref:System.ServiceModel.Configuration.StandardEndpointElement> to the `CreationEndpoint` project.</span></span> <span data-ttu-id="d8ff7-151">Questa classe rappresenterà un oggetto `CreationEndpoint` in un file web.config.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-151">This class will represent a `CreationEndpoint` in a web.config file.</span></span>  
  
    ```  
    using System;  
    using System.Configuration;  
    using System.ServiceModel.Activities;  
    using System.ServiceModel.Configuration;  
    using System.ServiceModel.Description;  
    using Shared;  
  
    namespace CreationEndpointTest  
    {  
        //config element for CreationEndpoint  
        public class CreationEndpointElement : StandardEndpointElement  
        {  
       }  
    ```  
  
3.  <span data-ttu-id="d8ff7-152">Aggiungere una proprietà denominata `EndpointType` per restituire il tipo di endpoint.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-152">Add a property called `EndpointType` to return the type of the endpoint.</span></span>  
  
    ```  
    protected override Type EndpointType  
    {  
       get { return typeof(CreationEndpoint); }  
    }  
    ```  
  
4.  <span data-ttu-id="d8ff7-153">Eseguire l'override del metodo <xref:System.ServiceModel.Configuration.StandardEndpointElement.CreateServiceEndpoint%2A> e restituire un nuovo oggetto `CreationEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-153">Override the <xref:System.ServiceModel.Configuration.StandardEndpointElement.CreateServiceEndpoint%2A> method and return a new `CreationEndpoint`.</span></span>  
  
    ```  
    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contractDescription)  
    {  
       return new CreationEndpoint();  
    }  
    ```  
  
5.  <span data-ttu-id="d8ff7-154">Eseguire l'overload dei metodi <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnApplyConfiguration%2A>, <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnApplyConfiguration%2A>, <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnInitializeAndValidate%2A> e <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnInitializeAndValidate%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-154">Overload the <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnApplyConfiguration%2A>, <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnApplyConfiguration%2A>, <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnInitializeAndValidate%2A>, and <xref:System.ServiceModel.Configuration.StandardEndpointElement.OnInitializeAndValidate%2A> methods.</span></span> <span data-ttu-id="d8ff7-155">Questi metodi devono solo essere definiti; non è necessario aggiungervi alcun codice.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-155">These methods just need to be defined, you do not need to add any code to them.</span></span>  
  
    ```  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)  
    {  
    }  
  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)  
    {  
    }  
  
    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)  
    {  
    }  
  
    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)  
    {  
    }  
    ```  
  
6.  <span data-ttu-id="d8ff7-156">Aggiungere la classe di raccolta per `CreationEndpoint` al file CreationEndpointElement.cs nel progetto `CreationEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-156">Add the collection class for `CreationEndpoint` to the CreationEndpointElement.cs file in the `CreationEndpoint` project.</span></span> <span data-ttu-id="d8ff7-157">Questa classe viene usata dalla configurazione per mantenere un numero di istanze `CreationEndpoint` in un file web.config.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-157">This class is used by configuration to hold a number of `CreationEndpoint` instances in a web.config file.</span></span>  
  
    ```  
    public class CreationEndpointCollection : StandardEndpointCollectionElement<CreationEndpoint, CreationEndpointElement>  
    {  
    }  
    ```  
  
7.  <span data-ttu-id="d8ff7-158">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-158">Build the solution.</span></span>  
  
### <a name="host-the-workflow-in-iis"></a><span data-ttu-id="d8ff7-159">Ospitare il flusso di lavoro in IIS</span><span class="sxs-lookup"><span data-stu-id="d8ff7-159">Host the workflow in IIS</span></span>  
  
1.  <span data-ttu-id="d8ff7-160">Creare una nuova applicazione denominata `MyCreationEndpoint` in IIS.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-160">Create a new application called `MyCreationEndpoint` in IIS.</span></span>  
  
2.  <span data-ttu-id="d8ff7-161">Copiare il file workflow1.xaml generato da Progettazione flussi di lavoro nella directory dell'applicazione e rinominarlo workflow1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-161">Copy the workflow1.xaml file generated by the workflow designer to the application directory and rename it to workflow1.xamlx.</span></span>  
  
3.  <span data-ttu-id="d8ff7-162">Copiare i file shared.dll e CreationEndpoint.dll nella directory bin dell'applicazione; se non è presente è necessario crearla.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-162">Copy the shared.dll and CreationEndpoint.dll files to the application’s bin directory (create the bin directory if it is not present).</span></span>  
  
4.  <span data-ttu-id="d8ff7-163">Sostituire il contenuto del file Web.config nel progetto `CreationEndpoint` con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-163">Replace the contents of the Web.config file in the `CreationEndpoint` project with the following code.</span></span>  
  
    ```xaml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.web>  
        <compilation debug="true" targetFramework="4.0" />  
      </system.web>   
    </configuration>  
    ```  
  
5.  <span data-ttu-id="d8ff7-164">Dopo l'elemento `<system.web>`, registrare `CreationEndpoint` aggiungendo il codice di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-164">After the `<system.web>` element, register `CreationEndpoint` by adding the following configuration code.</span></span>  
  
    ```xml  
    <system.serviceModel>  
        <!--register CreationEndpoint-->  
        <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
        <extensions>  
          <endpointExtensions>  
            <add name="creationEndpoint" type="CreationEndpointTest.CreationEndpointCollection, CreationEndpoint, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
          </endpointExtensions>  
        </extensions>  
    </system.serviceModel>  
    ```  
  
     <span data-ttu-id="d8ff7-165">Questa operazione consente di registrare la classe `CreationEndpointCollection` affinché sia possibile configurare un oggetto `CreationEndpoint` in un file web.config.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-165">This registers the `CreationEndpointCollection` class so you can configure a `CreationEndpoint` in a web.config file.</span></span>  
  
6.  <span data-ttu-id="d8ff7-166">Aggiungere un `<service>` elemento (dopo il \</extensions > tag) con un `CreationEndpoint` che sarà in ascolto dei messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-166">Add a `<service>` element (after the \</extensions> tag) with a `CreationEndpoint` which will listen for incoming messages.</span></span>  
  
    ```xml  
    <services>  
          <!-- add endpoint to service-->  
          <service name="Workflow1" behaviorConfiguration="basicConfig" >  
            <endpoint kind="creationEndpoint" binding="basicHttpBinding" address=""/>  
          </service>  
        </services>  
    ```  
  
7.  <span data-ttu-id="d8ff7-167">Aggiungere un \<comportamenti > elemento (dopo il  \< /services > tag) per abilitare i metadati del servizio.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-167">Add a \<behaviors> element (after the \</services> tag) to enable service metadata.</span></span>  
  
    ```xml  
    <behaviors>  
          <serviceBehaviors>  
            <behavior name="basicConfig">  
              <serviceMetadata httpGetEnabled="true" />  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
    ```  
  
8.  <span data-ttu-id="d8ff7-168">Copiare il file web.config nella directory dell'applicazione IIS.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-168">Copy the web.config to your IIS application directory.</span></span>  
  
9. <span data-ttu-id="d8ff7-169">Verificare se l'endpoint di creazione funziona correttamente aprendo Internet Explorer e immettendo l'indirizzo http://localhost/MyCreationEndpoint/Workflow1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-169">Test to see if the creation endpoint is working by starting Internet Explorer and browsing to http://localhost/MyCreationEndpoint/Workflow1.xamlx.</span></span> <span data-ttu-id="d8ff7-170">In Internet Explorer deve essere visualizzata la schermata seguente:</span><span class="sxs-lookup"><span data-stu-id="d8ff7-170">Internet Explorer should display the following screen:</span></span>  
  
     <span data-ttu-id="d8ff7-171">![Test del servizio](../../../../docs/framework/wcf/feature-details/media/testservice.gif "TestService")</span><span class="sxs-lookup"><span data-stu-id="d8ff7-171">![Testing the service](../../../../docs/framework/wcf/feature-details/media/testservice.gif "TestService")</span></span>  
  
### <a name="create-a-client-that-will-call-the-creationendpoint"></a><span data-ttu-id="d8ff7-172">Creare un client che consentirà di chiamare CreationEndpoint.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-172">Create a client that will call the CreationEndpoint.</span></span>  
  
1.  <span data-ttu-id="d8ff7-173">Aggiungere una nuova applicazione console alla soluzione `CreationEndpointTest`.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-173">Add a new Console application to the `CreationEndpointTest` solution.</span></span>  
  
2.  <span data-ttu-id="d8ff7-174">Aggiungere riferimenti a System.ServiceModel.dll e System.ServiceModel.Activities e il progetto `Shared`.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-174">Add references to System.ServiceModel.dll, System.ServiceModel.Activities, and the `Shared` project.</span></span>  
  
3.  <span data-ttu-id="d8ff7-175">Nel `Main` metodo crea un <xref:System.ServiceModel.ChannelFactory%601> di tipo `IWorkflowCreation` e chiamare <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-175">In the `Main` method create a <xref:System.ServiceModel.ChannelFactory%601> of type `IWorkflowCreation` and call <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>.</span></span> <span data-ttu-id="d8ff7-176">Questa operazione consentirà la restituzione di un proxy.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-176">This will return a proxy.</span></span> <span data-ttu-id="d8ff7-177">Successivamente è possibile chiamare `Create` su tale proxy per creare l'istanza del flusso di lavoro ospitata in IIS:</span><span class="sxs-lookup"><span data-stu-id="d8ff7-177">You can then call `Create` on that proxy to create the workflow instance hosted under IIS:</span></span>  
  
    ```  
    using System.Text;  
    using Shared;  
    using System.ServiceModel;  
  
    namespace CreationEndpointClient  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                try  
                {  
                    //client using BasicHttpBinding  
                    IWorkflowCreation client = new ChannelFactory<IWorkflowCreation>(new BasicHttpBinding(), new EndpointAddress("http://localhost/CreationEndpoint/Workflow1.xamlx")).CreateChannel();  
  
                    Console.WriteLine("Workflow Instance created using CreationEndpoint added in config. Instance Id: {0}", client.Create(null));  
                    Console.WriteLine("Press return to exit ...");  
                    Console.ReadLine();  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine(ex);  
                    Console.ReadLine();  
                }  
            }  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="d8ff7-178">Eseguire CreationEndpointClient.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-178">Run the CreationEndpointClient.</span></span> <span data-ttu-id="d8ff7-179">L'output dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d8ff7-179">The output should look like the following:</span></span>  
  
    ```Output  
    Workflow Instance created using CreationEndpoint added in config. Instance Id: 0875dac0-2b8b-473e-b3cc-abcb235e9693Press return to exit ...  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="d8ff7-180">L'output del flusso di lavoro non sarà visualizzato poiché è in esecuzione in IIS, il quale non dispone di alcun output di console.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-180">You will not see the output of the workflow because it is running under IIS which has no console output.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8ff7-181">Esempio</span><span class="sxs-lookup"><span data-stu-id="d8ff7-181">Example</span></span>  
 <span data-ttu-id="d8ff7-182">Di seguito è riportato il codice completo per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-182">The following is the complete code for this sample.</span></span>  
  
```xaml  
<!-— workflow1.xamlx -->  
<WorkflowService mc:Ignorable="sap"   
                 ConfigurationName="Workflow1"   
                 sap:VirtualizedContainerService.HintSize="263,230"   
                 Name="Workflow1"   
                 mva:VisualBasic.Settings="Assembly references and imported namespaces serialized as XML namespaces"   
                 xmlns="http://schemas.microsoft.com/netfx/2009/xaml/servicemodel"   
                 xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"   
                 xmlns:mv="clr-namespace:Microsoft.VisualBasic;assembly=System"   
                 xmlns:mva="clr-namespace:Microsoft.VisualBasic.Activities;assembly=System.Activities"   
                 xmlns:p="http://schemas.microsoft.com/netfx/2009/xaml/activities"   
                 xmlns:s="clr-namespace:System;assembly=mscorlib"   
                 xmlns:s1="clr-namespace:System;assembly=System"   
                 xmlns:s2="clr-namespace:System;assembly=System.Xml"   
                 xmlns:s3="clr-namespace:System;assembly=System.Core"   
                 xmlns:sad="clr-namespace:System.Activities.Debugger;assembly=System.Activities"   
                 xmlns:sap="http://schemas.microsoft.com/netfx/2009/xaml/activities/presentation"   
                 xmlns:scg="clr-namespace:System.Collections.Generic;assembly=System"   
                 xmlns:scg1="clr-namespace:System.Collections.Generic;assembly=System.ServiceModel"   
                 xmlns:scg2="clr-namespace:System.Collections.Generic;assembly=System.Core"   
                 xmlns:scg3="clr-namespace:System.Collections.Generic;assembly=mscorlib"   
                 xmlns:sd="clr-namespace:System.Data;assembly=System.Data"   
                 xmlns:sl="clr-namespace:System.Linq;assembly=System.Core"   
                 xmlns:st="clr-namespace:System.Text;assembly=mscorlib"   
                 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <p:Sequence DisplayName="Sequential Service"   
              sad:XamlDebuggerXmlReader.FileName="c:\projects\CreationEndpointTest\CreationEndpoint\Service1.xamlx"   
              sap:VirtualizedContainerService.HintSize="233,200"   
              mva:VisualBasic.Settings="Assembly references and imported namespaces serialized as XML namespaces">  
    <p:Sequence.Variables>  
      <p:Variable x:TypeArguments="CorrelationHandle" Name="handle" />  
      <p:Variable x:TypeArguments="x:Int32" Name="data" />  
    </p:Sequence.Variables>  
    <sap:WorkflowViewStateService.ViewState>  
      <scg3:Dictionary x:TypeArguments="x:String, x:Object">  
        <x:Boolean x:Key="IsExpanded">True</x:Boolean>  
      </scg3:Dictionary>  
    </sap:WorkflowViewStateService.ViewState>  
    <p:WriteLine sap:VirtualizedContainerService.HintSize="211,61" Text="Hello, world" />  
  </p:Sequence>  
</WorkflowService>  
```  
  
```csharp  
// CreationEndpointElement.cs  
using System;  
using System.Configuration;  
using System.ServiceModel.Activities;  
using System.ServiceModel.Configuration;  
using System.ServiceModel.Description;  
using Shared;  
  
namespace CreationEndpointTest  
{  
    //config element for CreationEndpoint  
    public class CreationEndpointElement : StandardEndpointElement  
    {  
        protected override Type EndpointType  
        {  
            get { return typeof(CreationEndpoint); }  
        }  
  
        protected override ConfigurationPropertyCollection Properties  
        {  
            get  
            {  
                ConfigurationPropertyCollection properties = base.Properties;  
                properties.Add(new ConfigurationProperty("name", typeof(String), null, ConfigurationPropertyOptions.IsRequired));  
                return properties;  
            }  
        }  
  
        protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contractDescription)  
        {  
            return new CreationEndpoint();  
        }  
  
        protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)  
        {  
        }  
  
        protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)  
        {  
        }  
  
        protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)  
        {  
        }  
  
        protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)  
        {  
        }  
    }  
  
    public class CreationEndpointCollection : StandardEndpointCollectionElement<CreationEndpoint, CreationEndpointElement>  
    {  
    }  
}  
```  
  
```xml  
<!-- web.config -->  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.web>  
    <compilation debug="true" targetFramework="4.0" />  
  </system.web>  
  <system.serviceModel>  
    <!--register CreationEndpoint-->  
    <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
    <extensions>  
      <endpointExtensions>  
        <add name="creationEndpoint" type="CreationEndpointTest.CreationEndpointCollection, Shared, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </endpointExtensions>  
    </extensions>  
    <services>  
      <!-- add endpoint to service-->  
      <service name="Workflow1" behaviorConfiguration="basicConfig" >  
        <endpoint kind="creationEndpoint" binding="basicHttpBinding" address=""/>  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="basicConfig">  
          <serviceMetadata httpGetEnabled="true" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
```csharp  
// IWorkflowCreation.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel;  
  
namespace Shared  
{  
    //service contract exposed from the endpoint  
    [ServiceContract(Name = "IWorkflowCreation")]  
    public interface IWorkflowCreation  
    {  
        [OperationContract(Name = "Create")]  
        Guid Create(IDictionary<string, object> inputs);  
  
        [OperationContract(Name = "CreateWithInstanceId", IsOneWay = true)]  
        void CreateWithInstanceId(IDictionary<string, object> inputs, Guid instanceId);  
    }  
}  
```  
  
```csharp  
// CreationEndpoint.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel.Activities;  
using System.ServiceModel.Channels;  
using System.ServiceModel;  
using System.Globalization;  
using System.Diagnostics;  
  
namespace Shared  
{  
    public class CreationEndpoint : WorkflowHostingEndpoint  
    {  
        static Uri defaultBaseUri;  
  
        public CreationEndpoint(Binding binding, EndpointAddress address)  
            : base(typeof(IWorkflowCreation), binding, address) { }  
  
        public CreationEndpoint()  
            : this(GetDefaultBinding(),  
                new EndpointAddress(new Uri(DefaultBaseUri, new Uri(Guid.NewGuid().ToString(), UriKind.Relative)))) { }  
  
        static Uri DefaultBaseUri  
        {  
            get  
            {  
                if (defaultBaseUri == null)  
                {  
                    defaultBaseUri = new Uri(string.Format(CultureInfo.InvariantCulture, "net.pipe://localhost/workflowCreationEndpoint/{0}/{1}",  
                        Process.GetCurrentProcess().Id,  
                        AppDomain.CurrentDomain.Id));  
                }  
                return defaultBaseUri;  
            }  
        }  
  
        //defaults to NetNamedPipeBinding  
        public static Binding GetDefaultBinding()  
        {  
            return new NetNamedPipeBinding(NetNamedPipeSecurityMode.None) { TransactionFlow = true };  
        }  
  
        protected override Guid OnGetInstanceId(object[] inputs, OperationContext operationContext)  
        {  
            //Create was called by client  
            if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create"))  
            {  
                return Guid.Empty;  
            }  
  
            //CreateWithInstanceId was called by client  
            else if (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId"))  
            {  
                return (Guid)inputs[1];  
            }  
            else  
            {  
                throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
            }  
        }  
  
        protected override WorkflowCreationContext OnGetCreationContext(object[] inputs, OperationContext operationContext, Guid instanceId, WorkflowHostingResponseContext responseContext)  
        {  
            WorkflowCreationContext creationContext = new WorkflowCreationContext();  
            if (operationContext.IncomingMessageHeaders.Action.EndsWith("Create"))  
            {  
                Dictionary<string, object> arguments = (Dictionary<string, object>)inputs[0];  
                if (arguments != null && arguments.Count > 0)  
                {  
                    foreach (KeyValuePair<string, object> pair in arguments)  
                    {  
                        //arguments to pass to the workflow  
                        creationContext.WorkflowArguments.Add(pair.Key, pair.Value);  
                    }  
                }  
                //reply to client with instanceId  
                responseContext.SendResponse(instanceId, null);  
            }  
            else if (operationContext.IncomingMessageHeaders.Action.EndsWith("CreateWithInstanceId"))  
            {  
                Dictionary<string, object> arguments = (Dictionary<string, object>)inputs[0];  
                if (arguments != null && arguments.Count > 0)  
                {  
                    foreach (KeyValuePair<string, object> pair in arguments)  
                    {  
                        //arguments to pass to workflow  
                        creationContext.WorkflowArguments.Add(pair.Key, pair.Value);  
                    }  
                }  
            }  
            else  
            {  
                throw new InvalidOperationException("Invalid Action: " + operationContext.IncomingMessageHeaders.Action);  
            }  
            return creationContext;  
        }  
    }  
}  
```  
  
```csharp  
// CreationEndpointClient.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using Shared;  
using System.ServiceModel;  
  
namespace CreationClient  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            try  
            {  
                //client using BasicHttpBinding  
                IWorkflowCreation client = new ChannelFactory<IWorkflowCreation>(new BasicHttpBinding(), new EndpointAddress("http://localhost/MyCreationEndpoint/Workflow1.xamlx")).CreateChannel();  
  
                Console.WriteLine("Workflow Instance created using CreationEndpoint added in config. Instance Id: {0}", client.Create(null));  
                Console.WriteLine("Press return to exit ...");  
                Console.ReadLine();  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine(ex);  
                Console.ReadLine();  
            }  
  
        }  
    }  
  
}  
```  
  
 <span data-ttu-id="d8ff7-183">Questo esempio può sembrare un elemento di confusione poiché non si implementa mai un servizio che consente di implementare `IWorkflowCreation`.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-183">This example may seem confusing because you never implement a service that implements `IWorkflowCreation`.</span></span> <span data-ttu-id="d8ff7-184">Il motivo è rappresentato dal fatto che l'implementazione viene effettuata da `CreationEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="d8ff7-184">This is because the `CreationEndpoint` does this for you.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8ff7-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8ff7-185">See Also</span></span>  
 [<span data-ttu-id="d8ff7-186">Servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="d8ff7-186">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="d8ff7-187">Hosting in Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="d8ff7-187">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [<span data-ttu-id="d8ff7-188">Hosting di procedure consigliate di Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="d8ff7-188">Internet Information Services Hosting Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [<span data-ttu-id="d8ff7-189">Istruzioni di Hosting Internet Information Service</span><span class="sxs-lookup"><span data-stu-id="d8ff7-189">Internet Information Service Hosting Instructions</span></span>](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)  
 [<span data-ttu-id="d8ff7-190">Architettura del flusso di lavoro di Windows</span><span class="sxs-lookup"><span data-stu-id="d8ff7-190">Windows Workflow Architecture</span></span>](../../../../docs/framework/windows-workflow-foundation/architecture.md)  
 [<span data-ttu-id="d8ff7-191">Segnalibro di ripresa WorkflowHostingEndpoint</span><span class="sxs-lookup"><span data-stu-id="d8ff7-191">WorkflowHostingEndpoint Resume Bookmark</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/workflowhostingendpoint-resume-bookmark.md)  
 [<span data-ttu-id="d8ff7-192">Riallocazione di Progettazione flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="d8ff7-192">Rehosting the Workflow Designer</span></span>](../../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [<span data-ttu-id="d8ff7-193">Panoramica del flusso di lavoro di Windows</span><span class="sxs-lookup"><span data-stu-id="d8ff7-193">Windows Workflow Overview</span></span>](../../../../docs/framework/windows-workflow-foundation/overview.md)

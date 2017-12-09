---
title: Aggiornamento dinamico
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8b6ef19b-9691-4b4b-824c-3c651a9db96e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0bd320b9875f7ed2d5acb124feb4b7d3bb82d62e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="dynamic-update"></a><span data-ttu-id="2ab11-102">Aggiornamento dinamico</span><span class="sxs-lookup"><span data-stu-id="2ab11-102">Dynamic Update</span></span>
<span data-ttu-id="2ab11-103">L'aggiornamento dinamico fornisce agli sviluppatori di applicazioni del flusso di lavoro un meccanismo per aggiornare la definizione del flusso di lavoro di un'istanza persistente del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2ab11-103">Dynamic update provides a mechanism for workflow application developers to update the workflow definition of a persisted workflow instance.</span></span> <span data-ttu-id="2ab11-104">Può servire a implementare una correzione di bug, nuovi requisiti o per implementare modifiche impreviste.</span><span class="sxs-lookup"><span data-stu-id="2ab11-104">This can be to implement a bug fix, new requirements, or to accommodate unexpected changes.</span></span> <span data-ttu-id="2ab11-105">In questo argomento viene fornita una panoramica sulla funzionalità di aggiornamento dinamico introdotta in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ab11-105">This topic provides an overview of the dynamic update functionality introduced in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span>  
  
## <a name="dynamic-update"></a><span data-ttu-id="2ab11-106">Aggiornamento dinamico</span><span class="sxs-lookup"><span data-stu-id="2ab11-106">Dynamic Update</span></span>  
 <span data-ttu-id="2ab11-107">Per applicare gli aggiornamenti dinamici a un'istanza persistente del flusso di lavoro, viene creato un oggetto <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> contenente le istruzioni per il runtime che spiegano come modificare tale istanza in modo da riflettere le modifiche desiderate.</span><span class="sxs-lookup"><span data-stu-id="2ab11-107">To apply dynamic updates to a persisted workflow instance, a <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> is created that contains instructions for the runtime that describe how to modify the persisted workflow instance to reflect the desired changes.</span></span> <span data-ttu-id="2ab11-108">Una volta creata, la mappa di aggiornamento viene applicata alle istanze persistenti del flusso di lavoro desiderate.</span><span class="sxs-lookup"><span data-stu-id="2ab11-108">Once the update map is created, it is applied to the desired persisted workflow instances.</span></span> <span data-ttu-id="2ab11-109">Dopo che è stato applicato l'aggiornamento dinamico, le istanze di flusso di lavoro possono essere riprese usando la nuova definizione aggiornata del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2ab11-109">Once the dynamic update is applied, the workflow instance may be resumed using the new updated workflow definition.</span></span> <span data-ttu-id="2ab11-110">Per la creazione e l'applicazione di una mappa di aggiornamento sono richiesti quattro passaggi.</span><span class="sxs-lookup"><span data-stu-id="2ab11-110">There are four steps required to create and apply an update map.</span></span>  
  
1.  [<span data-ttu-id="2ab11-111">Preparare la definizione del flusso di lavoro per l'aggiornamento dinamico</span><span class="sxs-lookup"><span data-stu-id="2ab11-111">Prepare the workflow definition for dynamic update</span></span>](../../../docs/framework/windows-workflow-foundation/dynamic-update.md#Prepare)  
  
2.  [<span data-ttu-id="2ab11-112">Aggiornare la definizione del flusso di lavoro in modo da riflettere le modifiche desiderate</span><span class="sxs-lookup"><span data-stu-id="2ab11-112">Update the workflow definition to reflect the desired changes</span></span>](../../../docs/framework/windows-workflow-foundation/dynamic-update.md#Update)  
  
3.  [<span data-ttu-id="2ab11-113">Creare la mappa di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="2ab11-113">Create the update map</span></span>](../../../docs/framework/windows-workflow-foundation/dynamic-update.md#Create)  
  
4.  [<span data-ttu-id="2ab11-114">Applicare la mappa di aggiornamento alle istanze del flusso di lavoro persistente desiderato</span><span class="sxs-lookup"><span data-stu-id="2ab11-114">Apply the update map to the desired persisted workflow instances</span></span>](../../../docs/framework/windows-workflow-foundation/dynamic-update.md#Apply)  
  
> [!NOTE]
>  <span data-ttu-id="2ab11-115">Si noti che i passaggi da 1 a 3, relativi alla creazione della mappa di aggiornamento, possono essere eseguiti indipendentemente dal fatto che l'aggiornamento venga poi applicato o meno.</span><span class="sxs-lookup"><span data-stu-id="2ab11-115">Note that steps 1 through 3, which cover the creation of the update map, may be performed independently of applying the update.</span></span> <span data-ttu-id="2ab11-116">In uno scenario comune, lo sviluppatore del flusso di lavoro crea la mappa di aggiornamento offline e un amministratore applica l'aggiornamento in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="2ab11-116">A common scenario that that the workflow developer will create the update map offline, and then an administrator will apply the update at a later time.</span></span>  
  
 <span data-ttu-id="2ab11-117">In questo argomento viene fornita una panoramica sul processo di aggiornamento dinamico per l'aggiunta di una nuova attività a un'istanza persistente di un flusso di lavoro XAML compilato.</span><span class="sxs-lookup"><span data-stu-id="2ab11-117">This topic provides an overview of the dynamic update process of adding a new activity to a persisted instance of a compiled Xaml workflow.</span></span>  
  
###  <a name="Prepare"></a><span data-ttu-id="2ab11-118">Preparare la definizione del flusso di lavoro per l'aggiornamento dinamico</span><span class="sxs-lookup"><span data-stu-id="2ab11-118">Prepare the workflow definition for dynamic update</span></span>  
 <span data-ttu-id="2ab11-119">Il primo passaggio nel processo di aggiornamento dinamico consiste nel preparare all'aggiornamento la definizione del flusso di lavoro desiderata.</span><span class="sxs-lookup"><span data-stu-id="2ab11-119">The first step in the dynamic update process is to prepare the desired workflow definition for update.</span></span> <span data-ttu-id="2ab11-120">Questa operazione viene eseguita chiamando il metodo <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> e passando la definizione del flusso di lavoro per la modifica.</span><span class="sxs-lookup"><span data-stu-id="2ab11-120">This is done by calling the <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> method and passing in the workflow definition to modify.</span></span> <span data-ttu-id="2ab11-121">Questo metodo convalida e successivamente analizza l'albero del flusso di lavoro per identificare tutti gli oggetti, quali le variabili e le attività pubbliche che devono essere contrassegnate in modo da poter essere confrontate in un secondo momento con la definizione del flusso di lavoro modificata.</span><span class="sxs-lookup"><span data-stu-id="2ab11-121">This method validates and then walks the workflow tree to identify all of the objects such as public activities and variables that need to be tagged so they can be compared later with the modified workflow definition.</span></span> <span data-ttu-id="2ab11-122">Al termine, l'albero del flusso di lavoro viene duplicato e collegato alla definizione del flusso di lavoro originale.</span><span class="sxs-lookup"><span data-stu-id="2ab11-122">When this is complete, the workflow tree is cloned and attached to the original workflow definition.</span></span> <span data-ttu-id="2ab11-123">Quando viene creata la mappa di aggiornamento, la versione aggiornata della definizione del flusso di lavoro viene confrontata con la definizione del flusso di lavoro originale. Sulla base delle differenze viene generata la mappa di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="2ab11-123">When the update map is created, the updated version of the workflow definition is compared with the original workflow definition and the update map is generated based on the differences.</span></span>  
  
 <span data-ttu-id="2ab11-124">Ai fini della preparazione per l'aggiornamento dinamico, un flusso di lavoro XAML può essere caricato in un oggetto <xref:System.Activities.ActivityBuilder>. L'oggetto <xref:System.Activities.ActivityBuilder> verrà quindi passato a <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2ab11-124">To prepare a Xaml workflow for dynamic update it may be loaded into an <xref:System.Activities.ActivityBuilder>, and then the <xref:System.Activities.ActivityBuilder> is passed into <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ab11-125">Per ulteriori informazioni sull'utilizzo di flussi di lavoro serializzati e <xref:System.Activities.ActivityBuilder>, vedere [la serializzazione di flussi di lavoro e attività da e verso XAML](../../../docs/framework/windows-workflow-foundation/serializing-workflows-and-activities-to-and-from-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="2ab11-125">For more information about working with serialized workflows and <xref:System.Activities.ActivityBuilder>, see [Serializing Workflows and Activities to and from XAML](../../../docs/framework/windows-workflow-foundation/serializing-workflows-and-activities-to-and-from-xaml.md).</span></span>  
  
 <span data-ttu-id="2ab11-126">Nell'esempio riportato di seguito, una definizione di `MortgageWorkflow` (costituita da un oggetto <xref:System.Activities.Statements.Sequence> con varie attività figlio) viene caricata in un oggetto <xref:System.Activities.ActivityBuilder> e successivamente preparata per l'aggiornamento dinamico.</span><span class="sxs-lookup"><span data-stu-id="2ab11-126">In the following example, a `MortgageWorkflow` definition (that consists of a <xref:System.Activities.Statements.Sequence> with several child activities) is loaded into an <xref:System.Activities.ActivityBuilder>, and then prepared for dynamic update.</span></span> <span data-ttu-id="2ab11-127">Una volta completato il metodo, <xref:System.Activities.ActivityBuilder> contiene la definizione del flusso di lavoro originale nonché una copia.</span><span class="sxs-lookup"><span data-stu-id="2ab11-127">After the method returns, the <xref:System.Activities.ActivityBuilder> contains the original workflow definition as well as a copy.</span></span>  
  
```csharp  
// Load the MortgageWorkflow definition from Xaml into  
// an ActivityBuilder.  
XamlXmlReaderSettings readerSettings = new XamlXmlReaderSettings()  
{  
    LocalAssembly = Assembly.GetExecutingAssembly()  
};  
  
XamlXmlReader xamlReader = new XamlXmlReader(@"C:\WorkflowDefitinions\MortgageWorkflow.xaml",   
    readerSettings);  
  
ActivityBuilder ab = XamlServices.Load(  
    ActivityXamlServices.CreateBuilderReader(xamlReader)) as ActivityBuilder;  
  
// Prepare the workflow definition for dynamic update.  
DynamicUpdateServices.PrepareForUpdate(ab);  
```  
  
> [!NOTE]
>  <span data-ttu-id="2ab11-128">Per scaricare il codice di esempio che accompagna questo argomento, vedere [il codice di esempio di aggiornamento dinamico](http://go.microsoft.com/fwlink/?LinkId=227905).</span><span class="sxs-lookup"><span data-stu-id="2ab11-128">To download the sample code that accompanies this topic, see [Dynamic Update sample code](http://go.microsoft.com/fwlink/?LinkId=227905).</span></span>  
  
###  <a name="Update"></a><span data-ttu-id="2ab11-129">Aggiornare la definizione del flusso di lavoro in modo da riflettere le modifiche desiderate</span><span class="sxs-lookup"><span data-stu-id="2ab11-129">Update the workflow definition to reflect the desired changes</span></span>  
 <span data-ttu-id="2ab11-130">Una volta che la definizione del flusso di lavoro è stata preparata per l'aggiornamento, è possibile apportare le modifiche desiderate.</span><span class="sxs-lookup"><span data-stu-id="2ab11-130">Once the workflow definition has been prepared for updating, the desired changes can be made.</span></span> <span data-ttu-id="2ab11-131">È possibile aggiungere o rimuovere attività, aggiungere, spostare o eliminare variabili pubbliche, aggiungere o rimuovere argomenti e apportare modifiche alla firma dei delegati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="2ab11-131">You can add or remove activities, add, move or delete public variables, add or remove arguments, and make changes to the signature of activity delegates.</span></span> <span data-ttu-id="2ab11-132">Non è possibile rimuovere un'attività in esecuzione o modificare la firma di un delegato in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2ab11-132">You cannot remove a running activity or change the signature of a running delegate.</span></span> <span data-ttu-id="2ab11-133">Tali modifiche possono essere eseguite usando il codice o in una finestra di progettazione del flusso di lavoro rieseguita nell'host.</span><span class="sxs-lookup"><span data-stu-id="2ab11-133">These changes may be made using code, or in a re-hosted workflow designer.</span></span> <span data-ttu-id="2ab11-134">Nell'esempio riportato di seguito viene aggiunta un'attività `VerifyAppraisal` personalizzata alla sequenza che costituisce il corpo dell'oggetto `MortgageWorkflow` usato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="2ab11-134">In the following example, a custom `VerifyAppraisal` activity is added to the Sequence that makes up the body of the `MortgageWorkflow` from the previous example.</span></span>  
  
```csharp  
// Make desired changes to the definition. In this example, we are  
// inserting a new VerifyAppraisal activity as the 3rd child of the root Sequence.  
VerifyAppraisal va = new VerifyAppraisal  
{  
    Result = new VisualBasicReference<bool>("LoanCriteria")  
};  
  
// Get the Sequence that makes up the body of the workflow.  
Sequence s = ab.Implementation as Sequence;  
  
// Insert the new activity into the Sequence.  
s.Activities.Insert(2, va);  
```  
  
###  <a name="Create"></a><span data-ttu-id="2ab11-135">Creare la mappa di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="2ab11-135">Create the update map</span></span>  
 <span data-ttu-id="2ab11-136">Una volta che la definizione del flusso di lavoro preparata per l'aggiornamento è stata modificata, è possibile creare la mappa di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="2ab11-136">Once the workflow definition that was prepared for update has been modified, the update map can be created.</span></span> <span data-ttu-id="2ab11-137">Per creare una mappa di aggiornamento dinamico, viene richiamato il metodo <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2ab11-137">To create a dynamic update map, the <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> method is invoked.</span></span> <span data-ttu-id="2ab11-138">Il metodo restituisce un oggetto <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> contenente le informazioni necessarie al runtime per modificare un'istanza persistente del flusso di lavoro in modo che possa essere caricata e ripresa con la nuova definizione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2ab11-138">This returns a <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> that contains the information the runtime needs to modify a persisted workflow instance so that it may be loaded and resumed with the new workflow definition.</span></span> <span data-ttu-id="2ab11-139">Nell'esempio riportato di seguito, viene creata una mappa di aggiornamento per la definizione di `MortgageWorkflow` modificata usata nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="2ab11-139">In the following example, a dynamic map is created for the modified `MortgageWorkflow` definition from the previous example.</span></span>  
  
```csharp  
// Create the update map.  
DynamicUpdateMap map = DynamicUpdateServices.CreateUpdateMap(ab);  
```  
  
 <span data-ttu-id="2ab11-140">Questa mappa di aggiornamento può essere immediatamente usata per modificare le istanze persistenti del flusso di lavoro o, come accade più spesso, può essere salvata e gli aggiornamenti possono essere applicati in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="2ab11-140">This update map can immediately be used to modify persisted workflow instances, or more typically it can be saved and the updates applied later.</span></span> <span data-ttu-id="2ab11-141">Un modo per salvare la mappa di aggiornamento consiste nel serializzarla in un file, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="2ab11-141">One way to save the update map is to serialize it to a file, as shown in the following example.</span></span>  
  
```csharp  
// Serialize the update map to a file.  
DataContractSerializer serializer = new DataContractSerializer(typeof(DynamicUpdateMap));  
using (FileStream fs = System.IO.File.Open(@"C:\WorkflowDefitinions\MortgageWorkflow.map", FileMode.Create))  
{  
    serializer.WriteObject(fs, map);  
}  
```  
  
 <span data-ttu-id="2ab11-142">Al termine del metodo <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType>, la definizione duplicata del flusso di lavoro e altre informazioni relative all'aggiornamento dinamico aggiunte nella chiamata al metodo <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> vengono rimosse e la definizione modificata del flusso di lavoro è pronta per essere salvata per poter essere usata in un secondo momento quando le istanze aggiornate del flusso di lavoro vengono riprese.</span><span class="sxs-lookup"><span data-stu-id="2ab11-142">When <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> returns, the cloned workflow definition and other dynamic update information that was added in the call to <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> is removed, and the modified workflow definition is ready to be saved so that it can be used later when resuming updated workflow instances.</span></span> <span data-ttu-id="2ab11-143">Nell'esempio riportato di seguito la definizione modificata del flusso di lavoro viene salvata in `MortgageWorkflow_v2.xaml`.</span><span class="sxs-lookup"><span data-stu-id="2ab11-143">In the following example, the modified workflow definition is saved to `MortgageWorkflow_v2.xaml`.</span></span>  
  
```csharp  
// Save the modified workflow definition.  
StreamWriter sw = File.CreateText(@"C:\WorkflowDefitinions\MortgageWorkflow_v1.1.xaml");  
XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(sw, new XamlSchemaContext()));  
XamlServices.Save(xw, ab);  
sw.Close();  
```  
  
###  <a name="Apply"></a><span data-ttu-id="2ab11-144">Applicare la mappa di aggiornamento alle istanze del flusso di lavoro persistente desiderato</span><span class="sxs-lookup"><span data-stu-id="2ab11-144">Apply the update map to the desired persisted workflow instances</span></span>  
 <span data-ttu-id="2ab11-145">Una volta creata, la mappa di aggiornamento può essere applicata in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="2ab11-145">Applying the update map can be done at any time after creating it.</span></span> <span data-ttu-id="2ab11-146">Può essere applicata subito usando l'istanza <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> restituita dal metodo <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> oppure in secondo momento usando una copia salvata.</span><span class="sxs-lookup"><span data-stu-id="2ab11-146">It can be done right away using the <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> instance that was returned by <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType>, or it can be done later using a saved copy of the update map.</span></span> <span data-ttu-id="2ab11-147">Per aggiornare un'istanza del flusso di lavoro, caricarla in <xref:System.Activities.WorkflowApplicationInstance> usando <xref:System.Activities.WorkflowApplication.GetInstance%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2ab11-147">To update a workflow instance, load it into a <xref:System.Activities.WorkflowApplicationInstance> using <xref:System.Activities.WorkflowApplication.GetInstance%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2ab11-148">Creare quindi un elemento <xref:System.Activities.WorkflowApplication> usando la definizione aggiornata del flusso di lavoro, quindi l'elemento <xref:System.Activities.WorkflowIdentity> desiderato.</span><span class="sxs-lookup"><span data-stu-id="2ab11-148">Next, create a <xref:System.Activities.WorkflowApplication> using the updated workflow definition, and the desired <xref:System.Activities.WorkflowIdentity>.</span></span> <span data-ttu-id="2ab11-149">Questo oggetto <xref:System.Activities.WorkflowIdentity> può essere diverso da quello usato per rendere persistente il flusso di lavoro originale e in genere è diverso in modo da indicare che l'istanza persistente è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="2ab11-149">This <xref:System.Activities.WorkflowIdentity> may be different than the one that was used to persist the original workflow, and typically is in order to reflect that the persisted instance has been modified.</span></span> <span data-ttu-id="2ab11-150">Una volta creato l'oggetto <xref:System.Activities.WorkflowApplication>, viene caricato usando l'overload di <xref:System.Activities.WorkflowApplication.Load%2A?displayProperty=nameWithType> che accetta un oggetto <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> quindi viene scaricato tramite una chiamata a <xref:System.Activities.WorkflowApplication.Unload%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2ab11-150">Once the <xref:System.Activities.WorkflowApplication> is created, it is loaded using the overload of <xref:System.Activities.WorkflowApplication.Load%2A?displayProperty=nameWithType> that takes a <xref:System.Activities.DynamicUpdate.DynamicUpdateMap>, and then unloaded with a call to <xref:System.Activities.WorkflowApplication.Unload%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2ab11-151">In questo modo viene applicato l'aggiornamento dinamico e resa persistente l'istanza aggiornata del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2ab11-151">This applies the dynamic update and persists the updated workflow instance.</span></span>  
  
```csharp  
// Load the serialized update map.  
DynamicUpdateMap map;  
using (FileStream fs = File.Open(@"C:\WorkflowDefitinions\MortgageWorkflow.map", FileMode.Open))  
{  
    DataContractSerializer serializer = new DataContractSerializer(typeof(DynamicUpdateMap));  
    object updateMap = serializer.ReadObject(fs);  
    if (updateMap == null)  
    {  
        throw new ApplicationException("DynamicUpdateMap is null.");  
    }  
  
    map = (DynamicUpdateMap)updateMap;  
}  
  
// Retrieve a list of workflow instance ids that corresponds to the  
// workflow instances to update. This step is the responsibility of  
// the application developer.  
List<Guid> ids = GetPersistedWorkflowIds();  
foreach (Guid id in ids)  
{  
    // Get a proxy to the persisted workflow instance.  
    SqlWorkflowInstanceStore store = new SqlWorkflowInstanceStore(connectionString);  
    WorkflowApplicationInstance instance = WorkflowApplication.GetInstance(id, store);  
  
    // If desired, you can inspect the WorkflowIdentity of the instance  
    // using the DefinitionIdentity property to determine whether to apply  
    // the update.  
    Console.WriteLine(instance.DefinitionIdentity);  
  
    // Create a workflow application. You must specify the updated workflow definition, and  
    // you may provide an updated WorkflowIdentity if desired to reflect the update.  
    WorkflowIdentity identity = new WorkflowIdentity  
    {  
        Name = "MortgageWorkflow v1.1",  
        Version = new Version(1, 1, 0, 0)  
    };  
  
    // Load the persisted workflow instance using the updated workflow definition  
    // and with an updated WorkflowIdentity. In this example the MortgageWorkflow class  
    // contains the updated definition.  
    WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identity);  
  
    // Apply the dynamic update on the loaded instance.                
    wfApp.Load(instance, map);  
  
    // Unload the updated instance.  
    wfApp.Unload();  
}  
```  
  
### <a name="resuming-an-updated-workflow-instance"></a><span data-ttu-id="2ab11-152">Ripresa di un'istanza aggiornata del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="2ab11-152">Resuming an Updated Workflow Instance</span></span>  
 <span data-ttu-id="2ab11-153">Una volta applicato l'aggiornamento dinamico, è possibile riprendere l'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2ab11-153">Once dynamic update has been applied, the workflow instance may be resumed.</span></span> <span data-ttu-id="2ab11-154">Si noti che è necessario usare la nuova definizione aggiornata e l'oggetto <xref:System.Activities.WorkflowIdentity>.</span><span class="sxs-lookup"><span data-stu-id="2ab11-154">Note that the new updated definition and <xref:System.Activities.WorkflowIdentity> must be used.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ab11-155">Per ulteriori informazioni sull'utilizzo di <xref:System.Activities.WorkflowApplication> e <xref:System.Activities.WorkflowIdentity>, vedere[usando WorkflowIdentity e controllo delle versioni](../../../docs/framework/windows-workflow-foundation/using-workflowidentity-and-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="2ab11-155">For more information about working with <xref:System.Activities.WorkflowApplication> and <xref:System.Activities.WorkflowIdentity>, see[Using WorkflowIdentity and Versioning](../../../docs/framework/windows-workflow-foundation/using-workflowidentity-and-versioning.md).</span></span>  
  
 <span data-ttu-id="2ab11-156">Nell'esempio riportato di seguito, il flusso di lavoro `MortgageWorkflow_v1.1.xaml` dell'esempio precedente è stato compilato e viene caricato e ripreso usando la definizione aggiornata del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2ab11-156">In the following example, the `MortgageWorkflow_v1.1.xaml` workflow from the previous example has been compiled, and is loaded and resumed using the updated workflow definition.</span></span>  
  
```csharp  
// Load the persisted workflow instance using the updated workflow definition  
// and updated WorkflowIdentity.  
WorkflowIdentity identity = new WorkflowIdentity  
{  
    Name = "MortgageWorkflow v1.1",  
    Version = new Version(1, 1, 0, 0)  
};  
  
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identity);  
  
// Configure persistence and desired workflow event handlers.  
// (Omitted for brevity.)  
ConfigureWorkflowApplication(wfApp);  
  
// Load the persisted workflow instance.  
wfApp.Load(InstanceId);  
  
// Resume the workflow.  
// wfApp.ResumeBookmark(...);  
```  
  
> [!NOTE]
>  <span data-ttu-id="2ab11-157">Per scaricare il codice di esempio che accompagna questo argomento, vedere [il codice di esempio di aggiornamento dinamico](http://go.microsoft.com/fwlink/?LinkId=227905).</span><span class="sxs-lookup"><span data-stu-id="2ab11-157">To download the sample code that accompanies this topic, see [Dynamic Update sample code](http://go.microsoft.com/fwlink/?LinkId=227905).</span></span>

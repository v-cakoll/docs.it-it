---
title: Utilizzo del contesto di modifica ModelItem
ms.date: 03/30/2017
ms.assetid: 7f9f1ea5-0147-4079-8eca-be94f00d3aa1
ms.openlocfilehash: e1481d96e39f837d72834222d2839c520e880cc6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142514"
---
# <a name="using-the-modelitem-editing-context"></a><span data-ttu-id="25b4d-102">Utilizzo del contesto di modifica ModelItem</span><span class="sxs-lookup"><span data-stu-id="25b4d-102">Using the ModelItem Editing Context</span></span>
<span data-ttu-id="25b4d-103">Il contesto di modifica <xref:System.Activities.Presentation.Model.ModelItem> è l'oggetto usato dall'applicazione host per comunicare con la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="25b4d-103">The <xref:System.Activities.Presentation.Model.ModelItem> editing context is the object that the host application uses to communicate with the designer.</span></span> <span data-ttu-id="25b4d-104"><xref:System.Activities.Presentation.EditingContext> espone due metodi utilizzabili, <xref:System.Activities.Presentation.EditingContext.Items%2A> e <xref:System.Activities.Presentation.EditingContext.Services%2A>.</span><span class="sxs-lookup"><span data-stu-id="25b4d-104"><xref:System.Activities.Presentation.EditingContext> exposes two methods, <xref:System.Activities.Presentation.EditingContext.Items%2A> and <xref:System.Activities.Presentation.EditingContext.Services%2A>, which can be used</span></span>  
  
## <a name="the-items-collection"></a><span data-ttu-id="25b4d-105">La raccolta Items</span><span class="sxs-lookup"><span data-stu-id="25b4d-105">The Items collection</span></span>  
 <span data-ttu-id="25b4d-106">La raccolta <xref:System.Activities.Presentation.EditingContext.Items%2A> viene usata per accedere ai dati condivisi tra l'host e la finestra di progettazione o ai dati disponibili a tutte le finestre di progettazione.</span><span class="sxs-lookup"><span data-stu-id="25b4d-106">The <xref:System.Activities.Presentation.EditingContext.Items%2A> collection is used to access data that is shared between the host and the designer, or data that is available to all designers.</span></span> <span data-ttu-id="25b4d-107">La raccolta dispone delle seguenti funzionalità, accessibili tramite la classe <xref:System.Activities.Presentation.ContextItemManager>:</span><span class="sxs-lookup"><span data-stu-id="25b4d-107">This collection has the following capabilities, accessed via the <xref:System.Activities.Presentation.ContextItemManager> class:</span></span>  
  
1. <xref:System.Activities.Presentation.ContextItemManager.GetValue%2A>  
  
2. <xref:System.Activities.Presentation.ContextItemManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ContextItemManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>  
  
## <a name="the-services-collection"></a><span data-ttu-id="25b4d-108">La raccolta Services</span><span class="sxs-lookup"><span data-stu-id="25b4d-108">The Services collection</span></span>  
 <span data-ttu-id="25b4d-109">La raccolta <xref:System.Activities.Presentation.EditingContext.Services%2A> viene usata per accedere ai servizi usati dalla finestra di progettazione per interagire con l'host o ai servizi usati da tutte le finestre di progettazione.</span><span class="sxs-lookup"><span data-stu-id="25b4d-109">The <xref:System.Activities.Presentation.EditingContext.Services%2A> collection is used to access services that the designer uses to interact with the host, or services that all designers use.</span></span> <span data-ttu-id="25b4d-110">Questa raccolta dispone dei principali metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="25b4d-110">This collection has the following methods of note:</span></span>  
  
1. <xref:System.Activities.Presentation.ServiceManager.Publish%2A>  
  
2. <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ServiceManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ServiceManager.GetService%2A>  
  
## <a name="assigning-a-designer-an-activity"></a><span data-ttu-id="25b4d-111">Assegnazione di un'attività a una finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="25b4d-111">Assigning a designer an activity</span></span>  
 <span data-ttu-id="25b4d-112">Per specificare quale finestra di progettazione viene usata da un'attività, viene usato l'attributo Designer.</span><span class="sxs-lookup"><span data-stu-id="25b4d-112">To specify which designer an activity uses, the Designer attribute is used.</span></span>  
  
```csharp  
[Designer(typeof(MyClassDesigner))]  
public sealed class MyClass : CodeActivity  
{
}
```  
  
## <a name="creating-a-service"></a><span data-ttu-id="25b4d-113">Creazione di un servizio</span><span class="sxs-lookup"><span data-stu-id="25b4d-113">Creating a service</span></span>  
 <span data-ttu-id="25b4d-114">Per creare un servizio con la funzione di condotto di informazioni tra la finestra di progettazione e l'host, è necessario creare un'interfaccia e un'implementazione.</span><span class="sxs-lookup"><span data-stu-id="25b4d-114">To create a service that serves as a conduit of information between the designer and the host, an interface and an implementation must be created.</span></span> <span data-ttu-id="25b4d-115">L'interfaccia viene usata dal metodo <xref:System.Activities.Presentation.ServiceManager.Publish%2A> per definire i membri del servizio e l'implementazione contiene la logica del servizio.</span><span class="sxs-lookup"><span data-stu-id="25b4d-115">The interface is used by the <xref:System.Activities.Presentation.ServiceManager.Publish%2A> method to define the members of the service, and the implementation contains the logic for the service.</span></span> <span data-ttu-id="25b4d-116">Nell'esempio di codice seguente vengono create l'interfaccia e l'implementazione di un servizio.</span><span class="sxs-lookup"><span data-stu-id="25b4d-116">In the following code example, a service interface and implementation are created.</span></span>  
  
```csharp  
public interface IMyService  
    {  
        IEnumerable<string> GetValues(string DisplayName);  
    }  
  
    public class MyServiceImpl : IMyService  
    {  
        public IEnumerable<string> GetValues(string DisplayName)  
        {  
            return new string[]  {
                DisplayName + " One",
                DisplayName + " Two",  
                "Three " + DisplayName  
            } ;  
        }  
    }  
```  
  
## <a name="publishing-a-service"></a><span data-ttu-id="25b4d-117">Pubblicazione di un servizio</span><span class="sxs-lookup"><span data-stu-id="25b4d-117">Publishing a service</span></span>  
 <span data-ttu-id="25b4d-118">Affinché una finestra di progettazione utilizzi un servizio, questo deve essere prima pubblicato dal host usando il metodo <xref:System.Activities.Presentation.ServiceManager.Publish%2A>.</span><span class="sxs-lookup"><span data-stu-id="25b4d-118">For a designer to consume a service, it must first be published by the host using the <xref:System.Activities.Presentation.ServiceManager.Publish%2A> method.</span></span>  
  
```csharp  
this.Context.Services.Publish<IMyService>(new MyServiceImpl);  
```  
  
## <a name="subscribing-to-a-service"></a><span data-ttu-id="25b4d-119">Sottoscrizione di un servizio</span><span class="sxs-lookup"><span data-stu-id="25b4d-119">Subscribing to a service</span></span>  
 <span data-ttu-id="25b4d-120">La finestra di progettazione ottiene accesso al servizio usando il metodo <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> nel metodo <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A>.</span><span class="sxs-lookup"><span data-stu-id="25b4d-120">The designer obtains access to the service using the <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> method in the <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A> method.</span></span> <span data-ttu-id="25b4d-121">Nel frammento di codice seguente viene mostrato come sottoscrivere un servizio.</span><span class="sxs-lookup"><span data-stu-id="25b4d-121">The following code snippet demonstrates how to subscribe to a service.</span></span>  
  
```csharp  
protected override void OnModelItemChanged(object newItem)  
{  
    if (!subscribed)  
    {  
        this.Context.Services.Subscribe<IMyService>(  
            servInstance =>  
            {  
                listBox1.ItemsSource = servInstance.GetValues(this.ModelItem.Properties["DisplayName"].ComputedValue.ToString());  
            }  
            );  
        subscribed = true;
    }  
}  
```  
  
## <a name="sharing-data-using-the-items-collection"></a><span data-ttu-id="25b4d-122">Condivisione di dati tramite la raccolta Items</span><span class="sxs-lookup"><span data-stu-id="25b4d-122">Sharing data using the Items collection</span></span>  
 <span data-ttu-id="25b4d-123">L'utilizzo della raccolta Items è simile all'utilizzo della raccolta Services, tranne che si usa <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> anziché Publish.</span><span class="sxs-lookup"><span data-stu-id="25b4d-123">Using the Items collection is similar to using the Services collection, except that <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> is used instead of Publish.</span></span> <span data-ttu-id="25b4d-124">Questa raccolta è più adatta per la condivisione di dati semplici tra le finestre di progettazione e l'host che per funzionalità complesse.</span><span class="sxs-lookup"><span data-stu-id="25b4d-124">This collection is more appropriate for sharing simple data between the designers and the host, rather than complex functionality.</span></span>  
  
## <a name="editingcontext-host-items-and-services"></a><span data-ttu-id="25b4d-125">Elementi e servizi host di EditingContext</span><span class="sxs-lookup"><span data-stu-id="25b4d-125">EditingContext host items and services</span></span>  
 <span data-ttu-id="25b4d-126">In .NET Framework sono disponibili numerosi elementi e servizi predefiniti a cui si accede tramite il contesto di modifica.</span><span class="sxs-lookup"><span data-stu-id="25b4d-126">The .NET Framework provides a number of built-in items and services accessed through the editing context.</span></span>  
  
 <span data-ttu-id="25b4d-127">Elementi:</span><span class="sxs-lookup"><span data-stu-id="25b4d-127">Items:</span></span>  
  
- <span data-ttu-id="25b4d-128"><xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: gestisce l'elenco degli assembly locali di riferimento che verranno usati nel flusso di lavoro per i controlli (ad esempio l'editor espressioni).</span><span class="sxs-lookup"><span data-stu-id="25b4d-128"><xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: Manages the list of referenced local assemblies that will be used inside the workflow for controls (such as the expression editor).</span></span>  
  
- <span data-ttu-id="25b4d-129"><xref:System.Activities.Presentation.Hosting.ReadOnlyState>: indica se la finestra di progettazione è in stato di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="25b4d-129"><xref:System.Activities.Presentation.Hosting.ReadOnlyState>: Indicates whether the designer is in a read-only state.</span></span>  
  
- <span data-ttu-id="25b4d-130"><xref:System.Activities.Presentation.View.Selection>: definisce la raccolta di oggetti attualmente selezionati.</span><span class="sxs-lookup"><span data-stu-id="25b4d-130"><xref:System.Activities.Presentation.View.Selection>: Defines the collection of objects that are currently selected.</span></span>  
  
- <span data-ttu-id="25b4d-131"><xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:</span><span class="sxs-lookup"><span data-stu-id="25b4d-131"><xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:</span></span>  
  
- <span data-ttu-id="25b4d-132"><xref:System.Activities.Presentation.WorkflowFileItem>: fornisce informazioni sul file su cui si basa la sessione di modifica corrente.</span><span class="sxs-lookup"><span data-stu-id="25b4d-132"><xref:System.Activities.Presentation.WorkflowFileItem>: Provides information on the file that the current editing session is based on.</span></span>  
  
 <span data-ttu-id="25b4d-133">Servizi:</span><span class="sxs-lookup"><span data-stu-id="25b4d-133">Services:</span></span>  
  
- <span data-ttu-id="25b4d-134"><xref:System.Activities.Presentation.Model.AttachedPropertiesService>: consente l'aggiunta di proprietà all'istanza corrente tramite <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="25b4d-134"><xref:System.Activities.Presentation.Model.AttachedPropertiesService>: Allows properties to be added to the current instance, using <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.</span></span>  
  
- <span data-ttu-id="25b4d-135"><xref:System.Activities.Presentation.View.DesignerView>: consente l'accesso alle proprietà del Canvas della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="25b4d-135"><xref:System.Activities.Presentation.View.DesignerView>: Allows access to the properties of the designer canvas.</span></span>  
  
- <span data-ttu-id="25b4d-136"><xref:System.Activities.Presentation.IActivityToolboxService>: consente l'aggiornamento del contenuto della casella degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="25b4d-136"><xref:System.Activities.Presentation.IActivityToolboxService>: Allows the contents of the toolbox to be updated.</span></span>  
  
- <span data-ttu-id="25b4d-137"><xref:System.Activities.Presentation.Hosting.ICommandService>: usato per integrare i comandi della finestra di progettazione (quale Menu di scelta rapida) con implementazioni del servizio personalizzate.</span><span class="sxs-lookup"><span data-stu-id="25b4d-137"><xref:System.Activities.Presentation.Hosting.ICommandService>: Used to integrate designer commands (such as Context Menu) with custom-provided service implementations.</span></span>  
  
- <span data-ttu-id="25b4d-138"><xref:System.Activities.Presentation.Debug.IDesignerDebugView>: fornisce funzionalità per il debugger della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="25b4d-138"><xref:System.Activities.Presentation.Debug.IDesignerDebugView>: Provides functionality for the designer debugger.</span></span>  
  
- <span data-ttu-id="25b4d-139"><xref:System.Activities.Presentation.View.IExpressionEditorService>: fornisce l'accesso alla finestra di dialogo dell'Editor espressioni.</span><span class="sxs-lookup"><span data-stu-id="25b4d-139"><xref:System.Activities.Presentation.View.IExpressionEditorService>: Provides access to the Expression Editor dialog.</span></span>  
  
- <span data-ttu-id="25b4d-140"><xref:System.Activities.Presentation.IIntegratedHelpService>: fornisce funzionalità integrate di Guida alla finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="25b4d-140"><xref:System.Activities.Presentation.IIntegratedHelpService>: Provides the designer with integrated help functionality.</span></span>  
  
- <span data-ttu-id="25b4d-141"><xref:System.Activities.Presentation.Validation.IValidationErrorService>: fornisce l'accesso agli errori di convalida tramite <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.</span><span class="sxs-lookup"><span data-stu-id="25b4d-141"><xref:System.Activities.Presentation.Validation.IValidationErrorService>: Provides access to validation errors using <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.</span></span>  
  
- <span data-ttu-id="25b4d-142"><xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: fornisce un servizio interno per l'archiviazione e il recupero dei dati.</span><span class="sxs-lookup"><span data-stu-id="25b4d-142"><xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: Provides an internal service to store and retrieve data.</span></span> <span data-ttu-id="25b4d-143">Questo servizio viene utilizzato internamente da .NET Framework e non è destinato all'utilizzo esterno.</span><span class="sxs-lookup"><span data-stu-id="25b4d-143">This service is used internally by the .NET Framework, and is not intended for external use.</span></span>  
  
- <span data-ttu-id="25b4d-144"><xref:System.Activities.Presentation.IXamlLoadErrorService>: fornisce l'accesso alla raccolta di errori di caricamento XAML tramite <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.</span><span class="sxs-lookup"><span data-stu-id="25b4d-144"><xref:System.Activities.Presentation.IXamlLoadErrorService>: Provides access to the XAML load error collection using <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.</span></span>  
  
- <span data-ttu-id="25b4d-145"><xref:System.Activities.Presentation.Services.ModelService>: usato dalla finestra di progettazione per interagire con il modello del flusso di lavoro modificato.</span><span class="sxs-lookup"><span data-stu-id="25b4d-145"><xref:System.Activities.Presentation.Services.ModelService>: Used by the designer to interact with the model of the workflow being edited.</span></span>  
  
- <span data-ttu-id="25b4d-146"><xref:System.Activities.Presentation.Model.ModelTreeManager>: fornisce l'accesso alla radice dell'albero dell'elemento del modello tramite <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.</span><span class="sxs-lookup"><span data-stu-id="25b4d-146"><xref:System.Activities.Presentation.Model.ModelTreeManager>: Provides access to the root of the model item tree using <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.</span></span>  
  
- <span data-ttu-id="25b4d-147"><xref:System.Activities.Presentation.UndoEngine>: fornisce funzionalità di rollback e rollforward.</span><span class="sxs-lookup"><span data-stu-id="25b4d-147"><xref:System.Activities.Presentation.UndoEngine>: Provides undo and redo functionality.</span></span>  
  
- <span data-ttu-id="25b4d-148"><xref:System.Activities.Presentation.Services.ViewService>: esegue il mapping degli elementi visivi agli elementi del modello sottostante.</span><span class="sxs-lookup"><span data-stu-id="25b4d-148"><xref:System.Activities.Presentation.Services.ViewService>: Maps visual elements to underlying model items.</span></span>  
  
- <span data-ttu-id="25b4d-149"><xref:System.Activities.Presentation.View.ViewStateService>: archivia gli stati di visualizzazione per gli elementi del modello.</span><span class="sxs-lookup"><span data-stu-id="25b4d-149"><xref:System.Activities.Presentation.View.ViewStateService>: Stores view states for model items.</span></span>  
  
- <span data-ttu-id="25b4d-150"><xref:System.Activities.Presentation.View.VirtualizedContainerService>: usato per personalizzare il comportamento dell'interfaccia utente del contenitore virtuale.</span><span class="sxs-lookup"><span data-stu-id="25b4d-150"><xref:System.Activities.Presentation.View.VirtualizedContainerService>: Used to customize the virtual container UI behavior.</span></span>  
  
- <span data-ttu-id="25b4d-151"><xref:System.Activities.Presentation.Hosting.WindowHelperService>: usato per registrare e annullare la registrazione dei delegati per le notifiche degli eventi.</span><span class="sxs-lookup"><span data-stu-id="25b4d-151"><xref:System.Activities.Presentation.Hosting.WindowHelperService>: Used to register and unregister delegates for event notifications.</span></span> <span data-ttu-id="25b4d-152">Consente inoltre l'impostazione del proprietario di una finestra.</span><span class="sxs-lookup"><span data-stu-id="25b4d-152">Also allows a window owner to be set.</span></span>

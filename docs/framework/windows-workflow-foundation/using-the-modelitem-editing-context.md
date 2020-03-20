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
# <a name="using-the-modelitem-editing-context"></a>Utilizzo del contesto di modifica ModelItem
Il contesto di modifica <xref:System.Activities.Presentation.Model.ModelItem> è l'oggetto usato dall'applicazione host per comunicare con la finestra di progettazione. <xref:System.Activities.Presentation.EditingContext> espone due metodi utilizzabili, <xref:System.Activities.Presentation.EditingContext.Items%2A> e <xref:System.Activities.Presentation.EditingContext.Services%2A>.  
  
## <a name="the-items-collection"></a>La raccolta Items  
 La raccolta <xref:System.Activities.Presentation.EditingContext.Items%2A> viene usata per accedere ai dati condivisi tra l'host e la finestra di progettazione o ai dati disponibili a tutte le finestre di progettazione. La raccolta dispone delle seguenti funzionalità, accessibili tramite la classe <xref:System.Activities.Presentation.ContextItemManager>:  
  
1. <xref:System.Activities.Presentation.ContextItemManager.GetValue%2A>  
  
2. <xref:System.Activities.Presentation.ContextItemManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ContextItemManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>  
  
## <a name="the-services-collection"></a>La raccolta Services  
 La raccolta <xref:System.Activities.Presentation.EditingContext.Services%2A> viene usata per accedere ai servizi usati dalla finestra di progettazione per interagire con l'host o ai servizi usati da tutte le finestre di progettazione. Questa raccolta dispone dei principali metodi seguenti:  
  
1. <xref:System.Activities.Presentation.ServiceManager.Publish%2A>  
  
2. <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>  
  
3. <xref:System.Activities.Presentation.ServiceManager.Unsubscribe%2A>  
  
4. <xref:System.Activities.Presentation.ServiceManager.GetService%2A>  
  
## <a name="assigning-a-designer-an-activity"></a>Assegnazione di un'attività a una finestra di progettazione  
 Per specificare quale finestra di progettazione viene usata da un'attività, viene usato l'attributo Designer.  
  
```csharp  
[Designer(typeof(MyClassDesigner))]  
public sealed class MyClass : CodeActivity  
{
}
```  
  
## <a name="creating-a-service"></a>Creazione di un servizio  
 Per creare un servizio con la funzione di condotto di informazioni tra la finestra di progettazione e l'host, è necessario creare un'interfaccia e un'implementazione. L'interfaccia viene usata dal metodo <xref:System.Activities.Presentation.ServiceManager.Publish%2A> per definire i membri del servizio e l'implementazione contiene la logica del servizio. Nell'esempio di codice seguente vengono create l'interfaccia e l'implementazione di un servizio.  
  
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
  
## <a name="publishing-a-service"></a>Pubblicazione di un servizio  
 Affinché una finestra di progettazione utilizzi un servizio, questo deve essere prima pubblicato dal host usando il metodo <xref:System.Activities.Presentation.ServiceManager.Publish%2A>.  
  
```csharp  
this.Context.Services.Publish<IMyService>(new MyServiceImpl);  
```  
  
## <a name="subscribing-to-a-service"></a>Sottoscrizione di un servizio  
 La finestra di progettazione ottiene accesso al servizio usando il metodo <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> nel metodo <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A>. Nel frammento di codice seguente viene mostrato come sottoscrivere un servizio.  
  
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
  
## <a name="sharing-data-using-the-items-collection"></a>Condivisione di dati tramite la raccolta Items  
 L'utilizzo della raccolta Items è simile all'utilizzo della raccolta Services, tranne che si usa <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A> anziché Publish. Questa raccolta è più adatta per la condivisione di dati semplici tra le finestre di progettazione e l'host che per funzionalità complesse.  
  
## <a name="editingcontext-host-items-and-services"></a>Elementi e servizi host di EditingContext  
 In .NET Framework sono disponibili numerosi elementi e servizi predefiniti a cui si accede tramite il contesto di modifica.  
  
 Elementi:  
  
- <xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: gestisce l'elenco degli assembly locali di riferimento che verranno usati nel flusso di lavoro per i controlli (ad esempio l'editor espressioni).  
  
- <xref:System.Activities.Presentation.Hosting.ReadOnlyState>: indica se la finestra di progettazione è in stato di sola lettura.  
  
- <xref:System.Activities.Presentation.View.Selection>: definisce la raccolta di oggetti attualmente selezionati.  
  
- <xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:  
  
- <xref:System.Activities.Presentation.WorkflowFileItem>: fornisce informazioni sul file su cui si basa la sessione di modifica corrente.  
  
 Servizi:  
  
- <xref:System.Activities.Presentation.Model.AttachedPropertiesService>: consente l'aggiunta di proprietà all'istanza corrente tramite <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.  
  
- <xref:System.Activities.Presentation.View.DesignerView>: consente l'accesso alle proprietà del Canvas della finestra di progettazione.  
  
- <xref:System.Activities.Presentation.IActivityToolboxService>: consente l'aggiornamento del contenuto della casella degli strumenti.  
  
- <xref:System.Activities.Presentation.Hosting.ICommandService>: usato per integrare i comandi della finestra di progettazione (quale Menu di scelta rapida) con implementazioni del servizio personalizzate.  
  
- <xref:System.Activities.Presentation.Debug.IDesignerDebugView>: fornisce funzionalità per il debugger della finestra di progettazione.  
  
- <xref:System.Activities.Presentation.View.IExpressionEditorService>: fornisce l'accesso alla finestra di dialogo dell'Editor espressioni.  
  
- <xref:System.Activities.Presentation.IIntegratedHelpService>: fornisce funzionalità integrate di Guida alla finestra di progettazione.  
  
- <xref:System.Activities.Presentation.Validation.IValidationErrorService>: fornisce l'accesso agli errori di convalida tramite <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.  
  
- <xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: fornisce un servizio interno per l'archiviazione e il recupero dei dati. Questo servizio viene utilizzato internamente da .NET Framework e non è destinato all'utilizzo esterno.  
  
- <xref:System.Activities.Presentation.IXamlLoadErrorService>: fornisce l'accesso alla raccolta di errori di caricamento XAML tramite <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.  
  
- <xref:System.Activities.Presentation.Services.ModelService>: usato dalla finestra di progettazione per interagire con il modello del flusso di lavoro modificato.  
  
- <xref:System.Activities.Presentation.Model.ModelTreeManager>: fornisce l'accesso alla radice dell'albero dell'elemento del modello tramite <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.  
  
- <xref:System.Activities.Presentation.UndoEngine>: fornisce funzionalità di rollback e rollforward.  
  
- <xref:System.Activities.Presentation.Services.ViewService>: esegue il mapping degli elementi visivi agli elementi del modello sottostante.  
  
- <xref:System.Activities.Presentation.View.ViewStateService>: archivia gli stati di visualizzazione per gli elementi del modello.  
  
- <xref:System.Activities.Presentation.View.VirtualizedContainerService>: usato per personalizzare il comportamento dell'interfaccia utente del contenitore virtuale.  
  
- <xref:System.Activities.Presentation.Hosting.WindowHelperService>: usato per registrare e annullare la registrazione dei delegati per le notifiche degli eventi. Consente inoltre l'impostazione del proprietario di una finestra.

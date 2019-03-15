---
title: Utilizzo del contesto di modifica ModelItem
ms.date: 03/30/2017
ms.assetid: 7f9f1ea5-0147-4079-8eca-be94f00d3aa1
ms.openlocfilehash: d8d2e7d055099a6aedd13dd48dd78403cdff2a50
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2019
ms.locfileid: "57846272"
---
# <a name="using-the-modelitem-editing-context"></a>Utilizzo del contesto di modifica ModelItem
Il contesto di modifica <xref:System.Activities.Presentation.Model.ModelItem> è l'oggetto usato dall'applicazione host per comunicare con la finestra di progettazione. <xref:System.Activities.Presentation.EditingContext> espone due metodi utilizzabili, <xref:System.Activities.Presentation.EditingContext.Items%2A> e <xref:System.Activities.Presentation.EditingContext.Services%2A>.  
  
## <a name="the-items-collection"></a>La raccolta Items  
 La raccolta <xref:System.Activities.Presentation.EditingContext.Items%2A> viene usata per accedere ai dati condivisi tra l'host e la finestra di progettazione o ai dati disponibili a tutte le finestre di progettazione. La raccolta dispone delle seguenti funzionalità, accessibili tramite la classe <xref:System.Activities.Presentation.ContextItemManager>:  
  
1.  <xref:System.Activities.Presentation.ContextItemManager.GetValue%2A>  
  
2.  <xref:System.Activities.Presentation.ContextItemManager.Subscribe%2A>  
  
3.  <xref:System.Activities.Presentation.ContextItemManager.Unsubscribe%2A>  
  
4.  <xref:System.Activities.Presentation.ContextItemManager.SetValue%2A>  
  
## <a name="the-services-collection"></a>La raccolta Services  
 La raccolta <xref:System.Activities.Presentation.EditingContext.Services%2A> viene usata per accedere ai servizi usati dalla finestra di progettazione per interagire con l'host o ai servizi usati da tutte le finestre di progettazione. Questa raccolta dispone dei principali metodi seguenti:  
  
1.  <xref:System.Activities.Presentation.ServiceManager.Publish%2A>  
  
2.  <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A>  
  
3.  <xref:System.Activities.Presentation.ServiceManager.Unsubscribe%2A>  
  
4.  <xref:System.Activities.Presentation.ServiceManager.GetService%2A>  
  
## <a name="assigning-a-designer-an-activity"></a>Assegnazione di un'attività a una finestra di progettazione  
 Per specificare quale finestra di progettazione viene usata da un'attività, viene usato l'attributo Designer.  
  
```  
[Designer(typeof(MyClassDesigner))]  
public sealed class MyClass : CodeActivity  
{  
```  
  
## <a name="creating-a-service"></a>Creazione di un servizio  
 Per creare un servizio con la funzione di condotto di informazioni tra la finestra di progettazione e l'host, è necessario creare un'interfaccia e un'implementazione. L'interfaccia viene usata dal metodo <xref:System.Activities.Presentation.ServiceManager.Publish%2A> per definire i membri del servizio e l'implementazione contiene la logica del servizio. Nell'esempio di codice seguente vengono create l'interfaccia e l'implementazione di un servizio.  
  
```  
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
  
```  
this.Context.Services.Publish<IMyService>(new MyServiceImpl);  
```  
  
## <a name="subscribing-to-a-service"></a>Sottoscrizione di un servizio  
 La finestra di progettazione ottiene accesso al servizio usando il metodo <xref:System.Activities.Presentation.ServiceManager.Subscribe%2A> nel metodo <xref:System.Activities.Presentation.WorkflowViewElement.OnModelItemChanged%2A>. Nel frammento di codice seguente viene mostrato come sottoscrivere un servizio.  
  
```  
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
 .NET Framework fornisce un numero di elementi incorporati e i servizi accessibili tramite il contesto di modifica.  
  
 Elementi:  
  
-   <xref:System.Activities.Presentation.Hosting.AssemblyContextControlItem>: Gestisce l'elenco locale di assembly di riferimento che verranno usati nel flusso di lavoro per i controlli (ad esempio, l'editor espressioni).  
  
-   <xref:System.Activities.Presentation.Hosting.ReadOnlyState>: Indica se la finestra di progettazione è in uno stato di sola lettura.  
  
-   <xref:System.Activities.Presentation.View.Selection>: Definisce la raccolta di oggetti che sono attualmente selezionate.  
  
-   <xref:System.Activities.Presentation.Hosting.WorkflowCommandExtensionItem>:  
  
-   <xref:System.Activities.Presentation.WorkflowFileItem>: Fornisce informazioni sul file che si basa la sessione di modifica corrente.  
  
 Servizi:  
  
-   <xref:System.Activities.Presentation.Model.AttachedPropertiesService>: Consente di proprietà da aggiungere all'istanza corrente, usando <xref:System.Activities.Presentation.Model.AttachedPropertiesService.AddProperty%2A>.  
  
-   <xref:System.Activities.Presentation.View.DesignerView>: Consente l'accesso alle proprietà dell'area di disegno della finestra di progettazione.  
  
-   <xref:System.Activities.Presentation.IActivityToolboxService>: Consente il contenuto della casella degli strumenti da aggiornare.  
  
-   <xref:System.Activities.Presentation.Hosting.ICommandService>: Usato per integrare i comandi della finestra di progettazione (quale menu di scelta rapida) con implementazioni del servizio personalizzato.  
  
-   <xref:System.Activities.Presentation.Debug.IDesignerDebugView>: Fornisce funzionalità per il debugger della finestra di progettazione.  
  
-   <xref:System.Activities.Presentation.View.IExpressionEditorService>: Fornisce l'accesso alla finestra di dialogo Editor espressioni.  
  
-   <xref:System.Activities.Presentation.IIntegratedHelpService>: Fornisce la finestra di progettazione con funzionalità integrate di Guida.  
  
-   <xref:System.Activities.Presentation.Validation.IValidationErrorService>: Fornisce l'accesso agli errori di convalida usando <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>.  
  
-   <xref:System.Activities.Presentation.IWorkflowDesignerStorageService>: Fornisce un servizio interno per archiviare e recuperare i dati. Questo servizio viene usato internamente da .NET Framework e non è destinato a uso esterno.  
  
-   <xref:System.Activities.Presentation.IXamlLoadErrorService>: Fornisce l'accesso a XAML load errore raccolta usando <xref:System.Activities.Presentation.IXamlLoadErrorService.ShowXamlLoadErrors%2A>.  
  
-   <xref:System.Activities.Presentation.Services.ModelService>: Usato dalla finestra di progettazione per interagire con il modello del flusso di lavoro in corso di modifica.  
  
-   <xref:System.Activities.Presentation.Model.ModelTreeManager>: Fornisce l'accesso alla radice nell'albero del modello di elemento usando <xref:System.Activities.Presentation.Model.ModelItem.Root%2A>.  
  
-   <xref:System.Activities.Presentation.UndoEngine>: Fornisce l'annullamento e funzionalità di ripristino.  
  
-   <xref:System.Activities.Presentation.Services.ViewService>: Esegue il mapping degli elementi visivi agli elementi del modello sottostante.  
  
-   <xref:System.Activities.Presentation.View.ViewStateService>: Gli archivi stati di visualizzazione degli elementi del modello.  
  
-   <xref:System.Activities.Presentation.View.VirtualizedContainerService>: Consente di personalizzare il comportamento dell'interfaccia utente di contenitore virtuale.  
  
-   <xref:System.Activities.Presentation.Hosting.WindowHelperService>: Usato per registrare e annullare la registrazione di delegati per le notifiche degli eventi. Consente inoltre l'impostazione del proprietario di una finestra.

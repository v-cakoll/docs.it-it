---
title: Novità in Windows Workflow Foundation in .NET 4.5
ms.date: 03/30/2017
ms.assetid: 195c43a8-e0a8-43d9-aead-d65a9e6751ec
ms.openlocfilehash: 0244457a051740f37c11c48f41d98bdb2d741aec
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "74142029"
---
# <a name="whats-new-in-windows-workflow-foundation-in-net-45"></a>Novità in Windows Workflow Foundation in .NET 4.5

Windows Workflow Foundation (WF) in .NET Framework 4.5 introduces many new features, such as new activities, designer capabilities, and workflow development models. Many, but not all, of the new workflow features introduced in .NET Framework 4.5 are supported in the re-hosted workflow designer. For more information about the new features that are supported, see [Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer](wf-features-in-the-rehosted-workflow-designer.md). For more information about migrating .NET 3.0 and .NET 3.5 workflow applications to use the latest version, see [Migration Guidance](migration-guidance.md). This topic provides an overview of the new workflow features introduced in .NET Framework 4.5.

> [!WARNING]
> The new Windows Workflow Foundation features introduced in .NET Framework 4.5 are not available for projects that target previous versions of the framework. If a project that targets .NET Framework 4.5 is re-targeted to a previous version of the framework, several issues can occur.
>
> - C# expressions will be replaced in the designer with the message **Value was set in XAML**.
> - Si verificheranno molti errori di compilazione, incluso il seguente errore.
>
> **The file format is not compatible with current targeting framework. To convert the file format, please explicitly save the file. This error message will go away after you save the file and reopen the designer.**

## <a name="BKMK_Versioning"></a> Workflow Versioning

.NET Framework 4.5 introduced several new versioning features based around the new <xref:System.Activities.WorkflowIdentity> class. La classe <xref:System.Activities.WorkflowIdentity> fornisce agli autori dell'applicazione flusso di lavoro un meccanismo per eseguire il mapping di un'istanza del flusso di lavoro persistente con la relativa definizione.

- Gli sviluppatori che usano l'hosting di <xref:System.Activities.WorkflowApplication> possono usare la classe <xref:System.Activities.WorkflowIdentity> per consentire l'hosting side-by-side di più versioni di un flusso di lavoro. Le istanze del flusso di lavoro persistenti possono essere caricate usando la nuova classe <xref:System.Activities.WorkflowApplicationInstance>. Successivamente, <xref:System.Activities.WorkflowApplicationInstance.DefinitionIdentity%2A> può essere usato dall'host per fornire la versione corretta della definizione del flusso di lavoro durante la creazione di istanze di <xref:System.Activities.WorkflowApplication>. For more information, see [Using WorkflowIdentity and Versioning](using-workflowidentity-and-versioning.md) and [How to: Host Multiple Versions of a Workflow Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).

- L'oggetto <xref:System.ServiceModel.WorkflowServiceHost> è ora un host multiversione. Quando viene distribuita una nuova versione di un servizio del flusso di lavoro, vengono create nuove istanze usando il nuovo servizio, mentre le istanze esistenti vengono completate con la versione precedente. For more information, see [Side by Side Versioning in WorkflowServiceHost](../wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md).

- Viene introdotto l'aggiornamento dinamico che fornisce un meccanismo per aggiornare la definizione di un'istanza del flusso di lavoro persistente. For more information, see [Dynamic Update](dynamic-update.md) and [How to: Update the Definition of a Running Workflow Instance](how-to-update-the-definition-of-a-running-workflow-instance.md).

- A SqlWorkflowInstanceStoreSchemaUpgrade.sql database script is provided to upgrade persistence databases created using the .NET Framework 4 database scripts. This script updates .NET Framework 4 persistence databases to support the new versioning capabilities introduced in .NET Framework 4.5. Le istanze persistenti del flusso di lavoro nel database sono valori predefiniti specificati per il controllo delle versioni e possono partecipare all'esecuzione side-by-side e all'aggiornamento dinamico. For more information, see [Upgrading .NET Framework 4 Persistence Databases to Support Workflow Versioning](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases).

## <a name="BKMK_NewActivities"></a> Activities

La libreria di attività predefinita contiene nuove attività e funzionalità per le attività esistenti.

### <a name="BKMK_NoPersistScope"></a> NoPersist Scope

<xref:System.Activities.Statements.NoPersistScope> è una nuova attività contenitore che impedisce a un flusso di lavoro di essere reso persistente durante l'esecuzione delle attività figlio di NoPersistScope. Ciò si rivela utile in scenari in cui non è necessario che il flusso di lavoro sia reso persistente, ad esempio quando il flusso di lavoro usa risorse specifiche del computer come handle di file o durante le transazioni di database. In precedenza, per impedire la persistenza durante l'esecuzione di un'attività, era necessario un oggetto <xref:System.Activities.NativeActivity> personalizzato in cui veniva usato un oggetto <xref:System.Activities.NoPersistHandle>.

### <a name="BKMK_NewFlowchartCapabilities"></a> New Flowchart Capabilities

Flowcharts are updated for .NET Framework 4.5 and have the following new capabilities:

- La proprietà `DisplayName` di un'attività <xref:System.Activities.Statements.FlowSwitch%601> o <xref:System.Activities.Statements.FlowDecision> è modificabile. In questo modo, nell'ActivityDesigner verranno illustrate ulteriori informazioni sullo scopo dell'attività.

- I diagrammi di flusso dispongono di una nuova proprietà denominata <xref:System.Activities.Statements.Flowchart.ValidateUnconnectedNodes%2A>; l'impostazione predefinita per questa proprietà è `False`. Se questa proprietà viene impostata su `True`, i nodi dei diagrammi di flusso non connessi genereranno errori di convalida.

## <a name="support-for-partial-trust"></a>Supporto per l'attendibilità parziale

Workflows in .NET Framework 4 required a fully trusted application domain. In .NET Framework 4.5, workflows can operate in a partial trust environment. In un ambiente parzialmente attendibile, i componenti di terze parti possono essere usati senza concedere loro accesso completo alle risorse dell'host. Di seguito vengono riportati alcuni dei problemi che riguardano i flussi di lavoro in esecuzione con attendibilità parziale:

1. L'utilizzo dei componenti legacy (regole incluse) contenuti nell'attività di <xref:System.Activities.Statements.Interop> non è supportato con l'attendibilità parziale.

2. I flussi di lavoro in esecuzione con attendibilità parziale in <xref:System.ServiceModel.WorkflowServiceHost> non sono supportati.

3. Rendere persistenti le eccezioni in uno scenario parzialmente attendibile rappresenta una potenziale minaccia alla sicurezza. Per disabilitare la persistenza delle eccezioni, un'estensione di tipo <xref:System.Activities.ExceptionPersistenceExtension> deve essere aggiunta al progetto per rifiutare la memorizzazione delle eccezioni. Nell'esempio di codice riportato di seguito viene illustrato come implementare questo tipo.

    ```csharp
    public class ExceptionPersistenceExtension
    {
        public ExceptionPersistenceExtension()
        {
            this.PersistExceptions = false;
        }
        public bool PersistExceptions { get; set; }
    }
    ```

     Se le eccezioni non devono essere serializzate, assicurarsi che le eccezioni vengano usate all'interno di <xref:System.Activities.Statements.NoPersistScope>.

4. Gli autori di attività devono eseguire l'override <xref:System.Activities.Activity.CacheMetadata%2A> per evitare che il runtime del flusso di lavoro esegua automaticamente la reflection per questo tipo. Gli argomenti e le attività figlio devono essere non Null e <xref:System.Activities.ActivityMetadata.Bind%2A> deve essere chiamato in modo esplicito. For more information on overriding <xref:System.Activities.Activity.CacheMetadata%2A>, see [Exposing data with CacheMetadata](exposing-data-with-cachemetadata.md). Also, instances of arguments that are of a type that is `internal` or **private** must be explicitly created in  <xref:System.Activities.Activity.CacheMetadata%2A> to avoid being created by reflection.

5. I tipi non utilizzeranno <xref:System.Runtime.Serialization.ISerializable> o <xref:System.SerializableAttribute> per la serializzazione; i tipi che devono essere serializzati devono supportare <xref:System.Runtime.Serialization.DataContractSerializer>.

6. Le espressioni che usano <xref:System.Activities.Expressions.LambdaValue%601> richiedono <xref:System.Security.Permissions.ReflectionPermissionAttribute.RestrictedMemberAccess%2A>e non funzioneranno con attendibilità parziale. I flussi di lavoro che usano <xref:System.Activities.Expressions.LambdaValue%601> sostituiscono le espressioni con le attività che derivano da <xref:System.Activities.CodeActivity%601>. .

7. Le espressioni non possono essere compilate usando <xref:System.Activities.XamlIntegration.TextExpressionCompiler> o il compilatore ospitato di Visual Basic in attendibilità parziale, ma le espressioni precedentemente compilate possono essere eseguite.

8. A single assembly that uses [Level 2 Transparency](https://aka.ms/Level2Transparency) cannot be used in .NET Framework 4, [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] in full trust, and [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] in partial trust.

## <a name="BKMK_NewDesignerCapabilites"></a> New Designer Capabilities

### <a name="BKMK_DesignerSearch"></a> Designer Search

Per rendere più gestibili i flussi di lavoro di grandi dimensioni, è ora possibile effettuarvi ricerche in base a parole chiave. This feature is only available in Visual Studio; this feature is not available in a rehosted designer. Sono disponibili due tipi di ricerche:

- Quick Find, initiated with either **Ctrl+F** or **Edit**, **Find and Replace**, **Quick Find**.

- Find in Files, initiated with either **Ctrl+Shift+F** or **Edit**, **Find and Replace**, **Find in Files**.

Si noti che la sostituzione non è supportata.

#### <a name="BKMK_QuickFind"></a> Quick Find

Le parole chiave ricercate nei flussi di lavoro corrisponderanno agli elementi delle finestre di progettazione seguenti:

- Proprietà degli oggetti <xref:System.Activities.Activity>, <xref:System.Activities.Statements.FlowNode>, <xref:System.Activities.Statements.State> e <xref:System.Activities.Statements.Transition>, nonché altri elementi di controllo del flusso personalizzati.

- Variabili

- argomenti

- Espressioni

La ricerca veloce viene effettuata nell'albero <xref:System.Activities.Presentation.Model.ModelItem> della finestra di progettazione. Con la ricerca veloce non verranno individuati gli spazi dei nomi importati nella definizione del flusso di lavoro.

#### <a name="BKMK_FindInFiles"></a> Find in Files

Le parole chiave ricercate nei flussi di lavoro corrisponderanno al contenuto effettivo dei file del flusso di lavoro. I risultati della ricerca verranno mostrati nel riquadro di visualizzazione Risultati ricerca di Visual Studio. Facendo doppio clic sull'elemento del risultato verrà visualizzata l'attività contenente la corrispondenza nella finestra di progettazione del flusso di lavoro.

### <a name="BKMK_VariableDeleteContextMenu"></a> Delete context menu item in variable and argument designer

In .NET Framework 4, variables and arguments could only be deleted in the designer using the keyboard. Starting with .NET Framework 4.5, variables and arguments can be deleted using the context menu.

Nella schermata seguente è illustrato il menu di scelta rapida della finestra di progettazione delle variabili e degli argomenti.

![Menu di scelta rapida della finestra di progettazione argomenti e variabili](./media/whats-new-in-wf-in-dotnet/designer-context-menu.png)

### <a name="BKMK_AutoSurround"></a> Auto-surround with Sequence

Poiché un flusso di lavoro o determinate attività contenitore (ad esempio <xref:System.Activities.Statements.NoPersistScope>) potevano contenere solo un'unica attività Body, l'aggiunta di una seconda attività richiedeva allo sviluppatore di eliminare la prima attività, di aggiungere un'attività <xref:System.Activities.Statements.Sequence> e, successivamente, di aggiungere entrambe le attività all'attività Sequence. Starting with .NET Framework 4.5, when adding a second activity to the designer surface, a `Sequence` activity will be automatically created to wrap both activities.

La schermata riportata di seguito mostra un'attività di `WriteLine` in `Body` di `NoPersistScope`.

![A WriteLine activity in the Body of a NoPersistScope activity.](./media/whats-new-in-wf-in-dotnet/auto-surround-write-line-activity.png)

La schermata riportata di seguito mostra l'attività automaticamente creata di `Sequence` in `Body` quando un secondo `WriteLine` viene rilasciato sotto il primo.

![An automatically created Sequence in the Body of a NoPersistScope.](./media/whats-new-in-wf-in-dotnet/auto-surround-sequence-activity.png)

### <a name="BKMK_PanMode"></a> Pan Mode

Per spostarsi più facilmente in un flusso di lavoro di grandi dimensioni nella finestra di progettazione è possibile abilitare la modalità dettaglio, consentendo allo sviluppatore di selezionare e trascinare la parte visibile del flusso di lavoro, anziché dover usare le barre di scorrimento. Il pulsante per attivare la modalità dettaglio si trova nell'angolo inferiore destro della finestra di progettazione.

Nella schermata seguente viene illustrato il pulsante della modalità dettaglio posizionato nell'angolo inferiore destro della finestra di progettazione del flusso di lavoro.

![The pan button highlighted in the workflow designer.](./media/whats-new-in-wf-in-dotnet/pan-button-workflow-designer.png)

Per ottenere il dettaglio della finestra di progettazione del flusso di lavoro è anche possibile usare il pulsante centrale del mouse o la barra spaziatrice.

### <a name="BKMK_MultiSelect"></a> Multi-select

È possibile selezionare più attività alla volta trascinando un rettangolo attorno a esse (quando la modalità dettaglio non è abilitata) o tenendo premuto CTRL e facendo clic sulle attività desiderate una alla volta.

Le selezioni di più attività possono anche essere trascinate e rilasciate all'interno della finestra di progettazione, nonché usate con il menu di scelta rapida.

### <a name="BKMK_DocumentOutline"></a> Outline view of workflow items

Per consentire uno spostamento più semplice nei flussi di lavoro gerarchici, i componenti di un flusso di lavoro vengono visualizzati in una visualizzazione ad albero. The outline view is displayed in the **Document Outline** view. To open this view, from the top menu, select **View**, **Other Windows**, **Document Outline**, or press Ctrl W,U. Facendo clic su un nodo nella visualizzazione Struttura verrà visualizzata l'attività corrispondente nella finestra di progettazione del flusso di lavoro e la visualizzazione Struttura verrà aggiornata in modo da mostrare le attività selezionate nella finestra di progettazione.

The following screenshot of the completed workflow from the [Getting Started Tutorial](getting-started-tutorial.md) shows the outline view with a sequential workflow.

![Screenshot of outline view with a sequential workflow in Visual Studio.](./media/whats-new-in-wf-in-dotnet/outline-view-in-workflow-designer.jpg)

### <a name="BKMK_CSharpExpressions"></a> C# Expressions

Prior to .NET Framework 4.5, all expressions in workflows could only be written in Visual Basic. In .NET Framework 4.5, Visual Basic expressions are only used for projects created using Visual Basic. Nei progetti Visual C# viene ora usato C# per le espressioni. È ora disponibile un editor espressioni C# completamente funzionale con funzionalità quali l'evidenziazione della grammatica e Intellisense. I progetti di flussi di lavoro C# creati in versioni precedenti che utilizzavano espressioni di Visual Basic continueranno a funzionare.

Le espressioni C# vengono convalidate in fase di progettazione. Gli errori nelle espressioni C# verranno contrassegnati con una sottolineatura ondulata rossa.

For more information about C# expressions, see [C# Expressions](csharp-expressions.md).

### <a name="BKMK_Visibility"></a> More control of visibility of shell bar and header items

In una finestra di progettazione ospitata nuovamente, alcuni dei controlli dell'interfaccia utente standard possono non essere appropriati per un determinato flusso di lavoro e, pertanto, è possibile disattivarli. In .NET Framework 4, this customization is only supported by the shell bar at the bottom of the designer. In .NET Framework 4.5, the visibility of shell header items at the top of the designer can be adjusted by setting <xref:System.Activities.Presentation.View.DesignerView.WorkflowShellHeaderItemsVisibility%2A> with the appropriate <xref:System.Activities.Presentation.View.ShellHeaderItemsVisibility> value.

### <a name="BKMK_AutoConnect"></a> Auto-connect and auto-insert in Flowchart and State Machine workflows

In .NET Framework 4, connections between nodes in a Flowchart workflow had to be added manually. In .NET Framework 4.5, Flowchart and State Machine nodes have auto-connect points that become visible when an activity is dragged from the toolbox onto the designer surface. Rilasciando un'attività in uno di questi punti, viene automaticamente aggiunta insieme alla connessione necessaria.

Nella schermata seguente vengono illustrati i punti di associazione che diventano visibili quando un'attività viene trascinata dalla casella degli strumenti.

![Flowchart start node showing auto-connect points](./media/whats-new-in-wf-in-dotnet/auto-connect-points-start-node.png)

Le attività possono anche essere trascinate nelle connessioni tra i nodi e gli stati del diagramma di flusso per inserire automaticamente un nodo tra altri due. Nella schermata seguente viene illustrata la linea di connessione evidenziata in cui è possibile trascinare e rilasciare le attività dalla casella degli strumenti.

![Handle di inserimento automatico per il trascinamento delle attività](./media/whats-new-in-wf-in-dotnet/auto-insert-connecting-line.png)

### <a name="BKMK_Annotations"></a> Designer Annotations

Per semplificare lo sviluppo di flussi di lavoro di grandi dimensioni, la finestra di progettazione supporta ora l'aggiunta di annotazioni per consentire di tenere traccia del processo di progettazione. Le annotazioni possono essere aggiunte ad attività, stati, nodi del diagramma di flusso, variabili e argomenti. Nella schermata seguente è illustrato il menu di scelta rapida usato per aggiungere annotazioni alla finestra di progettazione.

![Screenshot showing a menu for adding annotations.](./media/whats-new-in-wf-in-dotnet/designer-annotations-context-menu.png)

### <a name="debugging-states"></a>Stati di debug

In .NET Framework 4, non-activity elements could not support debug breakpoints since they were not units of execution. Questa versione fornisce un meccanismo per aggiungere punti di interruzione agli oggetti <xref:System.Activities.Statements.State>. Se un punto di interruzione è impostato su un oggetto <xref:System.Activities.Statements.State>, l'esecuzione verrà interrotta quando viene eseguita la transizione dello stato, prima della pianificazione delle attività o dei trigger di inserimento.

### <a name="BKMK_ActivityDelegates"></a> Define and consume ActivityDelegate objects in the designer

Activities in .NET Framework 4 used <xref:System.Activities.ActivityDelegate> objects to expose execution points where other parts of the workflow could interact with a workflow's execution, but using these execution points usually required a fair amount of code. In questa versione gli sviluppatori possono definire e usare delegati di attività tramite la finestra di progettazione del flusso di lavoro. For more information, see [How to: Define and consume activity delegates in the Workflow Designer](/visualstudio/workflow-designer/how-to-define-and-consume-activity-delegates-in-the-workflow-designer).

### <a name="BKMK_BuildTimeValidation"></a> Build-time validation

In .NET Framework 4, workflow validation errors weren’t counted as build errors during the build of a workflow project. In questo modo, la compilazione di un progetto di flusso di lavoro poteva essere completata correttamente anche in presenza di errori di convalida del flusso di lavoro. In .NET Framework 4.5, workflow validation errors cause the build to fail.

### <a name="BKMK_DesignTimeValidation"></a> Design-time background validation

In .NET Framework 4, workflows were validated as a foreground process, which could potentially block the UI during complex or time-consuming validation processes. La convalida del flusso di lavoro viene ora effettuata in un thread in background, pertanto l'interfaccia utente non viene bloccata.

### <a name="BKMK_ViewState"></a> View state located in a separate location in XAML files

In .NET Framework 4, the view state information for a workflow is stored across the XAML file in many different locations. Questa condizione è poco pratica per gli sviluppatori che desiderano leggere direttamente i file XAML o scrivere codice per rimuovere le informazioni sullo stato di visualizzazione. In .NET Framework 4.5, the view state information in the XAML file is serialized as a separate element in the XAML file. Developers can easily locate and edit the view state information of an activity, or remove the view state altogether.

### <a name="BKMK_ExpressionExtensibility"></a> Expression extensibility

In .NET Framework 4.5, we provide a way for developers to create their own expression and expression authoring experience that can be plugged into the workflow designer.

### <a name="BKMK_BackwardCompatRehostedDesigner"></a> Opt-in for Workflow 4.5 features in rehosted designer

To preserve backward compatibility, some new features included in .NET Framework 4.5 are not enabled by default in the rehosted designer. In questo modo si garantisce che le applicazioni esistenti in cui viene usata la finestra di progettazione ospitata nuovamente non vengano interrotte in caso di aggiornamento alla versione più recente. Per abilitare le nuove funzionalità nella finestra di progettazione ospitata nuovamente, impostare la proprietà <xref:System.Activities.Presentation.DesignerConfigurationService.TargetFrameworkName%2A> su ".NET Framework 4.5" oppure impostare singoli membri dell'oggetto <xref:System.Activities.Presentation.DesignerConfigurationService> per abilitare singole funzionalità.

## <a name="BKMK_NewWFModels"></a> New Workflow Development Models

Oltre ai modelli di sviluppo dei flussi di lavoro del diagramma di flusso e sequenziale, in questa versione sono inclusi i flussi di lavoro macchina a stati e i servizi dei flussi di lavoro con priorità al contratto ("contract-first").

### <a name="BKMK_StateMachine"></a> State machine workflows

State machine workflows were introduced as part of the .NET Framework 4, version 4.0.1 in the [Microsoft .NET Framework 4 Platform Update 1](https://go.microsoft.com/fwlink/?LinkID=215092). In questo aggiornamento sono incluse numerose nuove classi e attività che hanno consentito agli sviluppatori di creare i flussi di lavoro macchina a stati. These classes and activities have been updated for .NET Framework 4.5. Gli aggiornamenti includono:

1. Possibilità di impostare punti di interruzione negli stati

2. Possibilità di copiare e incollare transizioni nella finestra di progettazione del flusso di lavoro

3. Supporto della finestra di progettazione per la creazione di transizioni con trigger condivisi

4. Attività usate per creare i flussi di lavoro macchina a stati, incluse <xref:System.Activities.Statements.StateMachine>, <xref:System.Activities.Statements.State> e <xref:System.Activities.Statements.Transition>

The following screenshot shows the completed state machine workflow from the [Getting Started Tutorial](getting-started-tutorial.md) step [How to: Create a State Machine Workflow](how-to-create-a-state-machine-workflow.md).

![Illustration that shows the completed state machine workflow.](./media/whats-new-in-wf-in-dotnet/complete-state-machine-workflow.jpg)

For more information on creating state machine workflows, see [State Machine Workflows](state-machine-workflows.md).

### <a name="BKMK_ContractFirst"></a> Contract-first workflow development

The contract-first workflow development tool allows the developer to design a contract in code first, then, with a few clicks in Visual Studio, automatically generate an activity template in the toolbox representing each operation. Queste attività vengono quindi usate per creare un flusso di lavoro che implementa le operazioni definite dal contratto. La finestra di progettazione del flusso di lavoro convaliderà il servizio di quest'ultimo per garantire che queste operazioni vengano implementate e che la firma del flusso di lavoro corrisponda a quella del contratto. Lo sviluppatore può inoltre associare un servizio del flusso di lavoro a una raccolta di contratti implementati. For more information on contract-first workflow service development, see [How to: Create a workflow service that consumes an existing service contract](how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md).

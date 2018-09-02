---
title: Utilizzo dell'attività di interoperabilità in un flusso di lavoro di .NET Framework 4
ms.date: 03/30/2017
ms.assetid: 9bb747f0-eb33-4f70-84cd-317382372dcd
ms.openlocfilehash: 02eeaf5bb7ff484ba5982197fc395e247cd5a87f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43466725"
---
# <a name="using-the-interop-activity-in-a-net-framework-4-workflow"></a>Utilizzo dell'attività di interoperabilità in un flusso di lavoro di .NET Framework 4
Le attività create tramite [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] o [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] possono essere usate nel flusso di lavoro di [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] mediante l'attività <xref:System.Activities.Statements.Interop>. In questo argomento viene fornita una panoramica sull'utilizzo dell'attività <xref:System.Activities.Statements.Interop>.  
  
> [!NOTE]
>  Il <xref:System.Activities.Statements.Interop> attività non viene visualizzato nella casella degli strumenti della finestra di progettazione del flusso di lavoro a meno che non dispone di progetto del flusso di lavoro relativi **Framework di destinazione** impostazione **.Net Framework 4** o versione successiva.  
  
## <a name="using-the-interop-activity-in-net-framework-45-workflows"></a>Utilizzo dell'attività di interoperabilità nei flussi di lavoro di .NET Framework 4.5  
 In questo argomento viene creata una libreria di attività di [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] contenente un'attività `DiscountCalculator`. `DiscountCalculator` consente di calcolare uno sconto in base a un importo di acquisto ed è costituita da un oggetto <xref:System.Workflow.Activities.SequenceActivity> contenente un oggetto <xref:System.Workflow.Activities.PolicyActivity>.  
  
> [!NOTE]
>  L'attività di [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] creata in questo argomento usa un oggetto <xref:System.Workflow.Activities.PolicyActivity> per implementare la logica dell'attività. Non è necessario usare un'attività [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] personalizzata o l'attività <xref:System.Activities.Statements.Interop> per sfruttare le regole in un flusso di lavoro di [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]. Per un esempio di utilizzo delle regole in un [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] flusso di lavoro senza utilizzare il <xref:System.Activities.Statements.Interop> attività, vedere la [attività Policy in .NET Framework 4.5](../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) esempio.  
  
#### <a name="to-create-the-net-framework-35-activity-library-project"></a>Per creare il progetto della libreria di attività di .NET Framework 3.5  
  
1.  Aprire [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] e selezionare **New** e quindi **progetto...** dal **File** menu.  
  
2.  Espandere la **altri tipi di progetto** nodo il **modelli installati** riquadro e selezionare **soluzioni di Visual Studio**.  
  
3.  Selezionare **soluzione vuota** dalle **soluzioni di Visual Studio** elenco. Tipo di `PolicyInteropDemo` nella **Name** casella e fare clic su **OK**.  
  
4.  Fare doppio clic su **PolicyInteropDemo** nelle **Esplora soluzioni** e selezionare **Add** e quindi **nuovo progetto...** .  
  
    > [!TIP]
    >  Se il **Esplora soluzioni** finestra non è visibile, selezionarla **Esplora soluzioni** dal **visualizzazione** menu.  
  
5.  Nel **modelli installati** elenco, selezionare **Visual c#** e quindi **flusso di lavoro**. Selezionare **.NET Framework 3.5** dall'elenco di riepilogo a discesa versioni di .NET Framework e quindi selezionare **Workflow Activity Library** dal **modelli** elenco.  
  
6.  Tipo di `PolicyActivityLibrary` nella **Name** casella e fare clic su **OK**.  
  
7.  Fare doppio clic su **Activity1.cs** nelle **Esplora soluzioni** e selezionare **Elimina**. Per confermare scegliere **OK** .  
  
#### <a name="to-create-the-discountcalculator-activity"></a>Per creare l'attività DiscountCalculator  
  
1.  Fare doppio clic su **PolicyActivityLibrary** nelle **Esplora soluzioni** e selezionare **Add** e quindi **attività...** .  
  
2.  Selezionare **attività (con separazione del codice)** dalle **elementi di Visual c#** elenco. Tipo di `DiscountCalculator` nella **Name** casella e fare clic su **OK**.  
  
3.  Fare doppio clic su **discountcalculator. xoml** nelle **Esplora soluzioni** e selezionare **Visualizza codice**.  
  
4.  Aggiungere le tre seguenti proprietà alla classe `DiscountCalculator`.  
  
    ```csharp  
    public partial class DiscountCalculator : SequenceActivity  
    {  
        public double Subtotal { get; set; }  
        public double DiscountPercent { get; set; }  
        public double Total { get; set; }  
    }  
    ```  
  
5.  Fare doppio clic su **discountcalculator. xoml** nelle **Esplora soluzioni** e selezionare **Progettazione viste**.  
  
6.  Trascinare un **criteri** attività dal **Windows Workflow v3.0** sezione del **della casella degli strumenti** e rilasciarla nel **DiscountCalculator** attività .  
  
    > [!TIP]
    >  Se il **casella degli strumenti** finestra non è visibile, selezionarla **della casella degli strumenti** dal **visualizzazione** menu.  
  
#### <a name="to-configure-the-rules"></a>Per configurare le regole  
  
1.  Fare clic su appena aggiunta **criteri** attività per selezionarlo, se non è già selezionato.  
  
2.  Fare clic sul **RuleSetReference** proprietà di **proprietà** finestra per selezionarla e fare clic sul pulsante con puntini di sospensione a destra della proprietà.  
  
    > [!TIP]
    >  Se il **delle proprietà** finestra non è visibile, scegliere **finestra delle proprietà** dal **visualizzazione** menu.  
  
3.  Selezionare **fare clic su nuova...** .  
  
4.  Fare clic su **Aggiungi regola**.  
  
5.  Digitare l'espressione seguente nella **condizione** casella.  
  
    ```  
    this.Subtotal >= 50 && this.Subtotal < 100  
    ```  
  
6.  Digitare l'espressione seguente nella **azioni Then** casella.  
  
    ```  
    this.DiscountPercent = 0.075  
    ```  
  
7.  Fare clic su **Aggiungi regola**.  
  
8.  Digitare l'espressione seguente nella **condizione** casella.  
  
    ```  
    this.Subtotal >= 100  
    ```  
  
9. Digitare l'espressione seguente nella **azioni Then** casella.  
  
    ```  
    this.DiscountPercent = 0.15  
    ```  
  
10. Fare clic su **Aggiungi regola**.  
  
11. Digitare l'espressione seguente nella **condizione** casella.  
  
    ```  
    this.DiscountPercent > 0  
    ```  
  
12. Digitare l'espressione seguente nella **azioni Then** casella.  
  
    ```  
    this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent  
    ```  
  
13. Digitare l'espressione seguente nella **azioni Else** casella.  
  
    ```  
    this.Total = this.Subtotal  
    ```  
  
14. Fare clic su **OK** per chiudere la **Editor Set di regole** nella finestra di dialogo.  
  
15. Assicurarsi che appena creato <xref:System.Workflow.Activities.Rules.RuleSet> sia selezionato nel **Name** elenco e fare clic su **OK**.  
  
16. Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
 Le regole aggiunte all'attività `DiscountCalculator` in questa procedura vengono mostrate nell'esempio di codice seguente.  
  
```  
Rule1: IF this.Subtotal >= 50 && this.Subtotal < 100   
       THEN this.DiscountPercent = 0.075   
  
Rule2: IF this. Subtotal >= 100   
       THEN this.DiscountPercent = 0.15   
  
Rule3: IF this.DiscountPercent > 0   
       THEN this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent   
       ELSE this.Total = this.Subtotal  
```  
  
 Quando l'oggetto <xref:System.Workflow.Activities.PolicyActivity> viene eseguito, queste tre regole valutano e modificano i valori delle proprietà `Subtotal`, `DiscountPercent` e `Total` dell'attività `DiscountCalculator` per calcolare lo sconto desiderato.  
  
## <a name="using-the-discountcalculator-activity-with-the-interop-activity"></a>Utilizzo dell'attività DiscountCalculator con l'attività di interoperabilità  
 Per usare l'attività `DiscountCalculator` in un flusso di lavoro di [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], viene usata l'attività <xref:System.Activities.Statements.Interop>. Contenuto della sezione vengono creati due flussi di lavoro (in uno viene usato il codice e nell'altro la relativa utilità di progettazione) che illustrano come usare l'attività <xref:System.Activities.Statements.Interop> con l'attività `DiscountCalculator`. In entrambi i flussi di lavoro viene usata la stessa applicazione host.  
  
#### <a name="to-create-the-host-application"></a>Per creare l'applicazione host  
  
1.  Fare doppio clic su **PolicyInteropDemo** nelle **Esplora soluzioni** e selezionare **Add**e quindi **nuovo progetto...** .  
  
2.  Assicurarsi che **.NET Framework 4.5** sia selezionato nell'elenco a discesa versione .NET Framework e selezionare **applicazione Console flusso di lavoro** dal **elementi di Visual c#** elenco.  
  
3.  Tipo di `PolicyInteropHost` nella **Name** casella e fare clic su **OK**.  
  
4.  Fare doppio clic su **PolicyInteropHost** nelle **Esplora soluzioni** e selezionare **proprietà**.  
  
5.  Nel **framework di destinazione** elenco a discesa elenco, modificare la selezione dalla **.NET Framework 4 Client Profile** al **.NET Framework 4.5**. Fare clic su **Sì** per confermare.  
  
6.  Fare doppio clic su **PolicyInteropHost** nelle **Esplora soluzioni** e selezionare **Aggiungi riferimento...** .  
  
7.  Selezionare **PolicyActivityLibrary** dalle **progetti** scheda e fare clic su **OK**.  
  
8.  Fare doppio clic su **PolicyInteropHost** nelle **Esplora soluzioni** e selezionare **Aggiungi riferimento...** .  
  
9. Selezionare **System.Workflow.Activities**, **ComponentModel**e quindi **System.Workflow.Runtime** dal **.NET**scheda e fare clic su **OK**.  
  
10. Fare doppio clic su **PolicyInteropHost** nelle **Esplora soluzioni** e selezionare **imposta come progetto di avvio**.  
  
11. Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
### <a name="using-the-interop-activity-in-code"></a>Utilizzo dell'attività di interoperabilità nel codice  
 In questo esempio viene creata una definizione di flusso di lavoro tramite il codice contenente le attività <xref:System.Activities.Statements.Interop> e `DiscountCalculator`. Questo flusso di lavoro viene richiamato usando l'oggetto <xref:System.Activities.WorkflowInvoker> e i risultati della valutazione della regola vengono scritti nella console tramite un'attività <xref:System.Activities.Statements.WriteLine>.  
  
##### <a name="to-use-the-interop-activity-in-code"></a>Per usare l'attività di interoperabilità nel codice  
  
1.  Fare doppio clic su **Program.cs** nelle **Esplora soluzioni** e selezionare **Visualizza codice**.  
  
2.  Aggiungere la seguente istruzione `using` all'inizio del file.  
  
    ```csharp  
    using PolicyActivityLibrary;  
    ```  
  
3.  Rimuovere il contenuto del metodo `Main` e sostituirlo con il codice riportato di seguito.  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
4.  Creare un nuovo metodo nella classe `Program` denominato `CalculateDiscountUsingCodeWorkflow` contenente il codice seguente.  
  
    ```csharp  
    static void CalculateDiscountUsingCodeWorkflow()  
    {  
        Variable<double> Subtotal = new Variable<double>  
        {  
            Default = 75.99,  
            Name = "Subtotal"  
        };  
  
        Variable<double> DiscountPercent = new Variable<double>  
        {  
            Name = "DiscountPercent"  
        };  
  
        Variable<double> Total = new Variable<double>  
        {  
            Name = "Total"  
        };  
  
        Activity wf = new Sequence  
        {  
            Variables = { Subtotal, DiscountPercent, Total },  
            Activities =   
            {  
                new Interop  
                {  
                    ActivityType = typeof(DiscountCalculator),  
                    ActivityProperties =   
                    {  
                        { "Subtotal", new InArgument<double>(Subtotal) },  
                        { "DiscountPercentOut", new OutArgument<double>(DiscountPercent) },  
                        { "TotalOut", new OutArgument<double>(Total) }  
                    }  
                },  
                new WriteLine  
                {  
                    Text =  new InArgument<string>(env =>   
                        string.Format("Subtotal: {0:C}, Discount {1}%, Total {2:C}",   
                        Subtotal.Get(env), DiscountPercent.Get(env) * 100, Total.Get(env)))  
                }  
            }  
        };  
  
        WorkflowInvoker.Invoke(wf);  
    }  
    ```  
  
    > [!NOTE]
    >  Le proprietà `Subtotal`, `DiscountPercent` e `Total` dell'attività `DiscountCalculator` vengono rilevate come argomenti dell'attività <xref:System.Activities.Statements.Interop> e associate a variabili del flusso di lavoro locali nella raccolta <xref:System.Activities.Statements.Interop> dell'attività <xref:System.Activities.Statements.Interop.ActivityProperties%2A>. `Subtotal` viene aggiunto come argomento di <xref:System.Activities.ArgumentDirection.In> in quanto i dati di `Subtotal` fluiscono nell'attività <xref:System.Activities.Statements.Interop>; `DiscountPercent` e `Total` vengono aggiunti come argomenti di <xref:System.Activities.ArgumentDirection.Out> in quanto i relativi dati escono dall'attività <xref:System.Activities.Statements.Interop>. Si noti che i due argomenti <xref:System.Activities.ArgumentDirection.Out> vengono aggiunti con i nomi `DiscountPercentOut` e `TotalOut` per indicare che rappresentano gli argomenti <xref:System.Activities.ArgumentDirection.Out>. Il tipo `DiscountCalculator` viene specificato come proprietà <xref:System.Activities.Statements.Interop> dell'attività <xref:System.Activities.Statements.Interop.ActivityType%2A>.  
  
5.  Premere CTRL+F5 per compilare ed eseguire l'applicazione. Sostituire i diversi valori per il valore `Subtotal` al fine di testare i numerosi livelli di sconto forniti dall'attività `DiscountCalculator`.  
  
    ```csharp  
    Variable<double> Subtotal = new Variable<double>  
    {  
        Default = 75.99, // Change this value.  
        Name = "Subtotal"  
    };  
    ```  
  
### <a name="using-the-interop-activity-in-the-workflow-designer"></a>Utilizzo dell'attività di interoperabilità nell'utilità di progettazione del flusso di lavoro  
 In questo esempio viene creato un flusso di lavoro tramite l'utilità di progettazione del flusso di lavoro. Questo flusso di lavoro dispone della stessa funzionalità descritta nell'esempio precedente, tuttavia anziché usare un'attività <xref:System.Activities.Statements.WriteLine> per visualizzare lo sconto, l'applicazione host recupera e visualizza le informazioni sullo sconto quando il flusso di lavoro viene completato. Inoltre, invece di usare le variabili del flusso di lavoro locale per contenere i dati, gli argomenti vengono creati nell'utilità di progettazione del flusso di lavoro e i valori vengono passati dall'host quando il flusso di lavoro viene richiamato.  
  
##### <a name="to-host-the-policyactivity-using-a-workflow-designer-created-workflow"></a>Per ospitare PolicyActivity usando un flusso di lavoro creato tramite la relativa utilità di progettazione  
  
1.  Fare doppio clic su **Workflow1.xaml** nelle **Esplora soluzioni** e selezionare **Elimina**. Per confermare scegliere **OK** .  
  
2.  Fare doppio clic su **PolicyInteropHost** nelle **Esplora soluzioni** e selezionare **Add**, **nuovo elemento...** .  
  
3.  Espandere la **elementi di Visual c#** nodo e selezionare **flusso di lavoro**. Selezionare **impegno** dalle **elementi di Visual c#** elenco.  
  
4.  Tipo di `DiscountWorkflow` nella **Name** casella e fare clic su **Add**.  
  
5.  Fare clic sui **argomenti** pulsante sul lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare i **argomenti** riquadro.  
  
6.  Fare clic su **Crea argomento**.  
  
7.  Tipo `Subtotal` nella **nome** , quindi selezionare **nel** dal **direzione** elenco a discesa, selezionare **Double** dalla **Tipo di argomento** elenco a discesa e quindi premere INVIO per salvare l'argomento.  
  
    > [!NOTE]
    >  Se **doppie** non è nel **tipo di argomento** elenco a discesa, seleziona **Cerca tipi...** , tipo `System.Double` nel **nome del tipo** , quindi scegliere **OK**.  
  
8.  Fare clic su **Crea argomento**.  
  
9. Tipo di `DiscountPercent` nella **nome** , quindi selezionare **Out** dal **direzione** elenco a discesa, selezionare **Double** dalla **Tipo di argomento** elenco a discesa e quindi premere INVIO per salvare l'argomento.  
  
10. Fare clic su **Crea argomento**.  
  
11. Tipo di `Total` nella **nome** , quindi selezionare **Out** dal **direzione** elenco a discesa, selezionare **Double** dalla **Tipo di argomento** elenco a discesa e quindi premere INVIO per salvare l'argomento.  
  
12. Scegliere il **argomenti** pulsante sul lato inferiore sinistro della finestra di progettazione del flusso di lavoro per chiudere il **argomenti** riquadro.  
  
13. Trascinare un **sequenza** attività dalle **flusso di controllo** sezione del **della casella degli strumenti** e rilasciarlo nell'area di progettazione del flusso di lavoro.  
  
14. Trascinare un' **interoperabilità** attività dal **migrazione** sezione del **della casella degli strumenti** e rilasciarla nel **sequenza** attività.  
  
15. Fare clic sui **Interop** attività nel **fare clic per cercare...** assegnare un'etichetta, digitare **DiscountCalculator** nel **nome del tipo** , quindi scegliere **OK**.  
  
    > [!NOTE]
    >  Quando l'attività <xref:System.Activities.Statements.Interop> viene aggiunta al flusso di lavoro e il tipo `DiscountCalculator` viene specificato come la relativa proprietà <xref:System.Activities.Statements.Interop.ActivityType%2A>, l'attività <xref:System.Activities.Statements.Interop> espone tre argomenti <xref:System.Activities.ArgumentDirection.In> e tre argomenti <xref:System.Activities.ArgumentDirection.Out> che rappresentano le tre proprietà pubbliche dell'attività `DiscountCalculator`. Il <xref:System.Activities.ArgumentDirection.In> argomenti hanno lo stesso nome, le tre proprietà pubbliche e i tre <xref:System.Activities.ArgumentDirection.Out> gli argomenti hanno gli stessi nomi utilizzando **Out** accodato al nome della proprietà. Nei passaggi seguenti gli argomenti del flusso di lavoro creati in precedenza vengono associati agli argomenti dell'attività <xref:System.Activities.Statements.Interop>.  
  
16. Tipo `DiscountPercent` nella **immettere un'espressione VB** a destra della finestra di **DiscountPercentOut** proprietà e premere TAB.  
  
17. Tipo `Subtotal` nella **immettere un'espressione VB** a destra della finestra di **Subtotal** proprietà e premere TAB.  
  
18. Tipo `Total` nella **immettere un'espressione VB** a destra della finestra di **TotalOut** proprietà e premere TAB.  
  
19. Fare doppio clic su **Program.cs** nelle **Esplora soluzioni** e selezionare **Visualizza codice**.  
  
20. Aggiungere la seguente istruzione `using` all'inizio del file.  
  
    ```csharp  
    using System.Collections.Generic;  
    ```  
  
21. Impostare come commento la chiamata al metodo `CalculateDiscountInCode` nel metodo `Main` e aggiungere il codice seguente.  
  
    > [!NOTE]
    >  Se non è stata seguita la procedura precedente e il codice `Main` predefinito è presente, sostituire il contenuto di `Main` con il codice seguente.  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingDesignerWorkflow();  
        //CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
22. Creare un nuovo metodo nella classe `Program` denominato `CalculateDiscountUsingDesignerWorkflow` contenente il codice seguente.  
  
    ```csharp  
    static void CalculateDiscountUsingDesignerWorkflow()  
    {  
        double SubtotalValue = 125.99;  
        Dictionary<string, object> wfargs = new Dictionary<string, object>  
        {  
            {"Subtotal", SubtotalValue}  
        };  
  
        Activity wf = new DiscountWorkflow();  
  
        IDictionary<string, object> outputs =  
            WorkflowInvoker.Invoke(wf, wfargs);  
  
        Console.WriteLine("Subtotal: {0:C}, Discount {1}%, Total {2:C}",  
            SubtotalValue, (double)outputs["DiscountPercent"] * 100,  
            outputs["Total"]);  
    }  
    ```  
  
23. Premere CTRL+F5 per compilare ed eseguire l'applicazione. Per specificare un importo `Subtotal` diverso, modificare il valore di `SubtotalValue` nel codice seguente.  
  
    ```csharp  
    double SubtotalValue = 125.99; // Change this value.  
    ```  
  
## <a name="rules-features-overview"></a>Panoramica sulle funzionalità delle regole  
 Il motore di regole in [!INCLUDE[wf1](../../../includes/wf1-md.md)] facilita l'elaborazione di regole basata sulla priorità con supporto del concatenamento diretto. Le regole possono essere valutate per un singolo elemento o per gli elementi di una raccolta. Per una panoramica sulle regole e per informazioni sulla funzionalità di regole specifiche, fare riferimento alla tabella seguente.  
  
|Funzionalità delle regole|Documentazione|  
|-------------------|-------------------|  
|Panoramica sulle regole|[Introduzione al motore regole di Windows Workflow Foundation](https://go.microsoft.com/fwlink/?LinkID=152836)|  
|RuleSet|[Utilizzo di RuleSet in flussi di lavoro](https://go.microsoft.com/fwlink/?LinkId=178516) e <xref:System.Workflow.Activities.Rules.RuleSet>|  
|Valutazione delle regole|[Valutazione delle regole di RuleSet](https://go.microsoft.com/fwlink/?LinkId=178517)|  
|Concatenamento di regole|[Controllo del concatenamento](https://go.microsoft.com/fwlink/?LinkId=178518) e [concatenamento diretto di regole](https://go.microsoft.com/fwlink/?LinkId=178519)|  
|Elaborazione di raccolte nelle regole|[L'elaborazione di raccolte nelle regole](https://go.microsoft.com/fwlink/?LinkId=178520)|  
|Utilizzo dell'attività PolicyActivity|[Utilizzo dell'attività PolicyActivity](https://go.microsoft.com/fwlink/?LinkId=178521) e <xref:System.Workflow.Activities.PolicyActivity>|  
  
 I flussi di lavoro creati in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] non usano tutte le funzionalità delle regole fornite da [!INCLUDE[wf1](../../../includes/wf1-md.md)], ad esempio le condizioni di attività dichiarative e le attività condizionali quali <xref:System.Workflow.Activities.ConditionedActivityGroup> e <xref:System.Workflow.Activities.ReplicatorActivity>. Se necessario, questa funzionalità è disponibile per i flussi di lavoro creati tramite [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] e [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]. Per altre informazioni, vedere [materiale sussidiario di migrazione](../../../docs/framework/windows-workflow-foundation/migration-guidance.md).

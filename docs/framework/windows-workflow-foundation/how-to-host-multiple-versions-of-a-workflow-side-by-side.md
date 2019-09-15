---
title: 'Procedura: Ospitare più versioni di un flusso di lavoro side-by-side'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 09c575df-e0a3-4f3b-9e01-a7ac59d65287
ms.openlocfilehash: 820ed324c8095e2f9f2823513a37965099f42c48
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989642"
---
# <a name="how-to-host-multiple-versions-of-a-workflow-side-by-side"></a>Procedura: Ospitare più versioni di un flusso di lavoro side-by-side

`WorkflowIdentity` offre agli sviluppatori di applicazioni flusso di lavoro un modo per associare un nome e una versione a una definizione del flusso di lavoro. Consente inoltre di associare queste informazioni a un'istanza persistente del flusso di lavoro. Queste informazioni di identità possono essere usate dagli sviluppatori di applicazioni flusso di lavoro per scenari quali l'esecuzione affiancata di più versioni di una definizione del flusso di lavoro e costituiscono un elemento fondamentale per altre funzionalità come l'aggiornamento dinamico. In questo passaggio dell'esercitazione viene illustrato come usare `WorkflowIdentity` per ospitare più versioni di un flusso di lavoro contemporaneamente.

> [!NOTE]
> Per scaricare una versione completa o visualizzare una procedura dettagliata del video dell'esercitazione, vedere [Windows Workflow Foundation (WF45)-Introduzione esercitazione](https://go.microsoft.com/fwlink/?LinkID=248976).

## <a name="in-this-topic"></a>Contenuto dell'argomento

In questo passaggio dell'esercitazione, le attività di `WriteLine` nel flusso di lavoro vengono modificate per fornire informazioni aggiuntive e viene aggiunta una nuova attività `WriteLine`. Una copia dell'assembly originale del flusso di lavoro viene archiviata e l'applicazione host viene aggiornata in modo da poter eseguire il flusso di lavoro originale e aggiornato contemporaneamente.

- [Per creare una copia del progetto NumberGuessWorkflowActivities](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BackupCopy)

- [Per aggiornare i flussi di lavoro](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflows)

  - [Per aggiornare il flusso di lavoro StateMachine](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateStateMachine)

  - [Per aggiornare il flusso di lavoro del diagramma di flusso](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateFlowchart)

  - [Per aggiornare il flusso di lavoro sequenziale](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateSequential)

- [Per aggiornare WorkflowVersionMap in modo da includere le versioni precedenti del flusso di lavoro](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflowVersionMap)

- [Per compilare ed eseguire l'applicazione](how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BuildAndRun)

> [!NOTE]
> Prima di effettuare i passaggi di questo argomento, eseguire l'applicazione, avviare diversi flussi di lavoro di ogni tipo ed effettuare uno o due tentativi per ciascuno di essi. Questi flussi di lavoro salvati in [modo permanente vengono usati in questo passaggio e nel passaggio seguente: Aggiornare la definizione di un'istanza](how-to-update-the-definition-of-a-running-workflow-instance.md)del flusso di lavoro in esecuzione.

> [!NOTE]
> Ogni passaggio nell'Esercitazione introduttiva dipende dai passaggi precedenti. Se non sono stati completati i passaggi precedenti, è possibile scaricare una versione completa dell'esercitazione da [Windows Workflow Foundation (WF45)-Introduzione esercitazione](https://go.microsoft.com/fwlink/?LinkID=248976).

### <a name="BKMK_BackupCopy"></a>Per creare una copia del progetto NumberGuessWorkflowActivities

1. Aprire la soluzione **WF45GettingStartedTutorial** in Visual Studio 2012 se non è aperta.

2. Per compilare la soluzione, premere CTRL+MAIUSC+B.

3. Chiudere la soluzione **WF45GettingStartedTutorial** .

4. Aprire Esplora risorse e passare alla cartella in cui si trova il file della soluzione di esercitazione e le cartelle del progetto.

5. Creare una nuova cartella denominata **PreviousVersions** nella stessa cartella di **NumberGuessWorkflowHost** e **NumberGuessWorkflowActivities**. Questa cartella è usata per contenere gli assembly che includono le diverse versioni dei flussi di lavoro usate nei passaggi successivi dell'esercitazione.

6. Passare alla cartella **NumberGuessWorkflowActivities\bin\debug** (o **bin\release** a seconda delle impostazioni del progetto). Copiare **NumberGuessWorkflowActivities. dll** e incollarlo nella cartella **PreviousVersions** .

7. Rinominare **NumberGuessWorkflowActivities. dll** nella cartella **PreviousVersions** in **NumberGuessWorkflowActivities_v1. dll**.

    > [!NOTE]
    > Nei passaggi di questo argomento viene illustrato un modo per gestire gli assembly usati per contenere più versioni dei flussi di lavoro. È anche possibile usare altri metodi, come l'assegnazione dei nomi sicuri agli assembly e la registrazione degli assembly nella Global Assembly Cache.

8. Creare una nuova cartella denominata **NumberGuessWorkflowActivities_du** nella stessa cartella di **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**e la cartella **PreviousVersions** appena aggiunta, quindi copiare tutti i file e sottocartelle dalla cartella **NumberGuessWorkflowActivities** nella nuova cartella **NumberGuessWorkflowActivities_du** . Questa copia di backup del progetto per la versione iniziale delle attività viene usata in [procedura: Aggiornare la definizione di un'istanza](how-to-update-the-definition-of-a-running-workflow-instance.md)del flusso di lavoro in esecuzione.

9. Riaprire la soluzione **WF45GettingStartedTutorial** in Visual Studio 2012.

### <a name="BKMK_UpdateWorkflows"></a>Per aggiornare i flussi di lavoro

Questa sezione aggiorna le definizioni di flusso di lavoro. Le due attività `WriteLine` che forniscono il feedback sul tentativo dell'utente vengono aggiornate e viene aggiunta una nuova attività `WriteLine` che fornisce informazioni aggiuntive sul gioco una volta determinato il numero.

#### <a name="BKMK_UpdateStateMachine"></a>Per aggiornare il flusso di lavoro StateMachine

1. In **Esplora soluzioni**, nel progetto **NumberGuessWorkflowActivities** , fare doppio clic su **StateMachineNumberGuessWorkflow. XAML**.

2. Fare doppio clic sulla transizione **Guess errato** sulla macchina a Stati.

3. Aggiornare l'oggetto `Text` di `WriteLine` all'estrema sinistra dell'attività `If`.

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

4. Aggiornare l'oggetto `Text` di `WriteLine` all'estrema destra dell'attività `If`.

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

5. Tornare alla visualizzazione complessiva della macchina a stati nella finestra di progettazione del flusso di lavoro facendo clic su **StateMachine** nella parte superiore della finestra di progettazione del flusso di lavoro.

6. Fare doppio clic sulla transizione **Guess Correct** nella macchina a Stati.

7. Trascinare un'attività **WriteLine** dalla sezione **primitive** della **casella degli strumenti** e rilasciarla sull'etichetta **rilasciare l'attività azione qui** della transizione.

8. Digitare l'espressione seguente nella casella della proprietà `Text`.

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

#### <a name="BKMK_UpdateFlowchart"></a>Per aggiornare il flusso di lavoro del diagramma di flusso

1. In **Esplora soluzioni**, nel progetto **NumberGuessWorkflowActivities** , fare doppio clic su **FlowchartNumberGuessWorkflow. XAML**.

2. Aggiornare l'oggetto `Text` dell'attività `WriteLine` all'estrema sinistra.

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

3. Aggiornare l'oggetto `Text` dell'attività `WriteLine` all'estrema destra.

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

4. Trascinare un'attività **WriteLine** dalla sezione **primitive** della **casella degli strumenti** e rilasciarla sul punto di rilascio dell' `True` azione del `FlowDecision`livello superiore. L'attività di `WriteLine` viene aggiunta al diagramma di flusso e collegata all'azione `True` di `FlowDecision`.

5. Digitare l'espressione seguente nella casella della proprietà `Text`.

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

#### <a name="BKMK_UpdateSequential"></a>Per aggiornare il flusso di lavoro sequenziale

1. In **Esplora soluzioni**, nel progetto **NumberGuessWorkflowActivities** , fare doppio clic su **SequentialNumberGuessWorkflow. XAML**.

2. Aggiornare l'oggetto `Text` di `WriteLine` all'estrema sinistra dell'attività `If`.

    ```vb
    Guess & " is too low."
    ```

    ```csharp
    Guess + " is too low."
    ```

3. Aggiornare l'oggetto `Text` dell'attività `WriteLine` all'estrema destra dell'attività `If`.

    ```vb
    Guess & " is too high."
    ```

    ```csharp
    Guess + " is too high."
    ```

4. Trascinare un'attività **WriteLine** dalla sezione **primitive** della **casella degli strumenti** e rilasciarla dopo l'attività **DoWhile** in modo che **WriteLine** sia l'attività finale nell'attività `Sequence` radice.

5. Digitare l'espressione seguente nella casella della proprietà `Text`.

    ```vb
    Guess & " is correct. You guessed it in " & Turns & " turns."
    ```

    ```csharp
    Guess + " is correct. You guessed it in " + Turns + " turns."
    ```

### <a name="BKMK_UpdateWorkflowVersionMap"></a>Per aggiornare WorkflowVersionMap in modo da includere le versioni precedenti del flusso di lavoro

1. Fare doppio clic su **WorkflowVersionMap.cs** (o **WorkflowVersionMap. vb**) nel progetto **NumberGuessWorkflowHost** per aprirlo.

2. Aggiungere le seguenti istruzioni `using` (o `Imports`) nella parte superiore del file con le altre istruzioni `using` (o `Imports`).

    ```vb
    Imports System.Reflection
    Imports System.IO
    ```

    ```csharp
    using System.Reflection;
    using System.IO;
    ```

3. Aggiungere tre nuove identità del flusso di lavoro subito dopo le tre dichiarazioni di identità del flusso di lavoro esistenti. Queste nuove identità del flusso di lavoro `v1` verranno usate per fornire la definizione corretta del flusso di lavoro ai flussi di lavoro avviati prima dell'applicazione degli aggiornamenti.

    ```vb
    'Current version identities.
    Public StateMachineNumberGuessIdentity As WorkflowIdentity
    Public FlowchartNumberGuessIdentity As WorkflowIdentity
    Public SequentialNumberGuessIdentity As WorkflowIdentity

    'v1 Identities.
    Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity
    Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity
    Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity
    ```

    ```csharp
    // Current version identities.
    static public WorkflowIdentity StateMachineNumberGuessIdentity;
    static public WorkflowIdentity FlowchartNumberGuessIdentity;
    static public WorkflowIdentity SequentialNumberGuessIdentity;

    // v1 identities.
    static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;
    static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;
    static public WorkflowIdentity SequentialNumberGuessIdentity_v1;
    ```

4. Nel costruttore `WorkflowVersionMap`, aggiornare la proprietà `Version` delle tre identità correnti del flusso di lavoro a `2.0.0.0`.

    ```vb
    'Add the current workflow version identities.
    StateMachineNumberGuessIdentity = New WorkflowIdentity With
    {
        .Name = "StateMachineNumberGuessWorkflow",
        .Version = New Version(2, 0, 0, 0)
    }

    FlowchartNumberGuessIdentity = New WorkflowIdentity With
    {
        .Name = "FlowchartNumberGuessWorkflow",
        .Version = New Version(2, 0, 0, 0)
    }

    SequentialNumberGuessIdentity = New WorkflowIdentity With
    {
        .Name = "SequentialNumberGuessWorkflow",
        .Version = New Version(2, 0, 0, 0)
    }

    map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())
    map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())
    map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())
    ```

    ```csharp
    // Add the current workflow version identities.
    StateMachineNumberGuessIdentity = new WorkflowIdentity
    {
        Name = "StateMachineNumberGuessWorkflow",
        // Version = new Version(1, 0, 0, 0),
        Version = new Version(2, 0, 0, 0)
    };

    FlowchartNumberGuessIdentity = new WorkflowIdentity
    {
        Name = "FlowchartNumberGuessWorkflow",
        // Version = new Version(1, 0, 0, 0),
        Version = new Version(2, 0, 0, 0)
    };

    SequentialNumberGuessIdentity = new WorkflowIdentity
    {
        Name = "SequentialNumberGuessWorkflow",
        // Version = new Version(1, 0, 0, 0),
        Version = new Version(2, 0, 0, 0)
    };

    map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());
    map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());
    map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());
    ```

    Il codice che aggiunge le versioni correnti dei flussi di lavoro al dizionario usa le versioni correnti a cui si fa riferimento nel progetto, in modo che il codice che inizializza le definizioni dei flusso di lavoro non deve essere aggiornato.

5. Aggiungere il seguente codice nel costruttore immediatamente dopo il codice che aggiunge le versioni correnti al dizionario.

    ```vb
    'Initialize the previous workflow version identities.
    StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With
    {
        .Name = "StateMachineNumberGuessWorkflow",
        .Version = New Version(1, 0, 0, 0)
    }

    FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With
    {
        .Name = "FlowchartNumberGuessWorkflow",
        .Version = New Version(1, 0, 0, 0)
    }

    SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With
    {
        .Name = "SequentialNumberGuessWorkflow",
        .Version = New Version(1, 0, 0, 0)
    }
    ```

    ```csharp
    // Initialize the previous workflow version identities.
    StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity
    {
        Name = "StateMachineNumberGuessWorkflow",
        Version = new Version(1, 0, 0, 0)
    };

    FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity
    {
        Name = "FlowchartNumberGuessWorkflow",
        Version = new Version(1, 0, 0, 0)
    };

    SequentialNumberGuessIdentity_v1 = new WorkflowIdentity
    {
        Name = "SequentialNumberGuessWorkflow",
        Version = new Version(1, 0, 0, 0)
    };
    ```

    Queste identità del flusso di lavoro sono associate alle versioni iniziali delle corrispondenti definizioni di flusso di lavoro.

6. Quindi, caricare l'assembly contenente la versione iniziale delle definizioni di flusso di lavoro e creare e aggiungere le definizioni corrispondenti di flusso di lavoro al dizionario.

    ```vb
    'Add the previous version workflow identities to the dictionary along with
    'the corresponding workflow definitions loaded from the v1 assembly.
    'Assembly.LoadFile requires an absolute path so convert this relative path
    'to an absolute path.
    Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)
    Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)

    map.Add(StateMachineNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))

    map.Add(SequentialNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))

    map.Add(FlowchartNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))
    ```

    ```csharp
    // Add the previous version workflow identities to the dictionary along with
    // the corresponding workflow definitions loaded from the v1 assembly.
    // Assembly.LoadFile requires an absolute path so convert this relative path
    // to an absolute path.
    string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);
    Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);

    map.Add(StateMachineNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);

    map.Add(SequentialNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);

    map.Add(FlowchartNumberGuessIdentity_v1,
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);
    ```

    L'esempio seguente è l'elenco di codice per la classe `WorkflowVersionMap` aggiornata.

    ```vb
    Public Module WorkflowVersionMap
        Dim map As Dictionary(Of WorkflowIdentity, Activity)

        'Current version identities.
        Public StateMachineNumberGuessIdentity As WorkflowIdentity
        Public FlowchartNumberGuessIdentity As WorkflowIdentity
        Public SequentialNumberGuessIdentity As WorkflowIdentity

        'v1 Identities.
        Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity
        Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity
        Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity

        Sub New()
            map = New Dictionary(Of WorkflowIdentity, Activity)

            'Add the current workflow version identities.
            StateMachineNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(2, 0, 0, 0)
            }

            FlowchartNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(2, 0, 0, 0)
            }

            SequentialNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(2, 0, 0, 0)
            }

            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())

            'Initialize the previous workflow version identities.
            StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            'Add the previous version workflow identities to the dictionary along with
            'the corresponding workflow definitions loaded from the v1 assembly.
            'Assembly.LoadFile requires an absolute path so convert this relative path
            'to an absolute path.
            Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)
            Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)

            map.Add(StateMachineNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))

            map.Add(SequentialNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))

            map.Add(FlowchartNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))
        End Sub

        Public Function GetWorkflowDefinition(identity As WorkflowIdentity) As Activity
            Return map(identity)
        End Function

        Public Function GetIdentityDescription(identity As WorkflowIdentity) As String
            Return identity.ToString()
        End Function
    End Module
    ```

    ```csharp
    public static class WorkflowVersionMap
    {
        static Dictionary<WorkflowIdentity, Activity> map;

        // Current version identities.
        static public WorkflowIdentity StateMachineNumberGuessIdentity;
        static public WorkflowIdentity FlowchartNumberGuessIdentity;
        static public WorkflowIdentity SequentialNumberGuessIdentity;

        // v1 identities.
        static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;
        static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;
        static public WorkflowIdentity SequentialNumberGuessIdentity_v1;

        static WorkflowVersionMap()
        {
            map = new Dictionary<WorkflowIdentity, Activity>();

            // Add the current workflow version identities.
            StateMachineNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                // Version = new Version(1, 0, 0, 0),
                Version = new Version(2, 0, 0, 0)
            };

            FlowchartNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                // Version = new Version(1, 0, 0, 0),
                Version = new Version(2, 0, 0, 0)
            };

            SequentialNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                // Version = new Version(1, 0, 0, 0),
                Version = new Version(2, 0, 0, 0)
            };

            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());

            // Initialize the previous workflow version identities.
            StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            SequentialNumberGuessIdentity_v1 = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            // Add the previous version workflow identities to the dictionary along with
            // the corresponding workflow definitions loaded from the v1 assembly.
            // Assembly.LoadFile requires an absolute path so convert this relative path
            // to an absolute path.
            string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);
            Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);

            map.Add(StateMachineNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);

            map.Add(SequentialNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);

            map.Add(FlowchartNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);
        }

        public static Activity GetWorkflowDefinition(WorkflowIdentity identity)
        {
            return map[identity];
        }

        public static string GetIdentityDescription(WorkflowIdentity identity)
        {
            return identity.ToString();
        }
    }
    ```

### <a name="BKMK_BuildAndRun"></a> Per compilare ed eseguire l'applicazione

1. Premere CTRL+MAIUSC+B per compilare l'applicazione, quindi premere CTRL+F5 per avviarla.

2. Avviare un nuovo flusso di lavoro facendo clic su **nuovo gioco**. La versione del flusso di lavoro viene visualizzata nella finestra di stato e riflette la versione aggiornata dall'oggetto `WorkflowIdentity` associato. Prendere nota di `InstanceId` in modo da poter visualizzare il file di traccia per il flusso di lavoro quando viene completato e quindi immettere i tentativi fino al termine del gioco. Si noti in che modo la stima dell'utente viene visualizzata tra le informazioni riportate nella finestra di stato in base agli aggiornamenti alle attività `WriteLine`.

    ```console
    Please enter a number between 1 and 10
    5 is too high.
    Please enter a number between 1 and 10
    3 is too high.
    Please enter a number between 1 and 10
    1 is too low.
    Please enter a number between 1 and 10
    Congratulations, you guessed the number in 4 turns.
    ```

    > [!NOTE]
    > Viene visualizzato il testo aggiornato dalle attività `WriteLine`, ma non l'output dell'attività finale `WriteLine` aggiunta in questo argomento. Ciò accade perché la finestra di stato viene aggiornata dal gestore `PersistableIdle`. Poiché il flusso di lavoro viene completato e non risulta inattivo dopo l'attività finale, il gestore `PersistableIdle` non viene chiamato. Tuttavia, viene visualizzato un messaggio simile nella finestra di stato dal gestore `Completed`. Se necessario, è possibile aggiungere il codice al gestore `Completed` per estrarre il testo da `StringWriter` e per visualizzarlo nella finestra di stato.

3. Aprire Esplora risorse e passare alla cartella **NumberGuessWorkflowHost\bin\debug** (o **bin\release** a seconda delle impostazioni del progetto) e aprire il file di rilevamento utilizzando il blocco note corrispondente al flusso di lavoro completato. Se non è stata annotata la `InstanceId`, è possibile identificare il file di rilevamento corretto utilizzando le informazioni **modificate** in Esplora risorse.

    ```console
    Please enter a number between 1 and 10
    5 is too high.
    Please enter a number between 1 and 10
    3 is too high.
    Please enter a number between 1 and 10
    1 is too low.
    Please enter a number between 1 and 10
    2 is correct. You guessed it in 4 turns.
    ```

    L'output di `WriteLine` aggiornato è contenuto nel file di rilevamento, incluso l'output di `WriteLine` aggiornato in questo argomento.

4. Passare di nuovo all'applicazione per determinare il numero e selezionare uno dei flussi di lavoro avviato prima dell'applicazione degli aggiornamenti. È possibile identificare la versione del flusso di lavoro attualmente selezionato esaminando le informazioni sulla versione visualizzate nella finestra di stato. Immettere alcuni tentativi e notare che gli aggiornamenti di stato corrispondono all'output dell'attività `WriteLine` della versione precedente e non includono il tentativo dell'utente. Questo perché questi flussi di lavoro usano la definizione precedente del flusso di lavoro che non presenta gli aggiornamenti di `WriteLine`.

    Nel passaggio successivo, [procedura: Aggiornare la definizione di un'istanza](how-to-update-the-definition-of-a-running-workflow-instance.md)del flusso di lavoro in esecuzione, le istanze del flusso di lavoro in esecuzione `v1` vengono aggiornate `v2` in modo che contengano la nuova funzionalità come istanze di.

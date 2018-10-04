---
title: Creazione di attività del flusso di lavoro tramite la classe CodeActivity
ms.date: 03/30/2017
ms.assetid: cfe315c1-f86d-43ec-b9ce-2f8c469b1106
ms.openlocfilehash: 4954dfa5dba03823d119a456149f0f16cf5ed410
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48580128"
---
# <a name="workflow-activity-authoring-using-the-codeactivity-class"></a>Creazione di attività del flusso di lavoro tramite la classe CodeActivity
Le attività create ereditando dall'oggetto <xref:System.Activities.CodeActivity> possono implementare il comportamento imperativo di base eseguendo l'override del metodo <xref:System.Activities.CodeActivity.Execute%2A>.

## <a name="using-codeactivitycontext"></a>Uso di CodeActivityContext
 L'accesso a funzionalità dell'esecuzione del flusso di lavoro può essere eseguito dall'interno del metodo <xref:System.Activities.CodeActivity.Execute%2A> tramite i membri del parametro `context`, di tipo <xref:System.Activities.CodeActivityContext>. Tra le funzionalità disponibili tramite l'oggetto <xref:System.Activities.CodeActivityContext> sono incluse le seguenti:

-   Recupero e impostazione di valori di variabili e di argomenti.

-   Funzionalità di rilevamento personalizzate tramite <xref:System.Activities.CodeActivityContext.Track%2A>.

-   Accesso alle proprietà di esecuzione dell'attività tramite il metodo <xref:System.Activities.CodeActivityContext.GetProperty%2A>.

#### <a name="to-create-a-custom-activity-that-inherits-from-codeactivity"></a>Per creare un'attività personalizzata che eredita da CodeActivity

1.  Aprire Visual Studio 2010.

2.  Selezionare **File**, **nuove**e quindi **progetto**. Selezionare **Workflow 4.0** sotto **Visual c#** nel **tipi di progetto** finestra e selezionare il **v2010** nodo. Selezionare **libreria di attività** nel **modelli** finestra. Assegnare al nuovo progetto il nome HelloActivity.

3.  Fare doppio clic su Activity1.xaml nel progetto HelloActivity e selezionare **Elimina**.

4.  Pulsante destro del mouse sul progetto HelloActivity e selezionare **Add** e quindi **classe**. Assegnare alla nuova classe il nome HelloActivity.cs.

5.  Nel file HelloActivity.cs aggiungere le seguenti istruzioni `using`.

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6.  Assicurarsi che la nuova classe erediti dall'oggetto <xref:System.Activities.CodeActivity> aggiungendo una classe base alla dichiarazione di classe.

    ```csharp
    class HelloActivity : CodeActivity
    ```

7.  Aggiungere la funzionalità alla classe aggiungendo un metodo <xref:System.Activities.CodeActivity.Execute%2A>.

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8.  Usare l'oggetto <xref:System.Activities.CodeActivityContext> per creare un record di rilevamento.

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
        CustomTrackingRecord record = new CustomTrackingRecord("MyRecord");
        record.Data.Add(new KeyValuePair<String, Object>("ExecutionTime", DateTime.Now));
        context.Track(record);
    }
    ```

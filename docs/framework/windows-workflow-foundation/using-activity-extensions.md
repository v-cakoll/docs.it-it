---
title: Utilizzo di estensioni di attività
ms.date: 03/30/2017
ms.assetid: 500eb96a-c009-4247-b6b5-b36faffdf715
ms.openlocfilehash: 551ce24db8c0adc8225ac94a1d05f998a26873a9
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988629"
---
# <a name="using-activity-extensions"></a><span data-ttu-id="99953-102">Utilizzo di estensioni di attività</span><span class="sxs-lookup"><span data-stu-id="99953-102">Using Activity Extensions</span></span>
<span data-ttu-id="99953-103">Le attività possono interagire con estensioni dell'applicazione flusso di lavoro che consentono all'host di fornire funzionalità aggiuntive non modellate in modo esplicito nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="99953-103">Activities can interact with workflow application extensions that allow the host to provide additional functionality that is not explicitly modeled in the workflow.</span></span>  <span data-ttu-id="99953-104">In questo argomento viene descritto come creare e usare un'estensione per contare il numero di volte in cui un'attività viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="99953-104">This topic describes how to create and use an extension to count the number of times the activity executes.</span></span>

### <a name="to-use-an-activity-extension-to-count-executions"></a><span data-ttu-id="99953-105">Per usare un'estensione di attività per contare le esecuzioni</span><span class="sxs-lookup"><span data-stu-id="99953-105">To use an activity extension to count executions</span></span>

1. <span data-ttu-id="99953-106">Aprire Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="99953-106">Open Visual Studio 2010.</span></span> <span data-ttu-id="99953-107">Selezionare **nuovo**, **progetto**.</span><span class="sxs-lookup"><span data-stu-id="99953-107">Select **New**, **Project**.</span></span> <span data-ttu-id="99953-108">Nel nodo **visivo C#**  Selezionare flusso di **lavoro**.</span><span class="sxs-lookup"><span data-stu-id="99953-108">Under the **Visual C#** node, select **Workflow**.</span></span>  <span data-ttu-id="99953-109">Selezionare **applicazione console flusso di lavoro** dall'elenco di modelli.</span><span class="sxs-lookup"><span data-stu-id="99953-109">Select **Workflow Console Application** from the list of templates.</span></span> <span data-ttu-id="99953-110">Denominare il progetto `Extensions`.</span><span class="sxs-lookup"><span data-stu-id="99953-110">Name the project `Extensions`.</span></span> <span data-ttu-id="99953-111">Fare clic su **OK** per creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="99953-111">Click **OK** to create the project.</span></span>

2. <span data-ttu-id="99953-112">Aggiungere un' `using` istruzione nel file Program.cs per lo spazio dei nomi **System. Collections. Generic** .</span><span class="sxs-lookup"><span data-stu-id="99953-112">Add a `using` statement in the Program.cs file for the **System.Collections.Generic** namespace.</span></span>

    ```csharp
    using System.Collections.Generic;
    ```

3. <span data-ttu-id="99953-113">Nel file Program.cs creare una nuova classe denominata **ExecutionCountExtension**.</span><span class="sxs-lookup"><span data-stu-id="99953-113">In the Program.cs file, create a new class named **ExecutionCountExtension**.</span></span> <span data-ttu-id="99953-114">Il codice seguente crea un'estensione del flusso di lavoro che tiene traccia degli ID istanza quando viene chiamato il metodo **Register** .</span><span class="sxs-lookup"><span data-stu-id="99953-114">The following code creates a workflow extension that tracks instance IDs when its **Register** method is called.</span></span>

    ```csharp
    // This extension collects a list of workflow Ids
    public class ExecutionCountExtension
    {
        IList<Guid> instances = new List<Guid>();

        public int ExecutionCount
        {
            get
            {
                return this.instances.Count;
            }
        }

        public IEnumerable<Guid> InstanceIds
        {
            get
            {
                return this.instances;
            }
        }

        public void Register(Guid activityInstanceId)
        {
            if (!this.instances.Contains<Guid>(activityInstanceId))
            {
                instances.Add(activityInstanceId);
            }
        }
    }
    ```

4. <span data-ttu-id="99953-115">Creare un'attività che utilizza **ExecutionCountExtension**.</span><span class="sxs-lookup"><span data-stu-id="99953-115">Create an activity that consumes the **ExecutionCountExtension**.</span></span> <span data-ttu-id="99953-116">Il codice seguente definisce un'attività che recupera l'oggetto **ExecutionCountExtension** dal runtime e chiama il relativo metodo **Register** quando viene eseguita l'attività.</span><span class="sxs-lookup"><span data-stu-id="99953-116">The following code defines an activity that retrieves the **ExecutionCountExtension** object from the runtime and calls its **Register** method when the activity executes.</span></span>

    ```csharp
    // Activity that consumes an extension provided by the host. If the extension is available
    // in the context, it will invoke (in this case, registers the Id of the executing workflow)
    public class MyActivity: CodeActivity
    {
        protected override void Execute(CodeActivityContext context)
        {
            ExecutionCountExtension ext = context.GetExtension<ExecutionCountExtension>();
            if (ext != null)
            {
                ext.Register(context.WorkflowInstanceId);
            }

        }
    }
    ```

5. <span data-ttu-id="99953-117">Implementare l'attività nel metodo **Main** del file Program.cs.</span><span class="sxs-lookup"><span data-stu-id="99953-117">Implement the activity in the **Main** method of the program.cs file.</span></span> <span data-ttu-id="99953-118">Nel codice seguente sono contenuti metodi per generare due flussi di lavoro diversi, eseguire ogni flusso di lavoro più volte e visualizzare i dati risultanti contenuti nell'estensione.</span><span class="sxs-lookup"><span data-stu-id="99953-118">The following code contains methods to generate two different workflows, execute each workflow several times, and display the resulting data that is contained in the extension.</span></span>

    ```csharp
    class Program
    {
        // Creates a workflow that uses the activity that consumes the extension
        static Activity CreateWorkflow1()
        {
            return new Sequence
            {
                Activities =
                {
                    new MyActivity()
                }
            };
        }

        // Creates a workflow that uses two instances of the activity that consumes the extension
        static Activity CreateWorkflow2()
        {
            return new Sequence
            {
                Activities =
                {
                    new MyActivity(),
                    new MyActivity()
                }
            };
        }

        static void Main(string[] args)
        {
            // create the extension
            ExecutionCountExtension executionCountExt = new ExecutionCountExtension();

            // configure the first invoker and execute 3 times
            WorkflowInvoker invoker = new WorkflowInvoker(CreateWorkflow1());
            invoker.Extensions.Add(executionCountExt);
            invoker.Invoke();
            invoker.Invoke();
            invoker.Invoke();

            // configure the second invoker and execute 2 times
            WorkflowInvoker invoker2 = new WorkflowInvoker(CreateWorkflow2());
            invoker2.Extensions.Add(executionCountExt);
            invoker2.Invoke();
            invoker2.Invoke();

            // show the data in the extension
            Console.WriteLine("Executed {0} times", executionCountExt.ExecutionCount);
            executionCountExt.InstanceIds.ToList().ForEach(i => Console.WriteLine("...{0}", i));
        }
    }
    ```

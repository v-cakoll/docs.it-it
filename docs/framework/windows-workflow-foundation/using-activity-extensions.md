---
title: Utilizzo di estensioni di attività
ms.date: 03/30/2017
ms.assetid: 500eb96a-c009-4247-b6b5-b36faffdf715
ms.openlocfilehash: 420bd25a94f67169d299bbac64dae06e15c5b0b2
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2018
ms.locfileid: "48845521"
---
# <a name="using-activity-extensions"></a><span data-ttu-id="2ad7f-102">Utilizzo di estensioni di attività</span><span class="sxs-lookup"><span data-stu-id="2ad7f-102">Using Activity Extensions</span></span>
<span data-ttu-id="2ad7f-103">Le attività possono interagire con estensioni dell'applicazione flusso di lavoro che consentono all'host di fornire funzionalità aggiuntive non modellate in modo esplicito nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2ad7f-103">Activities can interact with workflow application extensions that allow the host to provide additional functionality that is not explicitly modeled in the workflow.</span></span>  <span data-ttu-id="2ad7f-104">In questo argomento viene descritto come creare e usare un'estensione per contare il numero di volte in cui un'attività viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="2ad7f-104">This topic describes how to create and use an extension to count the number of times the activity executes.</span></span>

### <a name="to-use-an-activity-extension-to-count-executions"></a><span data-ttu-id="2ad7f-105">Per usare un'estensione di attività per contare le esecuzioni</span><span class="sxs-lookup"><span data-stu-id="2ad7f-105">To use an activity extension to count executions</span></span>

1.  <span data-ttu-id="2ad7f-106">Aprire Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="2ad7f-106">Open Visual Studio 2010.</span></span> <span data-ttu-id="2ad7f-107">Selezionare **nuove**, **progetto**.</span><span class="sxs-lookup"><span data-stu-id="2ad7f-107">Select **New**, **Project**.</span></span> <span data-ttu-id="2ad7f-108">Sotto il **Visual c#** nodo, seleziona **flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="2ad7f-108">Under the **Visual C#** node, select **Workflow**.</span></span>  <span data-ttu-id="2ad7f-109">Selezionare **applicazione Console flusso di lavoro** dall'elenco dei modelli.</span><span class="sxs-lookup"><span data-stu-id="2ad7f-109">Select **Workflow Console Application** from the list of templates.</span></span> <span data-ttu-id="2ad7f-110">Denominare il progetto `Extensions`.</span><span class="sxs-lookup"><span data-stu-id="2ad7f-110">Name the project `Extensions`.</span></span> <span data-ttu-id="2ad7f-111">Fare clic su **OK** per creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="2ad7f-111">Click **OK** to create the project.</span></span>

2.  <span data-ttu-id="2ad7f-112">Aggiungere un `using` istruzione nel file Program.cs per il **System.Collections.Generic** dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="2ad7f-112">Add a `using` statement in the Program.cs file for the **System.Collections.Generic** namespace.</span></span>

    ```
    using System.Collections.Generic;
    ```

3.  <span data-ttu-id="2ad7f-113">Nel file Program.cs, creare una nuova classe denominata **ExecutionCountExtension**.</span><span class="sxs-lookup"><span data-stu-id="2ad7f-113">In the Program.cs file, create a new class named **ExecutionCountExtension**.</span></span> <span data-ttu-id="2ad7f-114">Il codice seguente crea un'estensione del flusso di lavoro che tiene traccia degli ID istanza quando relativi **registrare** viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="2ad7f-114">The following code creates a workflow extension that tracks instance IDs when its **Register** method is called.</span></span>

    ```
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

4.  <span data-ttu-id="2ad7f-115">Creare un'attività che utilizza il **ExecutionCountExtension**.</span><span class="sxs-lookup"><span data-stu-id="2ad7f-115">Create an activity that consumes the **ExecutionCountExtension**.</span></span> <span data-ttu-id="2ad7f-116">Il codice seguente definisce un'attività che recupera le **ExecutionCountExtension** oggetto dal runtime e chiama relativo **registrare** metodo quando viene eseguita l'attività.</span><span class="sxs-lookup"><span data-stu-id="2ad7f-116">The following code defines an activity that retrieves the **ExecutionCountExtension** object from the runtime and calls its **Register** method when the activity executes.</span></span>

    ```
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

5.  <span data-ttu-id="2ad7f-117">Implementare l'attività nel **Main** metodo del file program.cs.</span><span class="sxs-lookup"><span data-stu-id="2ad7f-117">Implement the activity in the **Main** method of the program.cs file.</span></span> <span data-ttu-id="2ad7f-118">Nel codice seguente sono contenuti metodi per generare due flussi di lavoro diversi, eseguire ogni flusso di lavoro più volte e visualizzare i dati risultanti contenuti nell'estensione.</span><span class="sxs-lookup"><span data-stu-id="2ad7f-118">The following code contains methods to generate two different workflows, execute each workflow several times, and display the resulting data that is contained in the extension.</span></span>

    ```
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

---
title: Utilizzo di estensioni di attività
ms.date: 03/30/2017
ms.assetid: 500eb96a-c009-4247-b6b5-b36faffdf715
ms.openlocfilehash: 32c465ae42a1f0238fab7bba5ea795486db3b562
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="using-activity-extensions"></a>Utilizzo di estensioni di attività
Le attività possono interagire con estensioni dell'applicazione flusso di lavoro che consentono all'host di fornire funzionalità aggiuntive non modellate in modo esplicito nel flusso di lavoro.  In questo argomento viene descritto come creare e usare un'estensione per contare il numero di volte in cui un'attività viene eseguita.  
  
### <a name="to-use-an-activity-extension-to-count-executions"></a>Per usare un'estensione di attività per contare le esecuzioni  
  
1.  Aprire [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]. Selezionare **nuova**, **progetto**. Sotto il **Visual c#** nodo, seleziona **flusso di lavoro**.  Selezionare **applicazione Console flusso di lavoro** dall'elenco dei modelli. Denominare il progetto `Extensions`. Fare clic su **OK** per creare il progetto.  
  
2.  Aggiungere un `using` istruzione nel file Program.cs per il **System.Collections.Generic** dello spazio dei nomi.  
  
    ```  
    using System.Collections.Generic;  
    ```  
  
3.  Nel file Program.cs, creare una nuova classe denominata **ExecutionCountExtension**. Il codice seguente crea un'estensione del flusso di lavoro che tiene traccia degli ID istanza quando la **registrare** metodo viene chiamato.  
  
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
  
4.  Creare un'attività che usa il **ExecutionCountExtension**. Il codice seguente definisce un'attività che recupera il **ExecutionCountExtension** oggetto dal runtime e chiama il relativo **registrare** metodo quando l'attività viene eseguita.  
  
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
  
5.  Implementare l'attività nel **Main** metodo del file program.cs. Nel codice seguente sono contenuti metodi per generare due flussi di lavoro diversi, eseguire ogni flusso di lavoro più volte e visualizzare i dati risultanti contenuti nell'estensione.  
  
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
